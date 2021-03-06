!["pipeline"](https://pic2.zhimg.com/v2-3785f9c0621f81a80cdab6fbaa3d04b5_b.jpg "图1：渲染管线，图片来源：Introduction to 3D Game Programming with DirectX 12")

<center> 图1：渲染管线，图片来源：Introduction to 3D Game Programming with DirectX 12 </center>


曲面细分是渲染管线的一个可选项，我们可以用它来对网格进行平滑处理，也可以用它来实现连续LOD（Levels of Details）算法。本文为曲面细分的学习笔记，粗略的描述了渲染管线中曲面细分的相关阶段。这里以DirectX 12为主要描述对象，OpenGL作为补充。


# Input Assembler Stage

当我们使用曲面细分的时候，我们不再向IA阶段（Input Assembler Stage，输入装配阶段，从显存读取几何数据用来组合几何图元）提交三角面，而是提交包含数个控制点的patch。例如isoline，我们提交线段的两端作为控制点传给GPU，以这两个控制点为基础来对线段进行变形。

三角形可以认为是有三个控制点的patch，所以我们依然可以提交常规的三角面网格。四边形（四个控制点）也可以被提交，不过在曲面细分阶段这些patch会被细分成三角面。

当然我们还可以在一个patch中添加更多的控制点。例如，我们可以用多个控制点来调整贝塞尔曲线（Bezier curves），或者贝塞尔曲面。控制点越多，自由度越高。

# Vertex Shader

控制点也会经过VS的处理，或者说，VS变成了控制点的shader。在这里，我们可以做一些针对控制点的计算，例如动画或者物理计算。

# Hull Shader

经过VS处理后的控制点会传到HS（对应于OpenGL的TCS，Tessellation Control Shader）,HS又会分为Const Hull Shader和Control Point Hull Shader。

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
1. domain: 指定patch的类型，可选的有：tri(三角形)、quad（四边形）、isoline（线段，苹果的metal api不支持：2018/8/21）。不同的patch类型，细分的方式也有差别，后面会详细介绍。
2. partitioning：分割模式，有三种：integer，fractional_even，fractional_odd。这三种分割模式，如图2、图3、图4所示。

![2](https://pic1.zhimg.com/80/v2-87029cee3fbdd447a97e188c2a52d2a2_hd.gif)

<center> 图2：integer </center>

![3](https://pic1.zhimg.com/80/v2-00b8af0c4de4405d525ba6606f9cb24b_hd.gif)

<center> 图3：fractional_odd </center>

![4](https://pic2.zhimg.com/80/v2-092729346554f82f7e7fd56717e2f8f2_hd.gif)

<center> 图4：fractional_even </center>


3. outputtopology：输出拓扑结构。有三种：triangle_cw（顺时针环绕三角形）、triangle_ccw（逆时针环绕三角形）、line（线段）。
4. outputcontrolpoints：输出的控制点的数量（每个图元），不一定与输入数量相同，也可以新增控制点。
5. patchconstantfunc：指定ConstHS。
6. maxtessfactor：最大细分度，告知驱动程序shader用到的最大细分度，硬件可能会针对这个做出优化。Direct3D 11和OpenGL Core都至少支持64。
然后是HS的参数：
1. InputPatch：输入的patch尖括号第二个参数，代表输入的控制点的数量（“quad”为4个），由API设置，并且ConstHS里对应的数值要与这里相同。
2. SV_OutputControlPointID：给出控制点的ID，与outputcontrolpoints对应，例如outputcontrolpoints为4，那么i的取值就是[0,4)的整数。
3. SV_PrimitiveID：给出patch的ID。

下面着重展示一下SV_TessFactor和SV_InsideTessFactor在不同path类型上是如何细分的。
对于三种不同的patch类型：

### quad

SV_TessFactor的长度为4，指定四条边各被分为多少段，SV_InsideTessFactor长度为2，指定内部在横向和纵向上各被分为多少段，如图5所示。

![5](https://pic2.zhimg.com/80/v2-c8a71cd56b5922e175e4b7c0d8206654_hd.png)

<center> 图5：SV_TessFactor:4,2,9,3 SV_InsideTessFactor:6,7 </center>


### tri

SV_TessFactor的长度为3，指定三条边各被分为多少段，SV_InsideTessFactor的长度为1，指定内部有多少个点。关于内部点的计算方法，如图6和图7所示，对于三角形的每个顶点，将他们的临边分割，然后在分割点上做垂线，得到的交点即为内部点。

![6](https://pic4.zhimg.com/80/v2-c9b07f0b90604ce60e242d39bc2349e8_hd.png)

<center> 图6 </center>

![7](https://pic2.zhimg.com/80/v2-e5ae5deba4275b691231eacd56059e3b_hd.png)

<center> 图7 </center>


整体分割，如果图8所示。


![8](https://pic1.zhimg.com/80/v2-4d52caa84ea507d65d767f237262091e_hd.png)

<center> 图8：SV_TessFactor:4,1,6 SV_InsideTessFactor:5 </center>


### isoline

SV_TessFactor长度为2，第0个元素指定线段的个数，第1个元素指定线段被分为多少段，SV_InsideTessFactor会被忽略。如图9和图10所示。

![9](https://pic1.zhimg.com/80/v2-1d6bb900e6306fd44359c0845f03ce0b_hd.png)

<center> 图9：SV_TessFactor:3,4  </center>

![10](https://pic1.zhimg.com/80/v2-568592621503bc8d53f95c00791a4fa2_hd.png)

<center> 图10：SV_TessFactor:6,2 </center>

# Tessellation Stage

曲面细分阶段，这个阶段是由硬件完成的，会根据ConstHS将patch分割成多个三角面或者线段。这些顶点会被传给下一个阶段DS，以供插值。

对于不同的patch，这些顶点的形式也不一样。

## quad

顶点以UV坐标的形式传给DS，如图11所示。

![11](https://pic1.zhimg.com/80/v2-4137fdf02af78b2f3342c0d2c01ca829_hd.png)

<center> 图11 </center>

## tri

顶点以重心坐标（[Barycentric coordinates](https://en.wikipedia.org/wiki/Barycentric_coordinate_system#Barycentric_coordinates_on_triangles)）的形式(u, v, w)传给DS，如图12所示。

![12](https://pic4.zhimg.com/80/v2-c409ca0f839a291ec6bd77b7f5f63b90_hd.png)

<center> 图12 </center>

## isoline

顶点以UV坐标的形式传给DS，如图13所示。

![13](https://pic2.zhimg.com/80/v2-ebcb92ec3bcf6457e2a81234ba2c70c1_hd.jpg)

<center> 图13 </center>

# Domain Shader

从曲面细分阶段获取新创建的顶点和三角面（或线段）之后，便进入了DS（对应于OpenGL Core的TES，Tessellation Evaluation Shader）阶段。对于每个顶点，都会调用一次DS。一般来讲，这里会涉及到大量的计算，所有的顶点信息都会在这里重新计算，最后会将顶点坐标转换到投影空间。

示例代码：
```
struct DomainOut
{
float4 PosH : SV_POSITION;
};
// The domain shader is called for every vertex
created by the tessellator.
// It is like the vertex shader after tessellation.
[domain(“quad”)]
DomainOut DS(PatchTess patchTess,
float2 uv : SV_DomainLocation,
const OutputPatch<HullOut, 4> quad)
{
DomainOut dout;
// Bilinear interpolation.
float3 v1 = lerp(quad[0].PosL, quad[1].PosL, uv.x);
float3 v2 = lerp(quad[2].PosL, quad[3].PosL, uv.x);
float3 p = lerp(v1, v2, uv.y);
float4 posW = mul(float4(p, 1.0f), gWorld);
dout.PosH = mul(posW, gViewProj);
return dout;
}
```

DS的参数：
1. PatchTess：由ConstHS输入，细分参数。
2. SV_DomainLocation：由曲面细分阶段阶段传入的顶点位置信息。
3. OutputPatch<HullOut, 4>：由ControlPointHS传入的patch数据，尖括号的第二个参数与outputcontrolpoints对应。

这里的patch类型是quad，先求当前顶点的坐标，然后转换到投影空间。
如果patch类型是tri：
```
[domain(“tri”)]
DomainOut DS(PatchTess patchTess,
float3 uvw : SV_DomainLocation,
const OutputPatch<HullOut, 3> tri)
{
DomainOut dout;
// Bilinear interpolation.
float3 p = tri[0] * uvw.x + tri[1] * uvw.y + tri[2] * uvw.z;
float4 posW = mul(float4(p, 1.0f), gWorld);
dout.PosH = mul(posW, gViewProj);
return dout;
}
```

这里没有做任何的变形，只是将顶点坐标计算出来，最后渲染出来的结果跟没有做曲面细分的shader没有区别。
我们可以使用贝塞尔曲线或曲面来改变三角面的形状，详情请参考文献1（或许会在后续文章中介绍，但愿……）。


DS输出的数据，可能会先传给GS（Geometry Shader）进行进一步的计算（增加顶点、修改顶点位置，计算顶点属性）。也可以直接（当然首先要进行裁剪和光栅化）传给FS（Fragment Shader）进行片元着色。最后进入输出合并阶段，完成整个渲染管线。

#参考文献

1. Introduction to 3D Game Programming with DirectX 12
2. [OpenGL Tessellation](https://www.khronos.org/opengl/wiki/Tessellation)
3. [Tessellation Modes Quick Reference](http://reedbeta.com/blog/tess-quick-ref/)