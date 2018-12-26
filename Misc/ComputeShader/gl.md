CS是一个着色器阶段，完全用于计算任意的信息。它不仅可以渲染，而且通常可以用于一些不直接跟绘制三角形和像素相关的任务上。

CS执行起来，跟其他着色器阶段不同。所有其他的着色器阶段，拥有明确定义的输入值集合，某些内置，某些用户定义的。着色器执行的频率是根据那个阶段的性质规定的；例如，对于每个输入的定点，vs执行一次（虽然使用cache来跳过某些执行）。fs的执行，是由光栅化处理生成的片元定义的。
CS工作起来很不一样。cs执行在一个很抽象的“空间”里；它取决于每个cs如何描述那个空间。cs执行的数量，定义于执行计算操作用的函数。最重要的是，cs完全没有用户定义的输入或输出。内置的输入之定义了一个被调用的cs在“空间”的哪里执行。
因此，如果一个cs想要使用某些值作为输入，它取决于shader本身获取那些数据，通过访问纹理，载入任意图像，SSBO，或者其他接口形式。同样的，如果cs确实计算了啥东西，它必须显示的写入一个图像或者ssbo。

## 计算空间

cs所执行的空间是抽象的。有一个work group的概念，这是用户可以执行的计算操作的最小量。或者换句话说，用户可以执行一定数量的work group。
计算操作执行的Work group的数量，是由玉壶定义的，当他们调用计算操作。这些组的空间是三维的，所以他们包含“X”，“Y”，“Z”组的数量。他们中的任意一个可以为1，所以你可以执行一个二维或者一维计算操作，而不是三维。这对处理图像数据或者粒子系统的线性数组或者其他任何东西都有用。
当系统真正计算work group的时候，那可能以任意的顺序执行。所以，如果给了它一个(3,1,2)的work group集合，它可能先执行group(0,0,0)，然后跳过group(1,0,1)，执行(2,0,0)。所以，在cs中，你不能依赖于单个group的执行顺序。
不要认为，一个单独的work group是跟一个单独的cs调用是同一个东西；它为啥被叫做“group”。在一个单独的work group 中，里面可能会有很多cs的调用。具体多少个，是由cs自己定义的，而不是根据调用定义的。这个被称作work group的local size。
每个cs都有一个三维的local size（同样，size可以为1，来允许2D或者1D的本地处理）。这个定义了，shader将要发生在每个work group中的调用数量。
所以，如果一个cs的local size是（128， 1， 1），而你使用(16, 8,64)个work group数量来执行它，那么你会获得1048576个分离的shader调用。
这样的区别，可以用来处理多种多样的图像压缩和解压缩；local size可以作为图像数据的一个block的大小（例如8x8）,group数量可以是图像的尺寸除以块的尺寸。每个块被当作一个单独的work group来处理。
一个work group中的单独调用将会被“并行”执行。work group数量和local size之间的区别的主要目的是，在一个work group里不同的cs调用可以通过shared变量集合和特定的函数来沟通。不同work group之间的调用（在同样的cs dispatch中）不能有效的沟通。不是没有潜在的死锁的可能。

## Dispatch

CS不是渲染管线中的常规部分。所以当执行一个draw命令的时候，连接到当前program或者管线的cs不会被执行。
有两个函数可以发起计算操作。他们可以使用已经激活的任意CS（通过glBindProgramPipeline或者glUseProgram，后面有用来决定一个阶段的活跃program通常的规则）。虽然他们不是Draw命令，但是他们是渲染命令，所以他们可以被有条件的执行。
void glDispatchCompute(GLuint num_groups_x, GLuint num_groups_y, GLuint num_groups_z);
参数num_groups_*定义了work group的数量，以三维的形式。这些值不能为0。被Dispatch的work group的数量是有限制的。
可以执行dispatch操作，work group的数量来自于Buffer Object的信息。它跟间接绘制vertex data相同。
void glDispatchComputeDirect(GLintptr indirect);

indrect参数是一个字节偏移，指向GL_DISPATCH_INDIRECT_BUFFER目标缓存。注意，同样的work group数量的限制同样起作用，不过，indirect dispatch绕过了OpenGL的常规错误检查。因此，尝试dispatch越界的work group大小，可能会导致崩溃或者GPU硬锁，所以生成这些数据的时候要注意。

## 输入

CS不能包含任何用户定义的输入变量。如果你希望为CS提供输入，你必须使用实现定义的输入，耦合到ssbo或者纹理这样的资源。你可以使用shader的调用和work group索引来决定获取和执行哪个数据。
CS包含以下内置的输入变量。
in uvec3 gl_NumWorkGroups;
包含了穿个dispatch函数的work group的数量。
in uvec3 gl_WorkGroupID;
这个是当前shader调用的work group。每个XYZ分量可能在[0, gl_NumWorkGroups.XYZ)之间。
in uvec3 gl_LocalInvocationID;
在work group中当前调用的shader。每个XYZ的分量可能在[0, gl_WorkGroupSIze.XYZ)之间。
in uvec3 gl_GlobalInvocationID;
在这个Compute Dispatch命令中，这是CS调用的唯一标识。它是数学计算(gl_WorkGroupID * gl_WorkGroupSize + gl_LocalInvocationID)的速记。
in uint gl_LocalInvocationIndex;
这个是1D版本的gl_GlobalInvocationID，它标记了work group中的调用索引。他是数学计算(gl_LocalInvocationID.z * gl_WorkGroupSize.x * gl_WorkGroupSize.y + gl_LocalInvocationID.y * gl_WorkGroupSize.x + gl_LocalInvocation.x)的速记。

