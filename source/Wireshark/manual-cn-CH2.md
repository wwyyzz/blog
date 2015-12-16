title: Chapter 2. 编译和安装Wireshark
---
### 2.1. 介绍 ###

正如所有的事情必须有一个开始，Wireshark也一样。要使用Wireshark，您必须先安装它。如果您运行的是Windows或Mac OS X，您可以在<https://www.wireshark.org/download.html>下载官方版本并安装， 然后跳过这一章的其余部分。

如果您正在运行其它操作系统，例如Linux或FreeBSD，您可能想从源代码安装。在一些Linux发行版提供Wireshark的软件包，但它们通常提供的是过时的版本。UNIX版本至今未提供Wireshark。出于这个原因，您需要知道从哪里得到Wireshark的最新版本，以及如何安装它。

本章介绍了如何获得源代码和二进制包，如何从源代码编译Wireshark。

以下是您可以使用的一般步骤：

1. 根据您的需求下载相关的软件包，如源代码或二进制分发版。
1. 如果需要的话编译源代码为二进制文件。这可能涉及编译和/或安装其他需要的包。
1. 安装二进制包到最终目的地。

### 2.2. 获取源代码和二进制发行版 ###

您可以同时从Wireshark网站: <https://www.wireshark.org/> 获得源代码和二进制分发版。选择下载链接，然后选择所需的二进制或源代码包。

[Note]	下载所有必需的文件
如果您是从源代码编译Wireshark，您通常情况下，您很可能需要下载几个源码包，除非您以前已经下载了Wireshark。这将在后面有更详细的说明。

一旦您已经下载了相关的文件，您可以去到下一个步骤。

### 2.3. 在Windows下安装Wireshark ###

Windows安装文件包含了平台和版本，如Wireshark-winxx-1.99.x.exe文件。Wireshark安装文件包括所需的用于数据包捕获的WinPcap软件。

只需要简单的从: <https://www.wireshark.org/download.html> 下载安装文件并执行。官方软件包由**Wireshark基金会**签名。您可以选择安装多个可选组件，然后选择安装包的位置。默认设置适用于大多数的用户。

#### 2.3.1. 安装组件 ####

在选择组件的安装程序的页面，您可以进行以下选择：

- **Wireshark** -网络协议分析软件，我们都知道并且最爱。
- **tshark** -命令行的网络协议分析软件。如果您还没有尝试过，您应该试试。
- **Wireshark 1 Legacy** -旧的（GTK +）用户界面的情况下您需要它。
- **插件和扩展** -Wireshark的tshark的解析引擎扩展
 - **解析器插件** -扩展解析器的插件。
 - **树统计插件** -扩展统计信息。
 - **MetaMeta分析和追踪引擎** -用户可配置的显示筛选器引擎的扩展，见<https://wiki.wireshark.org/Mate>了解详细信息。
 - **SNMP MIB** -SNMP MIB进行更详细的SNMP解析。
- **工具** -捕获文件的附加命令行工具
 - **Editcap** -读取捕捉文件，并写入部分或全部包到另一个捕获文件。
 - **Text2Pcap** -读入ASCII hex dump，将数据写入到一个pcap捕获文件。
 - **Reordercap** -根据时间戳对捕捉文件重新排序。
 - **Mergecap** -将多个保存的捕获文件合并成一个单一的输出文件。
 - **Capinfos** -提供捕获文件的信息。
 - **Rawshark** -原始数据包筛选器。
- 用户指南 -用户指南的本地安装。如果没有本地安装的用户指南，在大多数对话框中的帮助按钮将需要连接到互联网显示帮助页面。

#### 2.3.2. 其他任务 ####

- **开始菜单快捷方式** -添加开始菜单的快捷方式。
- **桌面图标** -添加Wireshark的图标到桌面。
- **快速启动图标** -增加一个Wireshark的图标到快速启动工具栏。
- **关联文件扩展名到Wireshark** -关联标准的网络跟踪文件到Wireshark。

#### 2.3.3. 安装位置 ####

