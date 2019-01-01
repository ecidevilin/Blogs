# Compute Shader : Optimize your game using compute

# ![](Pics/icon.png)

本文章标题来源于来源于AMD在4C上的一个演讲：
Compute Shaders: Optimize your engine using compute <sup>[3]</sup>


---
## 概念
Compute Shader是在GPU上运行的程序。虽然是老生常谈了，但是我们还是要先介绍一下GPU。
众所周知，CPU和GPU是两种不同的架构，那么他们之间的区别是什么？[1]


### CPU是基于低延迟的设计
![](Pics/CPU_Design.png)


CPU有很强大算术逻辑单元，减少操作延迟；巨大的cache，内存访问延迟大，空间换时间复杂的控制器，使用分支预测来减少分支延迟，使用数据转发减少数据延迟。
CPU擅长逻辑控制和串行的运算。<sup>[1]</sup>


### GPU是基于大吞吐量的设计
![](Pics/GPU_Design.png)
GPU有小的cache，用来促进吞吐量；简单的控制，没有分支预测和数据转发；高效节能的ALU，很多延迟很长的ALU，但是为了高吞吐量被重度管线化；需要开启大量的线程才能降低延迟。
GPU适用于计算密集型和易于并发的程序。<sup>[1][2]</sup>


### GPGPU

![](Pics/GPGPU.jpg)
可以看出，CPU和GPU各有自己的擅长，那么我们可以将二者结合起来，使用CPU做串行，而使用GPU做并行。<sup>[1]</sup>这种技术就叫做GPGPU，也就是利用GPU进行通用计算的技术（General Purpose Computing on GPU）。
但是，我们知道，通常来讲，GPU是用来执行图形渲染的。那么，为了执行通用计算，NV推出了CUDA，Khronos推出了OpenCL，Microsoft推出了DirectCompute，也就是后来的Compute Shader，然后，各种图形API也相继推出了CS。<sup>[25]</sup>


### 支持Compute Shader的图形API
![](Pics/DirectX10.jpg) ![](Pics/DirectX11.jpg) ![](Pics/DirectX12.jpg)
![4.3](Pics/OpenGL.png) ![3.1](Pics/OpenGLES.png)
![](Pics/Metal.png) ![](Pics/Vulkan.png)
DX虽然从10开始支持Compute Shader/Direct Compute，但是限制比较大。DX11支持了更强大的Compute Shader，当然肯定还有DX12<sup>[6]</sup>。所以我们一般在Unity中使用CS，还是要求shader target4.5（也就是shader model 5）<sup>[19]</sup>。
OpenGL从4.3开始支持CS，但是MacOSX不支持4.3ES从3.1开始支持CS。<sup>[5]</sup>
Metal和Vulkan都支持CS<sup>[4][7]</sup>。
另外PS4和Xbox one（DX11.2）也支持CS<sup>[19]</sup>。


### Compute管线与图形管线的对比
![](Pics/CompareToGraphics.png)

我们可以看到，计算管线变得很简单<sup>[3]</sup>。
（关于GPU Rendering Pipeline，可以参考这张图 https://github.com/ecidevilin/Blogs/blob/master/IntroTo3DGPWithDX/Tessellation/pic/pipeline.jpg）<sup>[14]</sup>


### 图形管线（硬件端）
![](Pics/GraphicsPipeline.png)


### 计算管线（硬件端）
![](Pics/ComputePipeline.png)
上图是计算管线在硬件端的工作流程<sup>[3]</sup>。

Compute Shader可以在不通过渲染管线的情况下，利用GPU完成一些与图像渲染不直接相关的工作。这样就可以降低硬件的overhead。

---
## 语法
### 如何在Unity里使用Compute Shader？
上文中，介绍了，有很多图形API支持CS，但是各种API的shading language语法和API各不相同。
Unity的ShaderLab采用了跟HLSL接近的API，方便我们编写shader。


### kernel
如果我们在Unity里面新建一个CS，便是如下的代码（稍作修改）。
``` ShaderLab
// test.compute
#pragma kernel FillWithRed // 1

RWTexture2D<float4> res;   // 2

[numthreads(8,8,1)]       // 3
void FillWithRed (uint3 dtid : SV_DispatchThreadID) // 4
{
    res[dtid.xy] = float4(1,0,0,1);                 // 5
}

```
这是一个简单的Compute Shader示例，将一个RT填充成红色。
1. 首先声明了一个Kernel，Kernel相当于一个main函数，是CS的入口。这应该是来源于Metal的思路<sup>[7]</sup>，可以在一个资源文件里定义不同的kernel方法，公用一些代码，同时也可以做到相对独立。
2. 然后声明了一个RWTexture2D，对应于C#，是RenderTexture。
3. 在函数名上面还有一个numthreads的attribute，这个我们后面会讲到。
4. 函数的参数后面带有一个Semantic（SV_DispatchThreadID），这个我们后面也会讲到。我们暂时可以把它当作一个坐标值。
5. 最后是函数体，是将rt中的像素设置成红色。