## Local Size
cs的Local Size在shader里定义，使用特殊的layout输入声明：
layout(local_size_x = X, local_size_y = Y, local_size_z = z) in;

默认情况下，local size为1，所以如果你想要一个1D或者2D的work group空间，你可以只制定X或者至指定XY分量。他们必须是大于0的整型的常量表达式。他们必须遵守下面的限制。否则，会发生编译或者链接错误。
local size可以作为编译时常量，在shader里可以访问，你不需要自己定义。
const uvec3 gl_WorkGroupSize;


## 输出

CS没有输出变量。如果你希望CS生成一些输出，你需要使用资源。SSBO和图像加载/保存操作作为CS的输出数据。

## 共享变量
CS中的全局变量，可以用shared存储标记来生命。这样变量的值，可以在一个work group的所有调用中被共享。你不能将一个不透明变量声明为shared，但是集合（数组和结构体）可以。
在一个work group的开始，这些数值没有被初始化。同样，这些数值声明是不能包含初始化，所以，下面是不合法的：
shared uint foo = 0; // No initializer for shared variables.

如果你想要初始化一个共享变量为一个特定的值，那么一个调用必须显示的设置这个变量到那个值。而且，只有一次调用需要这样做，由于以下：

### 共享内存相关性

共享内存访问使用了非相关内存访问的原则。这就意味着，用户必须执行一定的同步来保证这些共享变量是可见的。
共享变量全部被隐式的声明为coherent,所以你不需要（并且不能）使用那个标识符。但是，你仍然需要提供一个适当的内存barrier。常规的内存barrier集合可以在CS中使用，但是他们也需要访问memoryBarrierShaderd();这个barrier是为了共享变量排序特定的。groupMemoryBarrier()表现的像memoryBarrier()（为所有类型的变量排序内存写入），但是它只对当前work group进行read/writes排序。
在work group中的所有调用被称为“并行”执行，但它并不意味着，你可以假设，他们所有都在锁步中执行。如果你需要却保证一个调用已经被写入某个变量，然后你可以读取他，你需要同步调用的执行，而不只是提出一个内存barrier(虽然你仍然需要你个内存barrier)。
为了同步work group里调用之间的读写，你需要采用barrier()函数。这在work group之间的所有调用强制显式的执行了一个同步。work group中的操作不会执行，直到所有其他的调用已经到达了这个barrier。当通过barrier()，先前在group里的所有调用之间写入的所有共享变量会被可见。
如何命令barrier有一些限制，但是cs并不是像TCS那样限制大，cs可以在流控制中被调用，但是他只能在uniform流控制中被调用。所有导致barrier()执行的表达式必须是动态uniform。
简单来说，如果你需要执行一个相同的cs，无论它读取的数据如何不同，所有执行操作必须以准确的同样的顺序准确命中同一个Barrier调用集合。否则，会发生可怕的错误。


### 原子操作

有些源自操作可以被用到整型（vector/array/struct）的共享变量上。这些函数和SSBO的原子操作相同。
所有原子函数返回原始值。nint项可以是int或uint。
nint atomicAdd(inout nint mem, nint data)
加data到mem上。
nint atomicMin(inout nint mem, nint data)
mem值不小于data
nint atomicMax(inout nint mem, nint data)
mem值不大于data
nint atomicAnd(inout nint mem, nint data)
位与
nint atomicOr(inout nint mem, nint data)
位或
nint atomicXor(inout nint mem, nint data)
异或
nint atomicExchange(inout nint mem, nint data)
设置men为data
nint atomicCompSwap(inout nint mem, nint compare, nint data)
如果men的当前值等于compare，设置mem为data，否则不变。


## 限制

在单独一个调用中可以dispatch的work group数量定义为GL_MAX_COMPUTE_WORK_GOURP_COUNT。这个必须使用glGetIntegeri_v来获取，包含一个[0,2]的索引，表示work group数量的XYZ分量的最大值。
尝试使用一个超过这个范围的值来调用glDispatchCompute会报错。尝试调用glDispatchComputeIndirect更错，他可能导致程序中断或者其他坏事。
注意，这些值最小必须是65535，对所有三个轴。所以你可以获得很多工作空间。
local size也有限制，有两个限制的集合。一个对local size维度的通用限制，使用同样的方法获取GL_MAX_COMPUTE_WORK_GROUP_SIZE。注意，最小需求要小很多，对x和y是1024，对z是更小的64。
还有另外一个限制：在一个work group中的调用的总数。也就是，local size的XYZ分量的城西必须小于GL_MAX_COMPUTE_WORK_GROUP_INVOCATIONS。最小值为1024.
在一i个cs中，还有一个对所有共享变量的总容量的限制。GL_MAX_COMPUTE_SHARED_MEMORY_SIZE，以bytes形式。OpenGL的最小值是32KB。OpenGL
没有在GL类型和共享变量容量之间精确的映射，虽然你可以使用std140布局原则和UBO/SSBO大小作为一个普遍的准线。