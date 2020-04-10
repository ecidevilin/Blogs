# UE4.24 Hair Strands
UE4.24推出了次世代发丝（Hair Strands）系统Groom，实现大量参考了寒霜在Siggraph2019 Advances in Real-Time Rendering in Games course上的演讲。
[Strand-based Hair Rendering in Frostbite]("http://advances.realtimerendering.com/s2019/hair_presentation_final.pptx")   
在写这篇文章的时候，UE4.25已经出preview版本了，但是preview版本更新过于频繁，本文暂时还是以4.24.3来作为基础。  
UE4的实现主要分为以下三个部分：
* 基于Niagara实现的物理模拟
* Visibility Buffer管线
* 发丝的BSDF着色

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