默认情况下Wireshark在32位Windows上安装到的％ProgramFiles％\ Wireshark目录，在64位Windows上安装到％ProgramFiles64％\ Wireshark 目录。大部分系统上扩展到 C:\Program Files\Wireshark 。

#### 2.3.4. 安装 WinPcap ####

Wireshark安装包含了最新的WinPcap安装程序。

如果您没有安装WinPcap的，您将无法捕捉网络流量，但您仍然可以打开保存的捕获文件。默认情况下WinPcap的最新版本将被安装。如果您不希望这样做，或者如果您想重新安装WinPcap，您可以根据需要选择安装WinPcap的复选框。

有关WinPcap的更多信息，请参阅

 <https://www.winpcap.org/> 和 <https://wiki.wireshark.org/WinPcap>。

#### 2.3.5. Windows Installer命令行选项 ####

对于特殊情况下，也有一些命令行参数可供选择：

- /S 用默认值静默运行安装程序或卸载程序。静默安装程序将不会安装WinPcap。
- /desktopicon 桌面图标安装，=yes -强制安装，=no 不安装，否则使用默认的设置。此选项对静默安装非常有用。
- /quicklaunchicon 将安装快速启动图标，=yes -强制安装，=no 不安装，否则使用默认的设置。
- /D 设置默认安装目录（$ INSTDIR），覆盖InstallDir 和 InstallDirRegKey。它必须是在命令行中使用的最后一个参数，并且不得包含任何引号即使路径包含空格。
- /NCRC 禁止CRC校验。我们不建议使用此标志。

例如：

    > Wireshark-win64-wireshark-2.0.5.exe /NCRC /S /desktopicon=yes /quicklaunchi
    con=no /D=C:\Program Files\Foo
不带任何参数运行安装程序显示正常的交互式安装程序。

#### 2.3.6. 手工安装 WinPcap ####

如上所述，Wireshark的安装程序会安装WinPcap。只有在您想使用一个和包含在安装程序中的不同版本，例如，因为发布了一个新的WinPcap版本。

单独的WinPcap版本（包括更新的α或β版本）可以从WinPcap的网站下载

 <https://www.winpcap.org/>。Windows的安装程序支持现代的Windows操作系统。

#### 2.3.7. 更新 Wireshark ####

默认情况下，官方的Windows程序包将检查新版本，当新版本可用时会通知您。如果“检查更新”被禁用，或者如果您在一个孤立的环境中运行Wireshark，您应该订阅到 wireshark-announce邮件列表。 参见  1.6.5节, “邮件列表” 的订阅列表的详细信息。

Wireshark的新版本，通常每4至6周发布。更新Wireshark和安装的方式一样。只需下载和启动安装程序文件。通常不需要重新启动，所有的个人设置保持不变。

#### 2.3.8. 更新 WinPcap ####

WinPcap的新版本不会频繁更新。您可以在WinPcap的网站 <https://www.winpcap.org/>发现WinPcap的更新说明。您可能在安装新版本的WinPcap后，必须重新启动计算机。

#### 2.3.9. 卸载 Wireshark ####

您可以使用程序和功能控制面板来卸载Wireshark。选择“Wireshark”条目开始卸载程序。

Wireshark的卸载程序提供了几个选项。默认值是删除核心组件，但保留个人设置和WinPcap。WinPcap默认情况下会保留，防止其他程序需要使用它。

#### 2.3.10. 卸载 WinPcap ####

您可以使用程序和功能控制面板来独立卸载WinPcap。请记住，如果您卸载WinPcap，您将不能使用Wireshark捕获任何东西。

### 2.4. 在Mac OS X下安装 Wireshark ###

官方的Mac OS X软件包以包含程序安装程序的磁盘映像文件（.dmg）来发布。要安装Wireshark，只需打开磁盘映像并运行封装的安装程序即可。

安装程序包包括Wireshark、相关命令行实用程序、以及在系统启动时调整捕获权限的守护进程。请参阅附带的“首先阅读”了解详情。

### 2.5. 在UNIX下从源码编译 Wireshark ###