### Dispatch
如何执行这样一个CS代码？在C#里，调用如下代码。
``` C#
public void Dispatch(int kernelIndex,
	int threadGroupsX,
	int threadGroupsY,
    int threadGroupsZ);
```
在CPU端，我们可以通过这个接口，将CS dispatch出去。Dispatch就相当于Drawcall，但是没有draw。
其中kernelIndex可以通过ComputeShader.FindKernel来获取。而threadGroupsXYZ代表线程组的数量。
那么什么又是线程组？


### numthreads
![](Pics/ThreadGroups.png)


在CS里面，线程可以分为三个维度。<sup>[2]</sup>上图中，最右边的表示单个线程，最左边的表示一个dispatch，而图中间的，表示一个Thread Group。
thread group是指将多个线程组合成为一个group，在这个group里面，每个线程有自己的相对位置。group内，还可以使用共享变量，相互通信。
将numthreads这个attribute声明在kernel函数的前面，就表示一个thread group中有多少个thread。
如图所示一个Dispatch中有3x2x3个thread groups，而一个group中有4x4x2个thread。
这样做的好处一个是可以利用gpu的warp/wavefront/EU-thread<sup>[2][3]</sup>。另外，举个例子，现在很多图像压缩算法都是基于block的，而thread group（OpenGL里叫做local size）可以为图像数据的一个block的大小（例如8x8）,group数量可以是图像的尺寸除以块的尺寸。每个块被当作一个单独的work group来处理，并且group内可以共享一些信息<sup>[5]</sup>。



### thread groups
更进一步的，我们可以看下图<sup>[6]</sup>。
<img src=Pics/threadgroupids.png height=540/>
上半图代表了一个5x3x2的dispatch，图中的坐标代表一个thread group。
接着，将2,1,0的thread group打开，我们可以看到下半图。这张图代表了一个10x8x3的thread group，图中的坐标代表了一个thread。
如图所示，我们可以根据这些坐标算出GroupThreadID，GroupID，DispatchThreadID和GroupIndex。
这些id一般是用来作为索引来获取Buffer、Texture或者thread group shared memory里的数据，例如上面举的例子，GroupThreadID就是图像的block内的坐标，GroupID是图像按块划分的坐标（图像的尺寸除以块的尺寸），而DispatchThreadID是像素的坐标。


### Buffer & Texture
CS可以使用一些常规的类型，标量、向量、矩阵、纹理、数组等。除此之外，为了更灵活的使用CS，还推出了StructuredBuffer，简称SBuffer。
| GPU Side | CPU Side |
|-----|-----|
|\*StructuredBuffer|ComputeBuffer|
|RWTexture\*D|RenderTexture|
（SBuffer在fs里也可以使用，在其他shader里也可能可以使用。）
StructuredBuffer还包括
- RWStructuredBuffer
- RWStructuredBuffer with counter
- (RW)ByteAddressBuffer
- AppendStructuredBuffer
- ConsumeStructuredBuffer
StructuredBuffer除了可以包含各种内置的类型之外，还可以包含自定义的struct。

### groupshared

使用groupshared可以将一个变量标记为组内共享（又叫TGSM<sup>[2]</sup>）。
使用这种变量，就可以在thread group内进行通讯。
例如，我们可以在forward+/Deferred管线里使用compute shader对点光源进行剔除。
这个是在战地3中使用的技术<sup>[16][21]</sup>。

### Barrier
当我们在不同线程访问同一个资源的时候，我们需要使用barrier来进行阻塞和同步。
分为以下两种。
```
GroupMemoryBarrier 
DeviceMemoryBarrier
AllMemoryBarrier 
```
```
DeviceMemoryBarrierWithGroupSync 
GroupMemoryBarrierWithGroupSync  
AllMemoryBarrierWithGroupSync
```

