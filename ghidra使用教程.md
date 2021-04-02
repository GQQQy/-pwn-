**2019年，NSA发布了一款功能强大、免费的开源逆向分析工具：Ghidra。该反汇编工具类似于我们常用的IDA，不过其基于JAVA开发，是一款适用于Windows、Mac和Linux的跨平台反汇编工具，用户还可以使用Java或Python开发自己的Ghidra插件或者脚本。2017年维基解密在Vault 7中首次曝光了Ghidra，该信息来自于中央情报局（CIA）的内部文件，Ghidra在过去数年里一直被用于NSA相关的网络安全任务当中。**

# 安装
首先你需要在ghidra官网<https://ghidra-sre.org/>上下载文件或者你可以执行以下命令

`wget https://ghidra-sre.org/ghidra_9.0.1_PUBLIC_20190325.zip`

该命令制定下载版本，当然你也可以自己选择合适的版本下载。
下载完成之后进行解压缩，这是对于我的版本。

`unzip ghidra_9.0.1_PUBLIC_20190325.zip`

接下来安装Java jdk 和 jre

```
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt update
sudo apt install openjdk-11-jdk
sudo apt install openjdk-11-jre-headless
```
`进入安装目录`
`chmod +x gihdraRun` 
`./ghidraRun`
此时已经安装完成，程序已经可以跑起来了

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/qLOTEHBfMe.png!large)

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/uliucaeJeo.png!large)

# Ghidra的使用

Ghidra功能齐全。它包括强大的代码浏览器，图形查看器，反编译器，数百个脚本，各种搜索工具，撤消/重做支持，协同工作服务器，程序差异比较工具等。由于Ghidra是巨大的，这里无法涵盖每一个功能。那么，我们将关注那些经验丰富的逆向工程师所认为的基础功能，也就是最重要和最有用的功能。

### 项目管理

在Ghidra中，任何东西都是一个项目。与IDA不同，您不会使用输入文件开始逆向工程会话，而是从创建项目开始。

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/WKDqwZRCmm.png!large)

新建一个非共享项目

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/8gfMTktknT.png!large)

创建好项目之后我们就可以选择文件进行反编译了，选择2018SUCTF一道题目进行反编译测试

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/p2MiqhTdmj.png!large)

然后就可以在目录下看到加载的目标了，双击即可进入

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/bHCsIvaxVR.png!large)

分析后就可以看到完整界面了，由于是基于项目的，我们可以导入多个文件

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/6puJ6FQl9x.png!large)
# 主要功能介绍
### Navigation菜单
该菜单下是一些主要操作选项：

<img src = "https://upload.nsg.cn/uploads/images/202007/09/29/DnWwFPIt7R.png!large" width="300" height="400">

### Window菜单
该菜单下是其主要支持的功能窗口，类似于IDA中view->opensubview

<img src="https://upload.nsg.cn/uploads/images/202007/09/29/Rb77O9NNCG.png!large" width = "200" height = "500">

### 脚本管理菜单

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/GZFX1IS0o0.png!large)
选中之后是可以直接运行的，比如我们选择搜索字符串功能

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/kPrLJYsDRy.png!large)

在左侧的操作栏中可以看到有程序树，符号树，数据类型管理这几个界面。，
![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/pOTJnyG5Mm.png!large)
### 反编译（Ctrl+E）
相当于IDA中的F5，展示反编译后的代码：

![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/kbQfJFWxfF.png!large)

# 更多操作

更多详细的快捷键和操作可见解压后docs文件夹中的CheatSheet.html文件：


![ghidra使用教程](https://upload.nsg.cn/uploads/images/202007/09/29/gWWFXr4neU.png!large)


参考
- https://www.ylmzcmlttn.com/2019/03/26/ghidra-installation-on-ubuntu-18-04-16-04-14-04/
- https://www.secrss.com/articles/8829
