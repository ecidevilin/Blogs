!["pipeline"](https://pic2.zhimg.com/v2-3785f9c0621f81a80cdab6fbaa3d04b5_b.jpg)

图1：渲染管线，图片来源：Introduction to 3D Game Programming with DirectX 12

# IA

当我们使用曲面细分的时候，我们不再向IA阶段（Input Assembler Stage，输入装配阶段，从显存读取几何数据用来组合几何图元，例如三角面或线段）提交三角面，而是提交数个控制点的patch。
三角形可以认为是有三个控制点的patch，所以我们依然可以提交常规的三角面网格。一个有四个控制点的四边形也可以被提交，但是在曲面细分阶段这些patch会被细分成三角面。
当然我们还可以在一个patch中添加更多的控制点。例如，我们可以用多个控制点来调整贝塞尔曲线（Bezier curves），或者贝塞尔曲面。控制点越多，自由度越高。

# VS

控制点也会经过VS的处理，在这里，我们可以做一些对控制点的计算，例如动画或者物理计算。

# HS

经过处理后的控制点会传到HS（对应于OpenGL Core的TCS，Tessellation Control Shader）,HS又会分为Const Hull Shader和Control Point Hull Shader。

## ConstHS

示例代码：

```
struct PatchTess
{
float EdgeTess[4] : SV_TessFactor;
float InsideTess[2] : SV_InsideTessFactor;
// Additional info you want associated per patch.
};
PatchTess ConstantHS(InputPatch<VertexOut, 4> patch,
uint patchID : SV_PrimitiveID)
{
PatchTess pt;
// Uniformly tessellate the patch 3 times.
pt.EdgeTess[0] = 3; // Left edge
pt.EdgeTess[1] = 3; // Top edge
pt.EdgeTess[2] = 3; // Right edge
pt.EdgeTess[3] = 3; // Bottom edge
pt.InsideTess[0] = 3; // u-axis (columns)
pt.InsideTess[1] = 3; // v-axis (rows)
return pt;
}
```

InputPatch<VertexOut,4>尖括号中的4代表输入的控制点的数量（每个图元），由API设置。
SV_TessFactor代表细分度，SV_InsideTessFactor代表内部细分度。至于如何细分，我们稍后会解释。

## ControlPointHS

示例代码：

```
struct HullOut
{
float3 PosL : POSITION;
};
[domain(“quad”)]
[partitioning(“integer”)]
[outputtopology(“triangle_cw”)]
[outputcontrolpoints(4)]
[patchconstantfunc(“ConstantHS”)]
[maxtessfactor(64.0f)]
HullOut HS(InputPatch<VertexOut, 4> p,
uint i : SV_OutputControlPointID,
uint patchId : SV_PrimitiveID)
{
HullOut hout;
hout.PosL = p[i].PosL;
return hout;
}
```

我们来看一下HS的几个属性：
1. domain: 指定patch的类型，可选的有：tri(三角形)、quad（四边形）、isoline（线段，苹果的metal api不支持2018/8/21）。不同的patch类型，细分的方式也有差别，后面会详细介绍。
2. partitioning：分割模式，有三种：integer，fractional_even，fractional_odd。这三种分割模式，如图2、图3、图4所示。
![图2：integer](https://pic1.zhimg.com/80/v2-87029cee3fbdd447a97e188c2a52d2a2_hd.gif)
![图3：fractional_odd](https://pic1.zhimg.com/80/v2-00b8af0c4de4405d525ba6606f9cb24b_hd.gif)
![图4：fractional_even](https://pic2.zhimg.com/80/v2-092729346554f82f7e7fd56717e2f8f2_hd.gif)
3. outputtopology：输出拓扑结构。有三种：triangle_cw（顺时针环绕三角形）、triangle_ccw（逆时针环绕三角形）、line（线段）。
4. outputcontrolpoints：输出的控制点的数量（每个图元），不一定与输入数量相同。
5. patchconstantfunc：指定ConstHS。
6. maxtessfactor：最大细分度，告知驱动程序我们的shader用到的最大细分度，硬件可能会针对这个做出优化。Direct3D 11和OpenGL Core都至少支持64。
然后是HS的参数：
1. InputPatch：输入的patch。
2. SV_OutputControlPointID：给出控制点的ID。
3. SV_PrimitiveID：给出patch的ID。

下面着重展示一下SV_TessFactor和SV_InsideTessFactor在不同path类型上是如何细分的。
对于三种不同的patch类型：

### quad

SV_TessFactor的长度为4，指定四条边各被分为多少段，SV_InsideTessFactor长度为2，指定内部在横向和纵向上各被分为多少段，如图5所示。

![图5：SV_TessFactor:4,2,9,3 SV_InsideTessFactor:6,7](https://pic2.zhimg.com/80/v2-c8a71cd56b5922e175e4b7c0d8206654_hd.png)


### tri

SV_TessFactor的长度为3，指定三条边各被分为多少段，SV_InsideTessFactor的长度为1，指定内部有多少个点。关于内部点的计算方法，如图6和图7所示，对于三角形的每个顶点，将他们的临边分割，然后在分割点上做垂线，得到的交点即为内部点。

![图6](https://pic4.zhimg.com/80/v2-c9b07f0b90604ce60e242d39bc2349e8_hd.png)
![图7](https://pic2.zhimg.com/80/v2-e5ae5deba4275b691231eacd56059e3b_hd.png)


整体分割，如果图8所示。


![图8：SV_TessFactor:4,1,6 SV_InsideTessFactor:5](https://pic1.zhimg.com/80/v2-4d52caa84ea507d65d767f237262091e_hd.png)


### isoline

SV_TessFactor长度为2，第0个元素指定线段的个数，第1个元素指定线段被分为多少段，SV_InsideTessFactor会被忽略。如图9和图10所示。

![图9：SV_TessFactor:3,4](https://pic3.zhimg.com/80/v2-d2897dbffe7f4a0114469af369c81742_hd.png)
![图10：SV_TessFactor:6,2](https://pic4.zhimg.com/80/v2-3a5885bd4ffab81cb926725ce3352eae_hd.png)