GroupMemoryBarrier是等待对groupshared变量的访问。
DeviceMemoryBarrier是等待对texture或buffer的访问。
AllMemoryBarrier是以上两者的和。
\*WithGroupSync版本是需要同步到当前指令


### Interlocked
原子操作，不会被线程调度机制打断。
```
InterlockedAdd
InterlockedAnd
InterlockedCompareExchange
InterlockedCompareStore
InterlockedExchange
InterlockedMax
InterlockedMin
InterlockedOr
InterlockedXor
```
*但是只能用于int/uint*
例如可以用于计算灰度直方图，用于Tonemapping\Auto Exposure等效果<sup>[19]</sup>。


### 平台差异
虽然Unity帮我们做了跨平台的工作，但是我们仍然需要面对一些平台差异。
1. **数组越界**，DX上会返回0，其它平台会出错。
2. 变量名与关键字/内置库函数**重名**，DX无影响，其他平台会出错。
3. 如果SBuffer内结构的显存布局要与**内存布局不一致**，DX可能会转换，其他平台会出错。
4. **未初始化**的SBuffer或Texture，在某些平台上会全部是0，但是另外一些可能是任意值，甚至是NaN。
5. Metal不支持**对纹理的原子操作**，不支持对SBuffer调用**GetDimensions**。
6. ES 3.1在一个CS里**至少支持4个SBuffer**（所以，我们需要将相关联的数据定义为struct）。
7. 在渲染管线中，部分号称支持es3.1+的Android手机**只支持在片元着色器内访问StructuredBuffer**。

### 性能优化
另外，在使用CS的时候，我们还需要知道一些性能优化点。
1. 尽量减少Group之间的交互：硬件不支持全局同步<sup>[2]</sup>，不同步的话容易导致错误和崩溃<sup>[3]</sup>。
2. GPU一次Dispatch会调用64（AMD成为wavefront）或32（NVIDIA称为warp）个线程（这实际上是一宗SIMD技术），所以，numthreads的乘积最好是这个值的整数倍。但是Mali不需要这种优化<sup>[8]</sup>。此外，Metal可以通过api获取这个值<sup>[7]</sup>。
3. 避免回读：回读操作在渲染管线中使用的比较少，而在CS中可能会被用到，所以重点提一下<sup>[20]</sup>。
4. 避免分支，重点避免在thread group中间的分支，这其实跟第二点是相关的，如果在wavefront/warp蒸熟倍的地方发生分支，消耗就会小很多<sup>[2][26]</sup>。
5. 尽量保证内存连续性<sup>[2]</sup>。
6. 使用[unroll]来打开循环，有些时候需要手动unroll<sup>[22]</sup>。
还有一些在渲染管线中适用的tips这里没有列举出来。

---
## 应用
那么介绍过CS之后，我们看看，目前都有哪些应用。

### GPU Particle System
<img src=Pics/GPUParticles.png height=540>
图为用CS实现的GPU粒子系统，这个功能中使用CS计算粒子的运动轨迹<sup>[10]</sup>。

### GPU Simulation
![](Pics/GPUCloth.png)
图为布料模拟，使用了CS进行布料粒子的受力运动计算、碰撞检测和反馈，以及约束计算。类似的还有头发模拟和海水模拟<sup>[11]</sup>。

### Image Processing
![](Pics/cs_filters.jpg)
图为一个简单的去色的图像处理<sup>[12]</sup>，将rgb与(0.299,0.587,0.114)进行dot，获得灰度值<sup>[24]</sup>。类似的还有eye adaptation, color grading等等[3]，Unity的PPS2中使用的histogram就是一个很好的例子，几乎用到了CS的所有feature<sup>[23]</sup>。

### Image Compression
![](Pics/ImageCompression.png)
图为ASTC算法压缩过的图像（4x4 6x6 8x8）<sup>[13]</sup>。
上面提到过，我们可以使用CS来实现基于Block的纹理压缩算法。


### Tessellation
![](Pics/tessellation.jpg)
曲面细分<sup>[15]</sup>：默认管线中的Tessellation比较受限，虽然可以使用Displacement mapping来提升它的效果，但是仍然不够动态。
我们配合CS一起使用，我们可以配合一些逻辑更自由更动态的生成细分顶点<sup>[14][3]</sup>。

### Local lights culling
![](Pics/battlefield3.jpg)

战地3中，使用的是Deffered shading pipeline，通过cs对点光源、探照灯等光源进行剔除<sup>[16]</sup>。

### Occlusion culling
![](Pics/HizOcc.jpg)

