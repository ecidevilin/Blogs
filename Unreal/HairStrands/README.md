# UE4.24 Hair Strands
UE4.24推出了次世代发丝（Hair Strands）系统Groom，其实现大量参考了寒霜在Siggraph2019 Advances in Real-Time Rendering in Games course上的演讲。
[Strand-based Hair Rendering in Frostbite]("http://advances.realtimerendering.com/s2019/hair_presentation_final.pptx")   
在写这篇文章的时候，UE4.25已经出preview版本了，但是preview版本更新过于频繁，本文暂时还是以4.24.3来作为基础。  
UE4的实现主要分为以下三个部分：
* 基于Niagara实现的物理模拟
* Visibility Buffer管线
* BSDF
* Deep Opacity Maps和Dual Scattering
* 环境光和AO

其中，物理模拟部分的实现在以下目录里：
```
...\UE_4.24\Engine\Plugins\Experimental\HairStrands\
```
Visibility Buffer和BSDF部分的实现在以下目录里：
```
...\UE_4.24\Engine\Shaders\Private\HairStrands
...\UE_4.24\Engine\Source\Runtime\Renderer\Private\HairStrands
```

## 基于Niagara实现的物理模拟
UE4将发丝的物理模拟部分融合进了Niagara里，这一步操作有点让我不知道该怎么评价。   
我们可以看到，默认的Groom Niagara System Asset是这样的结构。
![Niagara](pic\Niagara.png)
整体采用堆叠式的组件结构，内部采用类似于蓝图或者材质编辑器一样的节点结构，通过这些节点拼合成运行时使用的shader。  
然而物理模拟各部分之间有比较强的依赖关系，很多步骤需要前置步骤的结果。例如Compute Grid Weights需要Transfer Groom Velocity的结果，并且它计算得到的结果要在下一帧里给Update Groom Velocity使用。这样的情况下，如果删除或者禁用某个组件，就无法得到正确的结果。并且，为了组件化、节点化，就难免会写一些冗余的代码。所以，在我看来，基于Niagara来实现发丝的物理模拟，着实有些多此一举了。   
话虽如此，我们还是来看看物理模拟部分是怎样实现的，主要分为三个部分：   
* HairStrands : 动力学模拟
* PhiysicsAsset ： 碰撞检测与反馈
* PressureGrid ： 速度场约束

### 动力学模拟
区别于常用的Verlet积分（TressFX），UE4采用了Eulerian积分来计算质点的线性移动，并增加了扭矩来计算质点的方位（Orientation）。     
而对于形状/长度约束，一般模拟头发会将头发视为弹簧质点模型来进行模拟，但其实头发的拉伸性并不是很好，所以UE4先将头发视为Cosserat细长竿（Rod）模型来模拟，对头发的位置（长度）和方位（形状）进行约束。   
在进行完Cosserat Rod约束之后，再用弹簧质点模型进行约束，这里使用了Lagrangian积分来对相邻（弹簧）质点之间进行约束。另外，还对头发的弯曲（bend）和扭转（twist）进行了约束，但本质上是对间隔一个（bend）或两个（twist）的质点进行Lagrangian积分。

### 碰撞检测与反馈
碰撞检测部分做得相对简单，将头发质点与球、立方体和胶囊体进行碰撞检测，然后修正质点的位置。没有做像TressFX那么SDF那种复杂的碰撞。

