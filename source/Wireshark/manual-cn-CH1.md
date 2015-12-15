title: Chapter 1. 介绍
---

### 1.1. Wireshark是什么? ###

Wireshark是网络数据包分析软件。网络数据包分析器将尝试捕获网络数据包，并试图尽可能详细的显示数据包的数据。

您可以认为一个网络包分析软件是一个用来检查网线内部发生了什么的测量设备，就像电工使用电压表来检查电缆内部发生了什么一样（当然，但在一个更高的水平 ）。

在过去，这样的工具要么非常昂贵的，专用的，或两者兼而有之。然而，随着Wireshark的出现，这一切都改变。

Wireshark也许是目前最好的开源数据包分析软件。

#### 1.1.1. 一些预期目的 ####

下面是一些使用Wireshark的例子：

- 网络管理员用它来​​解决网络问题
- 网络安全工程师用它来​​检查安全问题
- 开发人员可以使用它来​​调试协议实现
- 人们用它来​​学习网络协议内部

除了这些例子之外Wireshark在许多其他情况下也很有帮助。

#### 1.1.2. 特性 ####

下面是Wireshark众多特性中的一些：
- 
- 适用于 UNIX 和 Windows。
- 从网络接口捕获实时分组数据。
- 打开包含使用tcpdump / WinDump、Wireshark以及其他一些抓包程序文件捕获的数据包。
- 从包含hex dumps分组数据的文本文件中导入数据包。
- 显示数据包的非常详细的协议信息 。
- 保存捕获数据包。
- 以多种捕获文件格式导出部分或全部数据包。
- 以多种规则来过滤数据包。
- 以多种规则来搜索数据包。
- 基于筛选器来上色数据包。
- 创建各种统计数据。
- ...还有更多！

但是，要真正欣赏它的力量，您必须开始使用它。

图 1.1, “Wireshark 的捕获数据包，可以让您检查他们的内容” 显示Wireshark已经捕获的一些数据包，并等待着您

**图 1.1. Wireshark的捕获数据包，可以让您检查它们的内容。**


{% img /Wireshark/manual-cn-img/ws-main.png %}


#### 1.1.3. 在多种网络介质中捕获报文 ####

Wireshark可以捕捉来自多种不同网络介质类型的流量-不用关注它的名字-包括无线LAN。所支持的媒介类型，取决于很多方面，如正在使用的操作系统。支持的媒介类型的说明在https://wiki.wireshark.org/CaptureSetup/NetworkMedia。

#### 1.1.4. 从其他捕获软件导入文件 ####

Wireshark可以打开大量的其他捕获程序捕获的数据包。对于输入格式列表，请参阅  5.2.2节, “输入文件格式”。

#### 1.1.5. 为其他捕获软件导出文件 ####

Wireshark可以保存数据包为大量的其他捕获程序捕获的数据包格式。对于输出格式列表，请参阅  5.3.2节, “输出文件格式”。

#### 1.1.6. 多协议解码器 ####

支持众多协议的协议解码器（或解析器，他们在Wireshark中的叫法）：请参阅 附录 C，协议和协议字段。

#### 1.1.7. 开源软件 ####

Wireshark是开源软件项目，使用 GNU通用公共授权 (GPL)发布。您可以自由地使用Wireshark在任意数量的计算机上，而不用担心许可证或手续费等。此外，在GPL许可下的所有源代码是免费的。正因为如此，人们给Wireshark添加新的协议非常容易，无论是作为插件或内置的源代码，人们也经常这么做！

#### 1.1.8. Wireshark 不是什么 ####

这里有一些事情Wireshark不能提供：

Wireshark不是一个入侵检测系统。当有人在您的网络中做一些未经允许的奇怪的事情时，它不会警告您。但是，如果奇怪的事情发生了，Wireshark可以帮助您找出到底发生了什么。
Wireshark将不能操纵网络，它只会“测量”网络。Wireshark不能在网络上发送数据包或做其他一些动作（除了名称解析，但也可以禁用解析）。

