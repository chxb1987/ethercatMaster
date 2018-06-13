# ethercatMaster
建立项目学习Igh ethercat Master的使用。
在看代码之前，分析需要的基础知识。

1. ethercat Master相对应的概念。
2. linux 驱动开发
3. linux 网络编程
不得不说每一项都需要花很多时间去学习。不过，我并不是要成为一个合格的linux驱动工程师，也不需要完整的了解linux网络编程的内容。我只需要了解其中的一个子集，让我可以看懂主站代码就可以。

所以，目标明确是整个过程中提高效率节省时间的关键。

暂时确定一下学习计划：
1. 将 《ethercat-1.5.2.pdf》翻译成中文。 英文的在后面对照的时候浪费时间太多，既然要从头看明白，就干脆翻译成中文好了。
2. 《Linux设备驱动开发详解_宋宝华.pdf》 的学习。尽量只看概念和一些核心函数的使用方法
3. 《Linux网络编程.pdf》 的学习。只看概念。这部分后面可能用的到。但是尽量不投入过大精力，以免造成本末倒置。


应该学习ethercat协议与阅读部分主站用户空间接口的注释。现在已经可以实现伺服驱动器的CSP控制了。
demo_ec文件夹中是加入了链接ethercat主站的控制的源码。
整个代码分两个部分，rt_task（实时任务）与用户空间非实时任务（usr_task）。
rt_task，就是通过初始化函数配置PDO，链接主站。暂时没有做到自动读取xml或者是自动读取从站寄存器来做到自动配置。
后面可以看从站的cstruct命令的实现方案来实现。暂时并不需要。
ec_interface.c中实现了从站提供的功能：上使能，复位，csp运动。读取从站信息等几个接口。
Motion中调用这几个接口实现运动模块控制功能。
该项目暂时告一段落。
