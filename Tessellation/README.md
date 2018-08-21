![图1：渲染管线，图片来源：Introduction to 3D Game Programming with DirectX 12](https://pic2.zhimg.com/v2-3785f9c0621f81a80cdab6fbaa3d04b5_b.jpg)

#输入装配阶段

当我们使用曲面细分的时候，我们不再向IA阶段（Input Assembler Stage，从显存读取几何数据用来组合几何图元，例如三角面或线段）提交三角面，而是提交数个控制点的patch。
三角形可以认为是有三个控制点的patch，所以我们依然可以提交常规的三角面网格。一个有四个控制点的四边形也可以被提交，但是在曲面细分阶段这些patch会被细分成三角面。
当然我们还可以在一个patch中添加更多的控制点。例如，我们可以用多个控制点来调整贝塞尔曲线（Bezier curves），或者贝塞尔曲面。控制点越多，自由度越高。