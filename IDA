`IDA`为Interactive Disassembler公司的反编译与除错工具的产品。常用于逆向工程。在CTF比赛中经常用于静态分析，超强的工具。我们经常需要用到其F5反编译功能，但是网络上的资源大多数版本落后或者没有F5功能
这里我们提供资源方便同学们下载使用学习(๑•̀ㅂ•́)و
提供的IDA为windows下的，因为大多数linux或者mac的反编译F5功能并没有，这里我们提供wine工具，方便在Linux操作系统中使用Windows程序。
- 链接: https://pan.baidu.com/s/1kTCK96jy2-2klNPWFbYWZg  密码: 6mu6
- 链接: https://pan.baidu.com/s/1-iCiPMFRvYne91ey8XmjdA  密码: usol
网盘速度较慢，体谅一下就好。

如何通过wine安装Windows软件大家自行Google就好。
具体细节的教程大家可以看开发者的博客https://www.hex-rays.com/blog/, 我们这只是针对于CTF比赛常用的方法进行介绍。

# 常用快捷键
IDA中的快捷键都是和菜单栏的各个功能选项一一对应的，基本上你只要能在菜单栏上找到某个功能，也就能看到相应的快捷键，这里记录几个常用的：

a：将数据转换为字符串
f5：一键反汇编
esc：回退键，能够倒回上一部操作的视图（只有在反汇编窗口才是这个作用，如果是在其他窗口按下esc，会关闭该窗口）
shift+f12：可以打开string窗口，一键找出所有的字符串，右击setup，还能对窗口的属性进行设置
`ctrl+w`：保存ida数据库
`ctrl+s`：选择某个数据段，直接进行跳转
`ctrl+鼠标滚轮`：能够调节流程视图的大小
`x`：对着某个函数、变量按该快捷键，可以查看它的交叉引用
`g`：直接跳转到某个地址
`n`：更改变量的名称
`y`：更改变量的类型
`/ `：在反编译后伪代码的界面中写下注释
`\`：在反编译后伪代码的界面中隐藏/显示变量和函数的类型描述，有时候变量特别多的时候隐藏掉类型描述看起来会轻松很多
`；`：在反汇编后的界面中写下注释
`ctrl+shift+w`：拍摄IDA快照
`u`：undefine，取消定义函数、代码、数据的定义

# 常用设置
### 拍摄快照
由于IDA不提供撤销的功能，如果你不小心按到某个键，导致ida数据库发生了改变，就得重新来过，所以要记得在经常操作的时候，加上快照：file-->take database snapshot
加完快照后，会生成一个新的ida数据库文件，本质上是有点像另存的操作
快捷键：`ctrl+shift+w`

### 菜单栏常用设置

view-->open subviews: 可以恢复你无意中关闭的数据显示窗口

windows-->reset desktop: 可以恢复初始ida布局

option-->font: 可以改变字体的相关属性

### 在流程视图中添加地址偏移

IDA中的流程视图可以说是非常的好用，简单明了地能看出程序的执行流程，尤其是在看if分支代码和循环代码的时候，能够非常直观

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/zICnfrmksU.png!large)

但是，我们还可以改得更加好用，在这个视图中添加地址偏移的话，我们取地址就非常方便，不再需要`按空格切换视图`去找，在菜单栏中设置：option-->general

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/6PtR5UxZR7.png!large)

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/RYdkzxUYwh.png!large)

### 自动添加反汇编注释
这个功能对于萌新来说非常友好，在刚刚初学汇编的时候， 难免遇到几个不常用的蛇皮象拔蚌汇编指令，就得自己一个个去查，很麻烦，开启了自动注释的功能后，IDA就可以直接告诉你汇编指令的意思

同样是在菜单栏中设置：option-->general

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/AUYyjgmgGY.png!large)


![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/BeFYTiGWkg.png!large)

# 常用操作
### 创建数组
在操作IDA的时候，经常会遇到需要创建数组的情况，尤其是为了能方便我们看字符串的时候，创建数组显得非常必要，以下我随便找了个数据来创建数组

首先点击选中你想要转换成数组的一块区域：

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/2X5MiT69gq.png!large)

接着在菜单栏中选择：edit-->array，就会弹出如下的选项框


<img src= "https://upload.nsg.cn/uploads/images/202007/08/29/SnLeTydORB.png!large" weight = "350" height = "400" align = "middle"/>
下面来解释一下各个参数的意思：

`Array element size` 这个值表示各数组元素的大小（这里是1个字节），是根据你选中的数据值的大小所决定的

`Maximum possible size` 这个值是由自动计算得出的，他表示数组中的元素的可能的最大值

`Array size` 表示数组元素的数量，一般都根据你选定的自动产生默认值

`Items on a line` 这个表示指定每个反汇编行显示的元素数量，它可以减少显示数组所需的空间

`Element print width` 这个值用于格式化，当一行显示多个项目时，他控制列宽

`Use “dup” construct` ：使用重复结构，这个选项可以使得相同的数据值合并起来，用一个重复说明符组合成一项

`Signed elements` 表示将数据显示为有符号数还是无符号数

`Display indexes` 显示索引，使得数组索引以常规的形式显示，如果选了这个选项，还会启动右边的Indexes选项栏，用于选择索引的显示格式

`Create as array` 创建为数组，这个一般默认选上的

创建好了以后，就变成了这样：


![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/r5b1lorqG3.png!large)

可以看到这些数据已经被当成一个数组折叠到了一起，或许会遇到`n dup(0xff)`这样的，表示有n个重复的数据0xff。
# 流程图
### 折叠流程图中的分支

在流程视图中，分支过多的时候，可以在窗口标题处右击选择group nodes，就能把当前块折叠起来

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/YbJI3dhz7K.png!large)
分支可以自定义命名，方便与逆向理解。
### 函数调用图

菜单栏中：view-->graphs-->Function calls(快捷键Ctrl+F12)

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/hFYBGfcuxg.png!large)

这个图能很清楚地看到函数之间是如何相互调用的
### 函数流程图

菜单栏中：view-->graphs-->flowt chart(快捷键F12)


![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/S6troqtSTy.png!large)

这个其实跟IDA自带的反汇编流程视图差不多，他可以导出来作为单独的一张图

## 创建结构体：

### 手工创建结构体

创建结构体是在IDA的structures窗口中进行的，这个操作在`堆漏洞的pwn题中经常使用`


![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/jcerVdSNtD.png!large)


可以看到，这里已经存在了三个结构体，程序本身存在的，可以右击选择hide/unhide,来看具体的结构体的内容

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/NiqIHtrLKA.png!large)

**创建结构体的快捷键是：insert (d 增加结构体变量，n重命名结构体变量)**
### 导入C语言声明的结构体

实际上，IDA有提供一个更方便的创建结构体的方法，就是直接写代码导入

在View-->Open Subviews-->Local Types中可以看到本地已有的结构体，在该窗口中右击insert

可以添加新的结构体：

<img src = "https://upload.nsg.cn/uploads/images/202007/08/29/5QguNVVxoZ.png!large" height ="360" weight = "400" align = "center" >

这样就导入了新的结构体:

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/27Px93ysvh.png!large)
接着我们需要对着my_structure右击，选择 synchronize to idb。如果没有这一步的话，同学们会发现structure视图里面，并没有这个结构体。

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/fhggCk5CHm.png!large)
这里涉及到结构体的内存对其问题。ida默认统一4字节对齐，结构体的大小为0x18。

# IDA导出数据文件

在菜单栏中，这里有个选项可以生成各种不同的输出文件

![IDA的基本用法](https://upload.nsg.cn/uploads/images/202007/08/29/LczTZQEm27.png!large)

这里简单的介绍前两个文件，后面的大家可以自己去生成测试一下用途，我这里就不详细介绍了

.map文件描述二进制文件的总体结构，包括与构成改二进制文件的节有关的信息，以及每个节中符号的位置。

.asm文件，也就是汇编了，直接能导出ida中反汇编的结果，这个非常实用，有的时候在逆向中经常遇到大量数据加解密的情况，如果在从IDA中一个个慢慢复制可就太没效率了，直接导出生成asm，在里面复制数据快很多


# IDA常见命名意义

IDA经常会自动生成假名字。他们用于表示子函数，程序地址和数据。根据不同的类型和值假名字有不同前缀

sub *指令和子函数起点
locret* 返回指令
loc *指令
off* 数据，包含偏移量
seg *数据，包含段地址值
asc* 数据，ASCII字符串
byte *数据，字节（或字节数组）
word* 数据，16位数据（或字数组）
dword *数据，32位数据（或双字数组）
qword* 数据，64位数据（或4字数组）
flt *浮点数据，32位（或浮点数组）
dbl* 浮点数，64位（或双精度数组）
tbyte *浮点数，80位（或扩展精度浮点数）
stru* 结构体(或结构体数组)
algn *对齐指示
unk* 未处理字节

IDA中有常见的说明符号，如db、dw、dd分别代表了1个字节、2个字节、4个字节


参考
- https://xz.aliyun.com/t/4205#toc-12
-《IDA pro权威指南》(第二版)
- www.idaireland.com/