编译Wireshark需要适当的编译环境，包括编译器和许多支持库。请参阅开发人员指南 <https://www.wireshark.org/docs/> 了解更多信息。

在UNIX或Linux下使用下面的步骤从源代码编译Wireshark：


1.从压缩的tar文件解压缩源代码。如果您使用的是Linux或您的UNIX版本使用GNU 的tar，您可以使用下面的命令：

    $ tar xaf wireshark-2.0.5.tar.bz2

在其他情况下，您将不得不使用下面的命令：

    $ bzip2 -d wireshark-2.0.5.tar.bz2
    $ tar xf wireshark-2.0.5.tar
2.更改目录到Wireshark源代码目录。

    $ cd wireshark-2.0.5

3.配置您的源，它会为您的UNIX版本正确编译。您可以用下面的命令： 

    $ ./configure

如果这一步失败，您将不得不纠正问题并重新configure。故障排除提示在 2.7节, “Unix安装过程中故障排除”。

4.编译源代码。

    $ make

5.在最终目的地安装软件。 

    $ make install

如果您已经按照以上的make install安装了Wireshark，您应该能够输入Wireshark来运行它。

### 2.6. 在UNIX下安装二进制包 ###

通常，安装您的UNIX版本的二进制包的方法将与您的UNIX版本相关。例如，AIX下，您可以使用smit来安装Wireshark的二进制包，在Tru64 UNIX的（原Digital UNIX）您会使用setld。

#### 2.6.1. 在Red Hat 及类似系统下从rpm安装 ####

使用以下命令来安装您从Wireshark的网站上下载的Wireshark RPM：

    rpm -ivh wireshark-2.0.5.i386.rpm

如果由于缺少依赖包导致上面的步骤失败，首先安装依赖包，然后重试以上步骤。

#### 2.6.2. 在Debian, Ubuntu 及其他 Debian 衍生系统下从deb安装 ####

如果您可以从库中安装，然后使用

    $ aptitude install wireshark

Aptitude 应该为您处理所有的依赖问题。

使用以下命令在Debian下安装下载的Wireshark Deb：

    $ dpkg -i wireshark-common_2.0.5.0-1_i386.deb wireshark_wireshark-2.0.5.0-1_i386.deb

dpkg 不处理所有的依赖性，但报告缺少了什么。

[Note]	捕捉需要的权限
通过安装Wireshark，非root用户不会自动获得捕获数据包的权限。遵循/usr/share/doc/wireshark-common/README.Debian中所述的方法来允许非root用户捕获数据包。

#### 2.6.3. 在Gentoo Linux下从portage安装 ####

使用下面的命令在Gentoo Linux下安装Wireshark的所有的额外功能：

    $ USE="adns gtk ipv6 portaudio snmp ssl kerberos threads selinux" emerge wireshark

#### 2.6.4. 在FreeBSD下从packages安装 ####

使用下面的命令在FreeBSD下安装Wireshark：

    $ pkg_add -r wireshark

pkg_add 应该为您处理所有的依赖问题。

### 2.7. Unix安装过程中故障排除 ###

在安装过程中会发生很多错误。此处提供了解决这些错误的一些提示。

如果 configure 阶段失败，您需要找出原因。您可以在源目录下检查文件config.log，找出失败的地方。该文件的最后几行应可以帮助确定问题。

标准的问题是，您的系统没有所需的开发包或者开发包不够新。请注意，仅安装库是不够的。您需要同时安装开发包。如果您的系统没有libpcap（至少需要包含文件），configure将会失败。

如果您不能确定什么问题，请发邮件到 *wireshark-dev*的邮件列表说明您的问题。包括从config.log的输出和其他任何您认为相关的信息，例如 make阶段的跟踪信息。

### 2.8. 在Windows上从源代码编译 Wireshark ###

我们强烈建议您使用二进制的Windows安装程序，除非您想开始在Windows平台上开发Wireshark。

欲了解更多如何在Windows下从源代码编译Wireshark，请参考开发人员指南：
<https://www.wireshark.org/docs/>

您可能也想看看开发维基 (<https://wiki.wireshark.org/Development>) 获取最新的可用开发文档。
