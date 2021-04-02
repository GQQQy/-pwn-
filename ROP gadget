随着 NX 保护(No-eXecute 不可执行)的开启，以往直接向栈或者堆上直接注入代码的方式难以继续发挥效果。攻击者们也提出来相应的方法来绕过保护，目前主要的是 ROP(Return Oriented Programming)，其主要思想是在**栈缓冲区溢出的基础上，利用程序中已有的小片段( gadgets )来改变某些寄存器或者变量的值，从而控制程序的执行流程。所谓gadgets 就是以 ret 结尾的指令序列，通过这些指令序列，我们可以修改某些地址的内容，方便控制程序的执行流程。**
> 之所以称之为 ROP，是因为核心在于利用指令集中的 ret 指令，改变指令流的执行顺序。
> **具体利用细节将在栈溢出章节介绍。**

**ROPgadget工具可以帮助你寻找合适的gadgets，在编写你的ROP exp的时候有很大作用。ROPgadget支持 x86, x64, ARM, ARM64, PowerPC, SPARC和MIPS架构下的ELF/PE/Mach-O文件格式。**

# 安装
如果你要使用ROPgadget，你首先需要安装[Capstone](http://www.capstone-engine.org/)(反汇编框架)
```
$ sudo pip install capstone

```
Capstone支持多平台(Windows, ios, android, cygwin...)交叉编译请参考<https://github.com/aquynh/capstone/blob/master/COMPILE.TXT>。
Capstone安装好后，ROPgadget可以作为一个standalone工具使用。
```
$ ROPgadget.py

```
或者通过python安装库
```
$ python setup.py install
$ ROPgadget

```
直接通过Pypi安装也可以
```
$ pip install ropgadget
$ ROPgadget
```
测试一下安装完成
![ROPgadget](https://upload.nsg.cn/uploads/images/202007/10/29/eJhm8YWvMR.png!large)


# 具体使用方法

```
usage: ROPgadget.py [-h] [-v] [-c] [--binary <binary>] [--opcode <opcodes>]
                    [--string <string>] [--memstr <string>] [--depth <nbyte>]
                    [--only <key>] [--filter <key>] [--range <start-end>]
                    [--badbytes <byte>] [--rawArch <arch>] [--rawMode <mode>]
                    [--rawEndian <endian>] [--re <re>] [--offset <hexaddr>]
                    [--ropchain] [--thumb] [--console] [--norop] [--nojop]
                    [--callPreceded] [--nosys] [--multibr] [--all] [--noinstr]
                    [--dump]
```
## 参数
```
    -h, --help           显示帮助文档
    -v, --version        版本号
    -c, --checkUpdate    检测新版本是否可用
    --binary <binary>    指定二进制文件进行分析
    --opcode <opcodes>   在可执行段中查找opcode
    --string <string>    在可读的段中查找字符串
    --memstr <string>    查找单个byte在所有的可执行段中
    --depth <nbyte>      搜索引擎的深度
    --only <key>         只显示特别的指令
    --filter <key>       过滤特定指令
    --range <start-end>  在地址之间寻找(0x...-0x...)
    --badbytes <byte>    拒绝特定指令在gadget的地址下
    --rawArch <arch>     指定文件架构
    --rawMode <mode>     指定源文件的mode
    --rawEndian <endian> 指定源文件的endianness
    --re <re>            正则表达式
    --offset <hexaddr>   指定gadget的地址偏移
    --ropchain           ROP chain的生成
    --thumb              在ARM架构下使用搜索引擎thumb 模式
    --console            使用交互终端对于搜索引擎
    --norop              禁止ROP搜索引擎
    --nojop              禁止JOP搜索引擎
    --callPreceded       仅显示call-preceded的gadgets
    --nosys              禁止SYS搜索引擎
    --multibr            允许多分枝gadgets
    --all                禁止删除重复的gadgets，即显示所有
    --noinstr            禁止gadget指令终端打印
    --dump               输出gadget bytes
```




参考
- https://blog.csdn.net/weixin_44681716/article/details/89057022
- https://wiki.x10sec.org/pwn/stackoverflow/basic_rop/


