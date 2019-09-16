# 前言

上篇文章[屏幕空间深度阴影贴图（Screen Space Deep Shadow Maps）](https://zhuanlan.zhihu.com/p/79062045)留了个错误，实际上，屏幕空间结算的Deep Shadowmaps完全可以直接用到半透明物体上。

根据混合公式，对于屏幕上一个像素点

<img src=https://www.zhihu.com/equation?tex=%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7BL_%7Bl%7D%5Ccdot%20%5Calpha_%7Bl%7D%20%5Ccdot%20%5Cprod_%7Bk%3D0%2C%20z_%7Bk%7D%3Cz_%7Bl%7D%7D%5E%7Bb%7D%20(1-%5Calpha_%7Bk%7D)%7D&preview=true>

因为结算阴影也是在屏幕空间，所以，对于屏幕上一个像素点来说，它是一个定值，完全可以从公式中提取出来，无所谓混合了几层。对于（粒子）烟雾来讲，排序之后，按照由远及近的方式进行渲染，可以在frag里直接采样SSDSM的Lut，使阴影参与着色。

然而，对于我来说，这还没有完，因为我要做的是头发，一般是复杂的几何模型（例如小卷发），模型本身不是闭合的，甚至会有自相交，这种情况就无法使用排序（除非片元级排序）来解决半透明着色问题。为了解决这个问题，本文使用了基于矩的顺序无关半透明渲染（Moment-Based Order-Independent Transparency）。

此外，本文还将阐述，如何将Screen Space Deep Shadowmaps与之融合。

# 问题

首先我们看一下问题是什么：

![problem](https://github.com/ecidevilin/Blogs/blob/master/Misc/MOIT/pic/problem.png?raw=true) 

直接使用默认方式进行半透明渲染，出现了很明显的错误。

为什么会出现这种问题？

还是上面那个公式：

<img src=https://www.zhihu.com/equation?tex=%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7BL_%7Bl%7D%5Ccdot%20%5Calpha_%7Bl%7D%20%5Ccdot%20%5Cprod_%7Bk%3D0%2C%20z_%7Bk%7D%3Cz_%7Bl%7D%7D%5E%7Bb%7D%20(1-%5Calpha_%7Bk%7D)%7D&preview=true>

观察这个公式，我们就会发现：在进行半透明渲染的时候，我们无法知道同一屏幕坐标上，哪些片元的深度值小于当前片元。所以在没有排序的情况下，直接使用默认混合方式进行Alpha混合，结果就会出错。

那么如何解决这个问题？其实完全可以参考Deep Shadow Maps的做法，使用链表来对片元进行排序。这对我来说没什么难度，不过我想搞点新东西，所以，考虑使用Moment-Based Order-Independent Transparency（引用文献1）。


# 基于矩的顺序无关半透明渲染

关于矩和广义矩估计，感兴趣的同学可以看参考文献8和9，这里不做详述（实际上是因为还没有完全理解清楚）。

我们先看看效果：

![moit](https://github.com/ecidevilin/Blogs/blob/master/Misc/MOIT/pic/moit.png?raw=true) 


## 渲染不透明物体

首先，我们还是按照常规的顺序，将不透明物体绘制出来。

## 使用矩来表示吸收率

先跳过前面的公式推导部分，我们看看我们需要计算什么：

<img src=https://www.zhihu.com/equation?tex=%7B-ln(1-%5Calpha_l)%20%5Ccdot%20%5Cpmb%7Bb%7D(z_l)%7D&preview=true>

对于每个片元，我们需要计算上面公式的值，然后使用Blend One One的方式将它们累加到render targets里，即：

<img src=https://www.zhihu.com/equation?tex=b%3D%5Cvarepsilon_z(%5Cpmb%7Bb%7D)%3D%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7B-ln(1-%5Calpha_l)%20%5Ccdot%20%5Cpmb%7Bb%7D(z_l)%7D&preview=true>

那么问题来了，**b**是什么？**b**实际上是一个向量：

<img src=https://www.zhihu.com/equation?tex=%5Cpmb%7Bb%7D(z)%3D(1%2Cz%2Cz%5E2%2C...%2Cz%5Em)%5ET&preview=true>

这是一个m+1维的矩，z是当前片元的深度。它反映了一个脉冲函数δ的分布情况，脉冲函数δ的定义为：

<img src=https://www.zhihu.com/equation?tex=%5Cdelta_%7Bz_l%7D%3D%5Cbegin%7Bcases%7D%201%26z_l%20%3C%20z_f%20%5C%5C%200%20%26%20otherwise%20%5Cend%7Bcases%7D&preview=true>

那么这个脉冲函数δ是做什么的呢？


回想最开始的公式，我们把透射率T提取出来，它表示了在某个深度上的光照衰减值：

<img src=https://www.zhihu.com/equation?tex=T(z_%7Bf%7D)%3D%5Cprod_%7Bl%3D0%2Cz_%7Bl%7D%3Cz_%7Bf%7D%7D%5E%7Bn-1%7D(1-%5Calpha_%7Bl%7D)&preview=true>

然后我们使用对数函数，把累乘转换成累加，并定义吸收率函数：

<img src=https://www.zhihu.com/equation?tex=A(z_%7Bf%7D)%3D-lnT(z_%7Bf%7D)%3D%5Csum_%7Bl%3D0%2Cz_%7Bl%7D%3Cz_%7Bf%7D%7D%5E%7Bn-1%7D-ln(1-%5Calpha_%7Bl%7D)&preview=true>


根据前面脉冲函数δ的定义，吸收率函数A就可以认为是一个有限估计的累积分布函数

<img src=https://www.zhihu.com/equation?tex=Z%3D%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7B-ln(1-%5Calpha_l)%5Ccdot%5Cdelta_%7Bz_l%7D%7D&preview=true>

我们无法直接将这个函数保存起来，于是，我们按照前面提到的方式就通过矩将它存起来，并在下一步里面，构建它的近似函数。


## 重建透射率

假设我们已经获得了吸收率的近似函数A，那么我们就可以根据它来重建透射率：

<img src=https://www.zhihu.com/equation?tex=T(z_f%2Cb%2C%5Cbeta)%3Dexp(-A(z_f%2Cb%2C%5Cbeta))&preview=true>

其中β为overestimation，原文建议值为0.25。

然后我们根据下面的公式，重新对半透明的物体进行渲染，并将他们存到一个离屏（off-screen）render target里面

<img src=https://www.zhihu.com/equation?tex=%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7BL_l%20%5Ccdot%20%5Calpha_l%20%5Ccdot%20T(z_f%2Cb%2C%5Cbeta)%7D&preview=true>

也就是说，我们重新渲染半透明物体，对于每个片元，用他们的颜色(L<sub>l</sub>)乘以不透明度和透射率，使用Blend One One的方式将它们累加起来。那么α通道里面存的是什么？

<img src=https://www.zhihu.com/equation?tex=%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7B%5Calpha_l%5Ccdot%20T(z_f%2Cb%2C%5Cbeta)%7D&preview=true>

为了在合并阶段方便计算，所以将它保存到α通道里。


## Warping Depth（没有找到合适的翻译）

这一部分很简单，就是提高z的精度，对深度值进行了重新计算。


## 合并

这一步，我们要将半透明的render target和不透明的render target进行合并，也就是blit。

前面提到矩中，第0个矩保存了像素坐标上总体的吸收率：

<img src=https://www.zhihu.com/equation?tex=b_0%3D%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7B-ln(1-%5Calpha_l)%7D&preview=true>

所以，exp(-b<sub>0</sub>)为当前屏幕坐标上，总体的透射率，它被单独存到一个render target里面，方便这一步进行计算。

那么这一步里，我们就可以根据它来合并：

<img src=https://www.zhihu.com/equation?tex=exp(-b_0)%20%5Ccdot%20L_n%2B%5Cfrac%7B1-exp(-b_0)%7D%7B%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7B%5Calpha_l%5Ccdot%20T(z_f%2Cb%2C%5Cbeta)%7D%7D%5Ccdot%5Csum_%7Bl%3D0%7D%5E%7Bn-1%7D%7BL_l%5Ccdot%20%5Calpha_l%20%5Ccdot%20T(z_f%2Cb%2C%5Cbeta)%7D&preview=true>

分母的部分用来做归一化，来近似达到能量守恒的目的，而这个值已经在**重建透射率**这一步保存到半透明render target的α通道里，所以直接用rgb通道的值除以它，然后用Blend OneMinusSrcAlpha SrcAlpha的方式（α通道为exp(-b<sub>0</sub>)）Blit到不透明render target上。


# 幂矩

说了那么多，大家或许发现了，前面略过了最重要的一个部分，那就是如何获得吸收率的近似函数A。

之前提到了**b**是一个m+1维的矩：

<img src=https://www.zhihu.com/equation?tex=%5Cpmb%7Bb%7D(z)%3D(1%2Cz%2Cz%5E2%2C...%2Cz%5Em)%5ET&preview=true>

原文中使用了4维、6维、8维幂矩和2维、3维、4维三角矩（Trigonometric Moments），三角矩的效果有点辣眼睛，所以本文略过不提，只是简单介绍一下如何使用幂矩求解。另外，4维、6维和8维在求解方法上区别不大（8维需要求解4次多项式，比前二者更为复杂），所以本文以4维幂矩求解为例。

## Cholesky分解

<img src=https://www.zhihu.com/equation?tex=%5Cleft(%5Cbegin%7Bmatrix%7Db_0%20%26%20b_1%20%26%20b_2%20%5C%5C%20b_1%20%26%20b_2%20%26%20b_3%20%5C%5C%20b2%20%26%20b3%20%26%20b4%5Cend%7Bmatrix%7D%5Cright)%20%5Ccdot%20%5Cleft(%5Cbegin%7Bmatrix%7Dq_0%20%5C%5C%20q_1%20%5C%5Cq_2%5Cend%7Bmatrix%7D%5Cright)%3D%5Cleft(%5Cbegin%7Bmatrix%7D1%20%5C%5C%20z_f%5E1%20%5C%5C%20z_f%5E2%5Cend%7Bmatrix%7D%5Cright)&preview=true>

首先我们需要求解上式中的q向量(z<sub>f</sub>为当前片元的Warping深度)，这里用到了Cholesky分解法。

<img src=https://www.zhihu.com/equation?tex=A%3DLDL%5ET%3D%5Cleft(%5Cbegin%7Bmatrix%7D1%260%260%5C%5C%20L_%7B10%7D%20%26%201%20%260%20%5C%5C%20L_%7B20%7D%20%26%20L_%7B21%7D%20%26%201%5Cend%7Bmatrix%7D%5Cright)%5Cleft(%5Cbegin%7Bmatrix%7DD_0%260%260%5C%5C0%26D_1%260%5C%5C0%260%26D_2%5Cend%7Bmatrix%7D%5Cright)%5Cleft(%5Cbegin%7Bmatrix%7D1%26L_%7B10%7D%26L_%7B20%7D%5C%5C0%261%26L_%7B21%7D%5C%5C0%260%261%5Cend%7Bmatrix%7D%5Cright)&preview=true>

分解之后，求解难度大幅简化。

## 构建脉冲分布函数

然后求解多项式：

<img src=https://www.zhihu.com/equation?tex=q_2%5Ccdot%20z%5E2%2Bq_1%20%5Ccdot%20z%20%2B%20q_0%20%3D%200&preview=true>

得到z<sub>1</sub>和z<sub>2</sub>，构建脉冲分布函数。如果z<sub>l</sub>小于z<sub>f</sub>，则v<sub>l</sub>等于1，否则为0。

## Vandermonde矩阵

接着，求解Vandermonde矩阵

<img src=https://www.zhihu.com/equation?tex=%5Cleft(%5Cbegin%7Bmatrix%7D1%20%26%20z_f%20%26%20z_f%5E2%20%5C%5C%201%20%26%20z_1%20%26%20z_1%5E2%20%5C%5C%201%26z_2%26z_2%5E2%5Cend%7Bmatrix%7D%5Cright)%5Ccdot%5Cleft(%5Cbegin%7Bmatrix%7Du_0%5C%5Cu_1%5C%5Cu_2%5Cend%7Bmatrix%7D%5Cright)%3D%5Cleft(%5Cbegin%7Bmatrix%7Dv_0%5C%5Cv_1%5C%5Cv_2%5Cend%7Bmatrix%7D%5Cright)&preview=true>

其中v<sub>0</sub>为overestimation，原文建议值为0.25。求得权重值u<sub>0</sub>、u<sub>1</sub>和u<sub>2</sub>。

## 重建吸收率

<img src=https://www.zhihu.com/equation?tex=%5Csum_%7Bj%3D0%7D%5E%7B%5Cfrac%7Bm%7D%7B2%7D%7D%7Bb_j%5Ccdot%20u_j%7D&preview=true>

通过上式重建吸收率A，而透射率等于exp(-A)。


# 融合阴影

按照文首的结论，这一步原理很简单，只需要在上面**重建透射率**的步骤里将阴影值加入着色（光照）计算即可，但实际上还是有点麻烦，因为Screen Space Deep Shadowmaps需要相机深度图，而且需要半透明物体的深度，我又不希望半透明物体的深度污染不透明物体的深度，所以需要一张单独的render target。在深度预渲染之后，将Depth Texture复制一份为OIT Depth Texture，然后将半透明物体的深度绘制到上面。而Screen Space Deep Shadowmaps结算阶段，也改为采样这张RT。

效果如图：


![moit_ssdsm](https://github.com/ecidevilin/Blogs/blob/master/Misc/MOIT/pic/moit_ssdsm.png?raw=true) 


完整实现我已经放到了我的github上：

![https://github.com/ecidevilin/KhaosLWRP](https://github.com/ecidevilin/KhaosLWRP)




# 参考文献

1. Moment-Based Order-Independent Transparency
2. Moment Shadow Mapping
3. Improved Moment Shadow Maps for Translucent Occluders, Soft Shadows and Single Scattering
4. Moment-Based Methods for Real-Time Shadows and Fast Transient Imaging
5. Solving trigonometric moment problems for fast transient imaging
6. Non-linearly Quantized Moment Shadow Maps
7. Introduction to Probability 
8. [概率论中「矩」（moment）的实际含义是什么，高阶矩表示数据的哪些状态？ - 荆哲的回答 - 知乎](https://www.zhihu.com/question/23236070/answer/143316942)
9. [如何用简单的例子解释什么是 Generalized Method of Moments (GMM)？ - 慧航的回答 - 知乎](https://www.zhihu.com/question/41312883/answer/91484566)
10. [Web端的实时透明渲染算法](https://zhuanlan.zhihu.com/p/49164063)