图片来源，知乎大V MaxwellGeng实现的GPU Occlusiong Culling，他使用了Hiz的方法，对cluster进行遮挡剔除<sup>[17]</sup>。
而这种思想就是GPUDRP。


### GPU Driven Rendering Pipeline
![](Pics/GPUDRP.jpg)

图为刺客信条大革命，在这部游戏中使用了GPUDRP技术，并在Siggraph 2015: Advances in Real-Time Rendering in Games course中发表<sup>[18]</sup>。

### 还有很多很多……

### Simple, but not easy.
![bg](Pics/future.jpg)
“Simple, but not easy”是我对Compute Shader的认识，也是对本文的总结。
ES从3.1开始支持CS，也就是说，在手机上的支持率并不是很高。
另外，手机算力还是很低。GTX 1050 Ti的算力是1.9k~2.9k Gflops（floating point operations per second），有768个core。华为P20的Mali-G72 MP12的算力是300+ Gflops，只有12个core<sup>[28]</sup>。
所以，CS在手机上的使用，是困难的，但是有巨大潜力的。

---
## 引用
1. [Graphic Processing Processors (GPUs) Parallel Programming](https://slideplayer.com/slide/9636742/)
2. [DirectCompute
Optimizations and Best Practices](http://on-demand.gputechconf.com/gtc/2010/presentations/S12312-DirectCompute-Pre-Conference-Tutorial.pdf)
3. [Compute Shaders: Optimize your engine using compute / Lou Kramer, AMD (video)](https://www.youtube.com/watch?v=0DLOJPSxJEg)
4. [Introduction to Compute Shaders in Vulkan](https://arm-software.github.io/vulkan-sdk/basic_compute.html)
5. [Compute Shader(OpenGL)](https://www.khronos.org/opengl/wiki/Compute_Shader)
6. [Compute Shader Overview(Direct3D 11)](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/direct3d-11-advanced-stages-compute-shader)
7. [About Threads and Threadgroups(Metal)](https://developer.apple.com/documentation/metal/about_threads_and_threadgroups)
8. [ARM® Mali™ GPU OpenCL Developer Guide(Version 3.2)](https://static.docs.arm.com/100614/0302/arm_mali_gpu_opencl_developer_guide_100614_0302_00_en.pdf)
9. Real-Time Rendering 3rd Edition. Chapter 18
10. [GPU Particles (Github)](https://github.com/Robert-K/gpu-particles)
11. [GPU Cloth Tool](https://www.shpakivnia.com/cloth-tool)
12. [Compute Shader Filters](http://www.codinglabs.net/tutorial_compute_shaders_filters.aspx)
13. [Adaptive Scalable Texture Compression](https://en.wikipedia.org/wiki/Adaptive_Scalable_Texture_Compression)
14. Introduction to 3D Game Programming with DirectX 11
15. [DirectX 11 Tessellation (NVIDIA)](https://www.nvidia.com/object/tessellation.html)
16. [DirectX 11 Rendering in Battlefield 3](https://www.slideshare.net/DICEStudio/directx-11-rendering-in-battlefield-3)
17. [Hi-Z GPU Occlusion Culling](https://zhuanlan.zhihu.com/p/47615677)
18. [GPU-Driven Rendering Pipelines](http://advances.realtimerendering.com/s2015/aaltonenhaar_siggraph2015_combined_final_footer_220dpi.pdf)
19. https://docs.unity3d.com
20. [Problems with ComputeBuffer Readback](https://forum.unity.com/threads/compute-shaders.148874/#post-1021917)
21. [Volume Tiled Forward Shading (Github)](https://github.com/jpvanoosten/VolumeTiledForwardShading)
22. Low-level Shader Optimization for Next-Gen and DX11 [(ppt)](http://www.humus.name/Articles/Persson_LowlevelShaderOptimization.pptx) [(video)](https://www.gdcvault.com/play/1020352/Low-Level-Shader-Optimization-for)
23. [Post-processing Stack v2 (Github)](https://github.com/Unity-Technologies/PostProcessing)
24. 数字图像处理（冈萨雷斯）
25. [General-purpose computing on graphics processing units (Wikipedia)](https://en.wikipedia.org/wiki/General-purpose_computing_on_graphics_processing_units)
26.  全局光照技术：从离线到实时渲染
27.  [Mythbusters Demo GPU versus CPU ( NVIDIA )](http://v.youku.com/v_show/id_XNjY3MTY4NjAw.html)
28.  [Glops](https://gflops.surge.sh/)