### 速度场约束
前两个都是基本操作，PressureGrid是UE4新加的，似乎参考了寒霜PPT模拟部分的第三点。
![FrostbiteSimulation](pic\FrostbiteSimulation.png)
然而又感觉有些出入。毕竟，寒霜PPT没有对这部分进行详细介绍，而向量场又是UE4的看家本领，拿来做替代品似乎也不错。   
速度场类似于体素的原理，根据头发的包围盒，构建一个三维的立方体，三个轴向上分成若干个格子（Grid）。然后计算每个质点在哪个格子里，累加质量和动量到这个格子里。   
然后接着会有一步转换操作，因为对浮点型进行原子操作（这里是InterlocekdAdd）比较麻烦，所以构建速度场的时候使用了一些trick。这里会将质量转换成正确的数值并将动量转换为速度。   
然后在下一帧里，采样速度场获取格子内累计质量和平均速度，来约束质点的线速度。   
个人感觉这部分只实现了一小部分，很多方法都没实现完成，或者规划好的数据没有参与运算。默认的Groom Niagara System Asset里面也只调用了少数几个节点。   

## Visibility Buffer管线

关于为什么要用Visibility Buffer，可以看我之前的一个回答：
[Visibility Buffer有什么缺点，有可能代替G-buffer吗？](https://www.zhihu.com/question/340549627/answer/996877805)
UE4的Visibility Buffer基本上与寒霜的做法基本一致。
![FrostbiteVisibility](pic\FrostbiteVisibility.png)
![FrostbiteDeduplication](pic\FrostbiteDeduplication.png)
在原版（The Visibility Buffer: A Cache-Friendly Approach to Deferred Shading）的基础上进行了调整，加入了Deduplication。  
可以分为以下几个步骤：
1. 复制场景Opaque深度缓存到多采样的DepthTex
2. 构建多采样的IDTex和DepthTex
3. 去重复构建各种buffer并计数
4. 计算IndirectArgs
5. 构建材质属性buffer
6. 合并VisibilityDepth到场景Opaque深度缓存
7. DeferredLightPixelMain输出头发着色到mrt1
8. 合并头发rt到backbuffer

其中最终要的就是第3步：去重复构建各种buffer并计数。在每个屏幕坐标上，对子像素进行去重复，获得不同ID的数量，InterlockedAdd到CounterBuffer里。并根据单个ID出现的次数计算覆盖率（Coverage），将它和深度、头发顶点ID、材质ID保存到CompactNodeDataBuffer里，屏幕空间坐标保存到CompactNodeCoordBuffer里。此外还有两个Texture：CompactNodeIndex用来索引CompactNodeDataBuffer，CategorizationTexture保存了该屏幕坐标上头发总体的Coverage和最近的深度值。CategorizationTexture的用途可以直接看第6步的代码。
```HLSL
Texture2D<uint4> CategorisationTexture;

void MainPS(
	in FScreenVertexOutput Input,
	out float SvDepth		: SV_Depth,
	out float4  OutGBufferB	: SV_Target0,
	out float4 OutColor		: SV_Target1
)
{
	const FCategorizationData CategorisationData = DecodeCategorizationData(CategorisationTexture.Load(uint3(Input.Position.xy, 0)));
	if (CategorisationData.PixelCoverage < 1.0f)
	{
		discard;
	}

	SvDepth = CategorisationData.ClosestDepth;
	OutGBufferB = 0;
	OutColor = 0;
}
```
而第5步相当于生成GBuffer的过程，只不过是把各种属性保存在一个NodeDataBuffer里。   

可能因为是Experimental的缘故，这部分实现其实有些一言难尽。尤其是第5步，居然用VS和PS来模拟CS，看的我是一脸懵逼，亏你还在第4步计算了IndirectArgs，写个Compute能有多难。   
另外还有一些可以优化的点：
* 可以预先计算头发屏幕空间的AABB，用这个AABB计算一个IndirectArgs，用于第3步的Dispatch，这样大部分情况下Dispatch数量可以减少很多。（其他一些全屏的Pass也可以考虑这样优化）
* 在构建Visibility Buffer之前可以用场景的Depth先做一步HiZ Culling。
* 因为预先不知道去重复的id有多少，所以显存只能饱和式申请，CompactNodeDataBuffer和NodeDataBuffer的成员数量是Resolution.x\*Resolution.y\*MSAACount，显存分分钟爆炸（其实还好），然而我并没有发现ompactNodeDataBuffer有什么存在的必要，去重复的时候，完全可以把数据保存到NodeDataBuffer里。   
* 另外还有一些迷之转换，来回Encode和Decode，很多可以去掉。

## BSDF
说到头发的BSDF，就不得不祭出这张图
![Marschner](pic\Marschner.png)
目前主流的pbr的头发光照模型都是基于Marschner模型上的改进（你说什么？KajiyaKay？对不起，没戴眼镜听不见！）
Marschner创造性的将头发的光照分成了三个路径：
1. R：反射
2. TT：透射
3. TRT：内反射（透射、内壁反射、透射）   

然后将每个部分的散射函数有分为M和N。
![MarschnerMN](pic\MarschnerMN.png)
M表示纵向上的散射函数，只考虑lobe的分布。
N表示方位角（截面）上的散射函数，需要计算菲涅尔、吸收率和折射率。   
虚幻曾在Siggraph 2016上做过演讲（Physically Based Hair Shading in Unreal），简化了TT和TRT的N函数，TT做了一些近似，而TRT基本上就是差不多就行。   
寒霜在Siggraph 2019上，拿虚幻的这篇演讲作对比，做了一些改进，使用了预积分的方法来近似TT，而TRT……依旧是差不多就行（加了一个与粗糙度相关的系数做控制）。   
但是UE4坚守最后的倔强，还是坚持使用自己那套光照模型（虽然做了一些调整，但似乎跟寒霜的PPT没有关系）。   
具体细节，各位同学可以看两篇PPT（或者等我哪天总结一下Marschner）。

## Deep Opacity Maps和Dual Scattering
![DeepOpacity](pic\DeepOpacity.png)
Deep Opacity Maps的原理与Opacity Shadow Maps有些类似，不过它不是线性的分层，而是根据一张Front Depth Texture来分层，统计每层前面有多少头发。
与Opacity Shadow Maps或Deep Shadow Maps不同的是，这里Deep Opacity Maps实际上是Dual Scattering的一部分Global Scattering。UE4并没有听取原文（（Dual Scattering Approximation for Fast Multiple Scattering in Hair））的建议，将T<sub>f</sub>（沿着光照方向上的透射值）和$\sigma$<sub>f</sub>（沿着光照方向上的发散系数）累积到texture里，只是保存了头发的数量。计算光照的时候，采样一张3D Lut，获得A<sub>f</sub>（透射值除以密度系数常量），pow(A<sub>f</sub>, HairCount - 1)来获得光照穿过数层头发后的衰减值。做了一个很粗糙的近似，不过看起来效果还可以。   
而关于Local Scattering，也是在计算光照的时候采样3D Lut，获得A<sub>f</sub>、A<sub>b</sub>，然后带入到相关公式中计算。有兴趣的同学可以看原论文，这里不做赘述。而这张3D Lut是通过预积分头发的BSDF得到的。   

## 环境光和AO
如果有同学导入Groom资源，发现UE4有些卡，那么，关闭HairStrands.SkyLighting和HairStrands.SkyAO（或者降低SkyLighting.SampleCount和SkyAO.SampleCount），我相信应该可以解决大部分问题。   
因为里面用了Monte Carlo+Ray Marching！！！！
![GoDie](pic/GoDie.png)
在此之前需要构建一个头发密度的体素，随机数个（默认值16）光照方向在体素里进行ray marching计算头发数量，接着计算双重散射（环境光）、遮蔽（AO），最后做平均。环境光还需要计算R（和TRT一起计算）和TT（采样一张预积分的3D Lut），这两部分也需要做一次Ray Marching（TT可以不做，但是需要构建一张ViewHairCountTexture）。   
（AO算了个BendNormal丢在那里也不用……）    
前面说了Visibility Buffer的优化，其实也就是小打小闹，真的想实装UE4的Groom，我觉得还是需要Trick一下环境光和AO。
![Trick](pic/Trick.jpg)