### 1.2. 系统要求 ###

Wireshark需要资源的数量取决于您的环境和您待分析的捕获文件大小。以下的值对于中小大小的不超过几百兆的捕获文件是合适的。更大的捕获文件将需要更多的内存和磁盘空间。

[Note]	繁忙的网络意味着大量捕获
一个繁忙的网络工作可以很容易地产生巨大的捕获文件。捕捉千兆，甚至100兆的网络可以在很短的时间内生产上百兆字节的捕获数据。一个快速的处理器，大量的内存和磁盘空间始终是一个好主意。

如果Wireshark的内存用完，会导致它崩溃。见 [https://wiki.wireshark.org/KnownBugs/OutOfMemory](https://wiki.wireshark.org/KnownBugs/OutOfMemory) 的细节和解决方法。

虽然Wireshark捕获报文使用独立的进程，他的主界面是单线程的，并没有从多核系统中获益。

#### 1.2.1. 微软 Windows ####

- Wireshark的当前版本应该支持任何仍然在扩展支持生命周期 的Windows版本。在写这篇文章的时候包括Windows 8，7，Vista，Server 2012，Server 2008 R2，Server 2008和Server 2003。
- 任何现代的 32-位 x86 or 64-位 AMD64/x86-64 处理器。
- 200 MB 可用内存。 更大的捕获文件需要更多的内存。
- 75 MB可用磁盘空间。捕获文件需要额外的磁盘空间。
- 1024×768（1280×1024或建议更高）分辨率，至少为16位色。8位色彩应该也能工作，但用户体验会下降。
- 支持的用于捕获的网卡
 - 以太网。Windows支持的任何卡应该工作。查看维基页面 以太网捕获和 卸载了解可能影响您的环境的问题。
 - Ethernet. Any card supported by Windows should work. 参见 the wiki pages on Ethernet capture and offloading for issues that may affect your environment.
 - 802.11。参考 Wireshark wiki 页面.。没有特殊设备的话，捕获原始802.11信息可能很困难。
 - 其他介质。参考 https://wiki.wireshark.org/CaptureSetup/NetworkMedia
不再对超出微软的扩展生命周期支持窗外的旧版本Windows提供支持。由于我们无法控制的情况，很难或不可能支持这些系统，如我们所依赖的第三方库或哪些仅出现在新版本Windows中的特性（如硬化安全或内存管理）。

Wireshark的1.10是最后一个正式支持Windows XP的版本分支。Wireshark的1.2是支持Windows 2000的最后分支，请参见 Wireshark 版本生命周期 页面了解详细信息。

#### 1.2.2. UNIX / Linux ####

Wireshark目前可以运行在大多数UNIX平台。系统的要求可以对照上面列出的Windows值。

二进制软件包可用于大多数的Unices和Linux发行版，包括以下平台：

- Apple Mac OS X
- Debian GNU/Linux
- FreeBSD
- Gentoo Linux
- HP-UX
- Mandriva Linux
- NetBSD
- OpenPKG
- Red Hat Enterprise/Fedora Linux
- Sun Solaris/i386
- Sun Solaris/SPARC
- Canonical Ubuntu

如果一个二进制包不适用于您的平台，您可以下载源代码，并尝试编译它。请报告您的经验给 wireshark-dev[AT]wireshark.org.

### 1.3. 从哪里获取Wireshark ###

您可以从Wireshark的网站 [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)获取最新版本。下载页面会自动突出显示您的平台相应的下载，并指引您到最近的镜像。

新版本的Wireshark一般每一或两个月更新。

如果您想被通知新Wireshark的发布，您应该订阅Wireshark的Wireshark-通知邮件列表。您会发现更多的细节在  1.6.5节, “邮件列表”。

###1.4. Wireshark简史###

在1997年年底Gerald Combs需要一个工具用于跟踪网络问题，并希望更多地了解网络，所以他开始写Ethereal（Wireshark项目原来的名字）来解决这两个问题。

Ethereal在几次暂停开发后于1998年7月发布初始版本0.2.0。经过补丁修正，bug报告，鼓励的话开始出现，Ethereal开始走上成功之路。

此后不久Gilbert Ramirez 看到了它的潜力，并为他贡献了一个底层解析器。

在1998年10月盖伊·哈里斯正在寻找比TCPView的更好的东西，所以他开始了应用补丁和促进解剖，以空灵。

在1998年底Guy Harris ，正在讲授TCP / IP课程，看到了他对这些课程的潜力，并开始关注他，看它是否支持他所需要的协议。然而新的协议不是很容易地添加。于是，他开始贡献解析器和补丁。

自那时以来的为项目贡献的人的名单已经很长，几乎所有的人都从他们需要而Wireshark尚未支持的协议开始。因此，他们复制一个现有的解析器并将代码贡献回团队。

2006年该项目搬了家，并以一个新的名字重新出现：Wireshark。

2008年，经过十多年的发展，Wireshark的终于到了1.0版本。此版本是第一个被视为完整的，实现最小功能的版本。它的发布恰逢第一次Wireshark开发者和用户大会（被称为Sharkfest）。

### 1.5. 开发和维护Wireshark ###

Wireshark最初由Gerald Combs开发。持续开发和维护Wireshark的是Wireshark团队，该团队是由修复bug和提供新功能的个人组成的松散团队处理。

同时也有大量的人为Wireshark贡献协议解析器，而且预计这将继续下去。您可以通过检查Wireshark的关于对话框来找到这些贡献代码人员的列表，或者在Wireshark网站的作者页面上也能找到。

Wireshark是一个开源软件项目，根据 GNU通用公共许可证（GPL）版本2来发布。所有的源代码根据GPL免费提供。欢迎您修改Wireshark来满足自己的需要，如果您贡献您的改进回Wireshark团队，将不胜感激。

您通过贡献您的改进回馈社会，将获得三大好处：

1. 其他人的因为您的贡献而得到帮助的人将非常感激他们，您就会知道您已经在以同样的Wireshark的开发者帮助人们的方式帮助他人。
1. Wireshark的开发者可能更多帮助您的提升，因为总有改进的余地。或者，他们可以在您的代码上实现更多高级的事情，这对自己也是非常有帮助的。
1. Wireshark的维护者和开发者同时会维护您的代码，当API变化或其他更改发生时同时进行修正，并且通常和Wireshark保持配合。所以，如果Wireshark更新了（这经常发生），您可以从该网站获取一个新版本并且您的更改已经包含在内，而无需额外的工作。

Wireshark的源代码和一些平台的二进制文件包，都可以使用Wireshark的网站的下载页面： [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)。

### 1.6. 报告问题和获得帮助 ###

如果您在使用Wireshark时有问题或需要帮助，可能有几个地方您会感兴趣（当然除了本指南之外）。

#### 1.6.1. 网站 ####

您会在Wireshark的主页 [https://www.wireshark.org/](https://www.wireshark.org/)上发现很多有用的信息。

#### 1.6.2. Wiki ####

Wireshark Wiki  [https://wiki.wireshark.org/](https://wiki.wireshark.org/)提供了大量关于Wireshark和数据包捕获的信息。您会发现很多本用户指南没有涉及的信息。例如，解释如何在交换网络上进行捕获，不断努力建立协议参考以及更多内容。 

而最重要的，如果您想对一个特定的主题贡献自己的知识（可能是您非常熟悉的网络协议），您可以通过简单地使用Web浏览器来编辑维基页​​面。

#### 1.6.3. Q&A 网站 ####

Wireshark Q&A 网站 [https://ask.wireshark.org/](https://ask.wireshark.org/) 提供问题和答案的资源。您可以查找之前哪些问题被问过了，关于这个问题人们给出什么答案。答案是分级的，所以您可以很容易地挑选出最好的。如果您的问题还没有被讨论过，您可以自己发布一个。

#### 1.6.4. FAQ ####

常见问题列表经常遇到的问题进行相应的解答。

[Note]	阅读 FAQ
在发送任何邮件到下面的邮件列表前，请务必阅读FAQ。它往往会回答您的任何问题。这将节省自己和别人了大量的时间。请记住，很多人都订阅了邮件列表。

您可以通过点击Wireshark的菜单项“ Help/Contents”并选择所示的对话框中的FAQ页面来找到FAQ。

在线版本在Wireshark的网站： [https://www.wireshark.org/faq.html](https://www.wireshark.org/faq.html)。您可能会喜欢这个在线版本，因为它通常更新更及时并且HTML格式更容易使用。

#### 1.6.5. 邮件列表 ####

有几个可用的特定Wireshark主题邮件列表：

*wireshark-announce*

这个邮件列表会告知您新的程序版本发布，它通常大约每4-8周出现一次。
 
*wireshark-users*

这个列表提供给Wireshark的用户。人们发送关于编译和使用Wireshark的问题，其他人（希望）提供答案。 

*wireshark-dev*

这个列表是提供给Wireshark的开发者。如果您想开发协议解析器，加入这个列表。 
您可以分别从Wireshark网站上订阅这些列表： [https://www.wireshark.org/lists/](https://www.wireshark.org/lists/)。从那里，

您可以通过在相关列表的标题下点击 “订阅/取消/选项” 按钮项按钮来选择订阅哪些邮件列表。归档的链接也同时包含在该页面上。 

[Tip]	归档列表
您可以在归档列表中搜索，看看是否有人问过同样的问题，可能就能够获取答案。这样您就不必等到有人来回答您的问题。

#### 1.6.6. 报告问题 ####

[Note]	注意
在报告任何问题前，请确保您已经安装了Wireshark的最新版本。

当向Wireshark报告问题时，请提供以下信息：

1. Wireshark的版本号和与之相连的依赖库，如Qt或GLib。您可以从Wireshark的“关于”对话框或 wireshark -v命令来获取。
1. Wireshark运行平台的信息。
1. 您的问题的详细描述。
1. 如果您得到一个错误/警告消息，复制该消息的文本（如果有很多消息，需包含之前和之后几行），以便其他人发现出差错的地方。请不要给这样的信息：“在做x时，我得到一个警告”，因为这不会对去哪里查找问题提供帮助。

[Note]	不要发送大文件
不要发送大文件（> 500KB）到邮件列表。只需提示，进一步的数据可应要求提供。大文件只会惹恼了邮件列表上很多对您的问题不感兴趣的人。如果需要的话，您会被要求提供进一步的数据给真的可以帮助您的人。

[Warning]	不要发送机密信息！
如果您发送捕捉文件到邮件列表，要确保它们不包含任何敏感或机密信息，像密码或个人识别信息（PII）。

#### 1.6.7. UNIX/Linux 平台崩溃报告 ####

在报告Wireshark崩溃的时候，如果能提供“报告问题”中提到的跟踪信息是非常有帮助的。

您可以在UNIX或Linux（注意反引号）上通过以下命令来获取跟踪信息：

    $ gdb `whereis wireshark | cut -f2 -d: | cut -d' ' -f2` core >& backtrace.txt
    backtrace
    ^D
如果您没有gdb可用，您必须检查您的操作系统的调试器。

邮件 backtrace.txt 给 [wireshark-dev[AT]wireshark.org](wireshark-dev[AT]wireshark.org)。

#### 1.6.8. Windows平台崩溃报告 ####

Windows发布版本不包含符号文件（.PDB），因为他们非常大。您可以单独在[https://www.wireshark.org/download/win32/all-versions](https://www.wireshark.org/download/win32/all-versions) 和 [https://www.wireshark.org/download/win64/all-versions](https://www.wireshark.org/download/win64/all-versions) 下载。
