**本文首发自我的简书，原文地址：https://www.jianshu.com/p/27dbffe16631**

# 什么是矩阵

翻翻教科书，我们可以看到关于矩阵的描述是：

由m行n列数放在一起组成的数学对象。

![矩阵](http://upload-images.jianshu.io/upload_images/10172014-4e2d41da01fd2caf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



简单而直观，但是对于我们理解矩阵似乎并没有什么帮助。
那么我们需要先从向量说起。（根据OpenGL的规定，我们这里使用的是列向量）
## 向量
什么是向量，（列）向量其实是列数为1的矩阵。
![列向量](http://upload-images.jianshu.io/upload_images/10172014-e30dcbd6dcced395.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
或者写成
![列向量](http://upload-images.jianshu.io/upload_images/10172014-9a6f6a1e413d1279.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
向量的几何意义是空间中A点和B点二者的差值，即B点到A点的方向与距离（向量的模）。它描述了空间中点与点之间的关系。
此外，我们都知道，空间中的点也可以用N个数字来（N为空间的维度，例如N=3）表示。
但是，这就有了一个问题：在一个空间中，我们将不同维度的N个值称为一个对象，这些对象可以全部用来表示向量，也可以全部用来表示点，但是如果二者混用（即同一空间中的对象即表示点又表示向量）就会产生歧义。
点和向量是两个非常相近但是又很不一样的两个概念，在不引起歧义的情况下，我们确实可以在某些情况下用N个数表示一个点，也可以在另外某些情况下同样用N个数表示一个向量。但是，总会有一些特殊的情况下，我们需要同时要表示点和向量，于是我们就不得不去面对上面的歧义问题。
这里我们就需要引入一个概念：仿射空间。
## 仿射空间
仿射空间其实是一种特殊的齐次空间（后面会讲到齐次空间）。在这个空间里，用N+1维向量来表示N维空间里的对象。例如N=2，那么就有
![仿射向量](http://upload-images.jianshu.io/upload_images/10172014-3783ecb4cb6a27f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

其中w=1表示为2维空间的点，w=0表示为2维空间的向量。
下面是二维空间的仿射空间：
![仿射空间](http://upload-images.jianshu.io/upload_images/10172014-e6a3bd1252966729.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
图中P1表示向量平面，P2表示点平面，两个平面共同构成了二维空间的仿射空间。
显而易见的，P2上的点相减会落在P1上，P1上的向量加上P2上的点落在P2上，P1上的向量相加还是在P1上，P2上的点相加没有实际意义。这与点和向量的几何定义正好契合。
说到仿射空间，下面就该说仿射变换了。
## 仿射变换
仿射变换是指将仿射空间中的点变换成另外一个点的操作。
常用的仿射变换包括：平移、缩放、旋转、切变、反射和投影。
![仿射变换](http://upload-images.jianshu.io/upload_images/10172014-e0afd1c3dfcd75d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

怎么变换呢？这里就需要用到本文的主角：矩阵。
我们知道变换N维向量需要N维方阵（即N行N列）来变换，那么在仿射空间里，就需要一个增广矩阵来变换点。

![增广矩阵](http://upload-images.jianshu.io/upload_images/10172014-822398fd0191feb5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![增广矩阵](http://upload-images.jianshu.io/upload_images/10172014-4d59ef589d591a34.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

对于点来讲，w是1，也就意味着第四列实际上是常数项。
而对于向量来讲，w是0，也就是说向量的变换不包括常数项（即向量只有方向和大小没有位置）。
这里就体现了仿射变换的一个重要的作用：它用一个矩阵乘法合并了矩阵的乘法（旋转和缩放）和加法（平移）。

我们用下图来简单复习一下矩阵乘法：
![矩阵乘法](http://upload-images.jianshu.io/upload_images/10172014-c4ddd06c02d7228c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
即：
![矩阵乘法](http://upload-images.jianshu.io/upload_images/10172014-08911a0206726cf7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果我们把xyzw当做自变量xt、yt、zt、wt当做因变量的话，我们就可以得到一个结论：  **矩阵是系数表**。

## 变换
[理解矩阵，矩阵背后的现实意义](http://www.360doc.com/content/14/0824/14/202378_404267225.shtml)文中举了两个特别有意思的例子：飞矢不动和量子跃迁。旨在说明一个问题：运动是连续的，变换是离散的。所谓离散，就是不连续，就是不需要中间过程。
例如哆啦A梦的任意门
![任意门](http://upload-images.jianshu.io/upload_images/10172014-e5eea67ec7566e8d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在宏观的世界中，两点之间线段最短，所以从A点到B点，无论速度有多快，都要经历一段时间。
在哆啦A梦的世界中，大雄可以通过任意门门“传送”到任意一个地方，我们可以认为这个“传送”的过程不需要时间。那么我们就可以把变换定义为：将一个点直接变成另外一个点的操作。
例如游戏中传送、闪现和各种位移技能，再比如星际穿越里的虫洞，科幻作品中的跃迁，哆啦A梦中的翘曲空间以及超时空要塞中的空间折叠等，我们都可以认为这些是变换。
令一个对象从一个位置“穿越”到另一个位置，即变换。
![使用仿射变换构建的分形图](http://upload-images.jianshu.io/upload_images/10172014-15be9dbb152c9c36.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果完成变换？当然是使用矩阵。
那么我们就又可以得到一个结论：**矩阵描述了变换**。
## 坐标系
我们都知道，一个点在不同的坐标系中的表示是不一样的。
![错的不是我，是这个世界](http://upload-images.jianshu.io/upload_images/10172014-d250e0db429559e2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
例如图中的剑，如果在人物的坐标系中，它的坐标是：
![人物坐标系](http://upload-images.jianshu.io/upload_images/10172014-95af29965298fa45.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
而在全局坐标系中，（人物的x坐标为1，绕y轴旋转180度，均匀缩放为2）它的坐标是：
![全局坐标系](http://upload-images.jianshu.io/upload_images/10172014-8f96c2c0eeb177a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
反过来思考这个问题，我们有一个全局坐标系，这个坐标系是不会变的，某个确定的点也是不会变的，那么在不同的坐标系中，这个点的表达方式却变了，这是为何呢？我们是否可以认为这其实是坐标系在变。另外，矩阵也在变，我们是否可以认为矩阵的变化和坐标系的变化是相关的呢？或者本身二者就是一致的？
我们用更加直观的方式来解释这个问题：
![右手坐标系](http://upload-images.jianshu.io/upload_images/10172014-d4c881a3681d846f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
从上图我们可以看出，坐标系的xyz基向量分别对应了其变换矩阵的第一、二、三列（m3、m7和m11为0），而原点的位置对应了其变换矩阵的第四列（m15为1）。
这并不是什么魔法，也不是什么巧合，如果你将上面这个图和矩阵的乘法结合在一起看，或者就可以更好的理解这个问题：坐标系的变化实际上是用3个新的基向量和1个新的原点重新描述对象（点或者向量）。
回到之前的人剑模型，人物的x坐标为1，绕y轴旋转180度，均匀缩放为2，我们可以算出，人物的xyz基向量（非归一化）分别为(-2,0,0) (0,2,0)和(0,0,-2)，原点位置为(1,0,0)。将它组成矩阵，与人物坐标系中的坐标（仿射）相乘，我们就可以得到世界坐标系中坐标。
于是，我们又双叒叕得到一个结论：**矩阵描述坐标系**。
## 矩阵究竟是什么？
前面我们留下一个疑问，到底矩阵是变换还是坐标系？
本文给出一个简单的区分：对于同一个坐标系中的不同点，矩阵即是变换；对于不同坐标系中的同一点，矩阵即是坐标系。
但是，仍需要再说一句：坐标系和点，谁同谁不同，本身就是相对的，所以变换即是坐标系。

## 齐次空间
等等！仿佛收尾之前还漏了点什么。
上文中说过，仿射空间是一种特殊的齐次空间，仿射空间的w非0即1，但是普通齐次空间的w可以是任意值（点与相机的深度值）。
![铁轨在无穷远处相交在一起](http://upload-images.jianshu.io/upload_images/10172014-6c43e9cc1ab638ca.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我们知道，在欧氏空间里，平行的两条直线永远不可能相交。但是因为透视关系，当3D对象投影到2D空间时，平行线就可能在无穷远处相交。为了解决这个问题，我们就需要齐次空间。
![齐次坐标系到笛卡尔坐标系](http://upload-images.jianshu.io/upload_images/10172014-cd237dfebdb57835.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
熟悉图形学的同学肯定看出来了，这分明就是从齐次裁剪空间到设备归一化空间的操作。
而齐次空间本身是为了描述透视关系而存在的，它并不能作为一个实际的空间来观察，所以最后都要将齐次空间里的点投影到w=1的平面上，即除以w。因为除以w，所以才能表达出正确的透视（近大远小）关系。
此外，我们知道了仿射空间里的向量其实是无穷远处的点。

# 参考文献
1. DirectX 9.0 3D游戏开发编程基础
2. 3D数学基础：图形与游戏开发
3. 3D游戏与计算机图形学中的数学方法
4. 计算机图形学
5. [理解矩阵，矩阵背后的现实意义](http://www.360doc.com/content/14/0824/14/202378_404267225.shtml)
6. [OpenGL Transformation](http://www.songho.ca/opengl/gl_transform.html#matrix)
7. [Matrix (mathematics)](https://en.wikipedia.org/wiki/Matrix_(mathematics))
8. [齐次空间的裁剪-为什么不在投影除法后裁剪重要](http://blog.csdn.net/linuxheik/article/details/53404141)
9. [齐次坐标](http://www.360doc.com/content/10/1226/10/3843418_81406265.shtml)
10. [土圭垚㙓数学课（四）空间变换](http://blog.csdn.net/ecidevilin/article/details/78182421)