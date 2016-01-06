title: Chapter 4. 捕获实时网络数据
date: 2016-01-06 14:18:23
---
### 4.1. 介绍 ###

捕捉实时网络数据是Wireshark的主要功能之一。

Wireshark的捕获引擎提供了以下功能：

- 捕获从不同种类的网络硬件，如以太网或802.11。
- 根据不同的触发条件来停止捕获，如捕获数据的量、经过时间、或数据包的数目。
- 当Wireshark在捕获的同时显示解码数据包。
- 过滤数据包，减少捕获的数据量。参见  4.13节, “捕获时过滤”。
- 在进行长期捕获时在多个文件中保存数据包，可以在固定数量的文件间进行轮转（“环形缓冲”）。参见 4.11节, “捕获文件盒文件模式”。
- 从多个网络接口同时捕获。

捕获引擎仍然缺乏以下功能：

- 根据所捕获的数据来停止捕获（或执行一些其他动作）。

### 4.2. 先决条件 ###

设置Wireshark来进行第一次捕获数据包可能会比较棘手。综合指南“如何设置捕获”可在https://wiki.wireshark.org/CaptureSetup获得。

下面是一些常见的陷阱：

- 您可能需要特殊的权限启动实时捕捉。
- 您需要选择正确的网络接口来捕获数据包。
- 您需要在网络的正确地方来捕获，以查看到您希望的流量。

如果您设置您的捕获环境时有任何问题，您应该看看上面提到的指南。

### 4.3. 启动捕获 ###

可以使用下面的方法来启动Wireshark进行捕获数据包：

- 您可以双击主窗口上的接口。
- 您可以使用You can get an overview of the available interfaces using the “Capture Interfaces/捕获接口” 对话框 (Capture/捕获 → Options/选项…)来获取可用接口的概述。 参见 图 4.1, “ 微软Windows下“Capture Interfaces/捕获接口” 对话框 ” 或 图 4.2, “ Unix/Linux下“Capture Interfaces/捕获接口” 对话框 ” 获取更多信息。您可以使用该对话框的Start/开始按钮来开始捕获。
- 您可以通过选择 Capture/捕获 → Start/开始或点击第一个工具栏按钮，使用当前设置立即开始捕获。
- 如果你已经知道捕获接口的名称，你可以通过命令行启动Wireshark： 

    $ wireshark -i eth0 -k

这将在接口eth0上启动Wireshark捕获。更多详细信息可以在这里找到 10.2节, “从命令行启动 Wireshark”。

### 4.4. “Capture Interfaces/捕获接口” 对话框 ###

当您从Wireshark的主菜单中选择 Capture/捕获 → Options/选项… ，将弹出 “Capture Interfaces/捕获接口” 对话框 如 图 4.1, “微软Windows的“Capture Interfaces/捕获接口” 对话框” 或 图 4.2, “Unix/Linux的“Capture Interfaces/捕获接口” 对话框 ”。

[Note]	您和您的操作系统可以隐藏接口
该对话框只显示Wireshark可以访问的本地接口。它将隐藏在 10.5.1节, “接口选项”中被标记为隐藏的接口。Wireshark可能无法检测到所有的本地接口，它也不能检测到可用的远程接口，有可能存在比列出来更多的捕获接口。

可以同时选择多个接口并同时进行捕获。

图 4.1. 微软 Windows下“Capture Interfaces/捕获接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-interfaces-win32.png %} wsug_graphics/ws-capture-interfaces-win32.png

图 4.2. Unix/Linux下 “Capture Interfaces/捕获接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-interfaces.png %}

*Device /设备(只在Unix/Linux )*
接口设备名称。

*Description /描述*
由操作系统提供的接口描述，或者在 10.5.1节, “Interface Options/接口选项”中添加的用户定义的注释。

*IP*

Wireshark能发现的这个接口的第一个IP地址。您可以在地址上点击来循环显示分配给它的其他地址。如果没有地址被发现，“none/无”将被显示。 

*Packets /数据包*

自打开此对话框以来，从这个接口捕获的数据包的数量。如果在最后一秒没有数据包被抓获，将显示为灰色。

*Packets/s / 数据包/秒*

在最后一秒捕获的数据包的数量。如果在最后一秒没有数据包被抓获，将显示为灰色。

*Stop /停止*

停止当前运行的捕捉。 

*Start / 开始*

立即开始在所有选定的接口上进行捕获，如果没有选项被设置将使用最后捕获设置或默认设置。

*Options /选项*
打开标记接口的捕捉选项对话框 。参见  4.5节, “ “Capture Options/捕获选项” 对话框”.

*Details (Microsoft Windows only) / 详细信息（只在微软Windows）*

打开该接口的详细信息对话框。参见  4.10节, “ “Interface Details/接口详细信息” 对话框”。

*Help / 帮助*

显示此帮助页面。

*Close / 关闭*

关闭此对话框。

###　4.5. “Capture Options/捕获选项” 对话框

当您选择 Capture/捕获 → Options/捕获… (或者使用主工具栏对应项)， Wireshark 弹出 “Capture Options/捕获选项” 对话框如 图 4.3, “ “Capture Options/捕获选项” 对话框”所示。

图 4.3.  “Capture Options/捕获选项” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options.png %}

[Tip]	提示
如果您不确定选择哪个选项，在此对话框中尽量保持默认值，因为这应该可以在很多情况下很好地工作。

#### 4.5.1. Capture/捕获区

表格显示所有可用接口的设置：

- 接口名称和它的IP地址。如果没有地址可以从系统中获取，将显示“none/无”。

[Note]	注意
Windows 平台不支持环回接口。


- 链路层包头类型。

- promicuous模式是否启用或禁用的信息。

- 将要捕获的数据包的最大数据的数量。默认值设置为65535字节。

- 预留用以保存捕获的数据包的内核缓冲区的大小。

- 数据包是否在监控模式被捕获的信息（仅Unix / Linux）。

- 所选择的捕获筛选器。

通过标记第一列的复选框，接口被选择为捕获接口。通过在接口上双击将弹出“Edit Interface Settings/编辑接口设置”对话框， 图 4.4, ““Edit Interface Settings/编辑接口设置” 对话框” 将会打开。

*Capture on all interfaces / 捕获所有接口*

作为Wireshark的可以在多个接口上捕获，它可以选择在所有可用的接口上捕获。

*Capture all packets in promiscuous mode / 混杂模式下捕获所有数据包*

此复选框允许您指定Wireshark在捕获时，将所有接口设置为混杂模式。

*Capture Filter / 捕获筛选器*

此字段允许您对于当前选择的所有接口指定一个捕获筛选器。一旦筛选器在这个字段中输入，新选定的接口将继承筛选器。捕获筛选器的更多细节将在   4.13节, “Filtering while capturing/捕获时过滤”中讨论。 它默认为空，没有筛选器。

您也可以点击**Capture Filter/捕获筛选**按钮，Wireshark将会弹出“Capture Filters/捕获筛选器”对话框，并允许您创建或选择一个筛选器。请参见  6.6节, “Defining and saving filters/定义和保存筛选器”

*Compile selected BPFs / 编译所选BPF*

该按钮可以编译捕获筛选器为BPF代码，并弹出您所得到的伪代码的窗口。这可以帮助我们理解您所创建的捕获筛选器的工作。该**Compile Selected BPFs/编译所选BPF**按钮打开  图 4.5, “The “Compile Results” 对话框”.

[Tip]	提示
Linux 高级用户提示

在Linux上，BPF的执行可以通过执行以下命令打开BPF JIT来加速：

    $ echo 1 >/proc/sys/net/core/bpf_jit_enable

如果尚未启用。为了使持久生效，您可以使用 sysfsutils。

*Manage Interfaces / 管理接口*

**Manage Interfaces/管理接口** 按钮打开 图 4.6, ““Add New Interfaces/添加新接口” 对话框” ，可以定义管道、本地接口扫描或隐藏、远程接口添加（仅Windows）。

#### 4.5.2. Capture Options/捕获文件区

有关捕获文件的使用解释在  4.11节, “捕获文件和文件格式”。

*File/文件*

此字段允许您指定将用于捕捉文件的文件名 ​​。此字段保留默认为空。如果该字段为空，捕获的数据将被存储在一个临时文件。 详细信息参见  4.11节, “Capture files and file modes”。

您也可以点击该字段右侧的按钮，来浏览文件系统。

*Use multiple files/使用多文件*

如果达到特定的触发条件，Wireshark将会自动切换到一个新文件来代替单文件。

*Use pcap-ng format/使用pcap-ng格式*

此复选框允许您指定Wireshark以pcap-ng格式来保存捕获的数据包。该下一代捕捉文件格式正在开发中。如果多个接口被选择用于捕获，此复选框默认设置。参见 https://wiki.wireshark.org/Development/PcapNg 获取关于 pcap-ng的详细信息。

*Next file every n megabyte(s) /下一个文件，每n兆字节*

仅多文件：达到指定的字节/千字节/兆字节/千兆字节被捕获后，切换到下一个文件。 

*Next file every n minute(s) / 下一个文件，每n分钟*

仅多文件：经过指定的秒/分钟/小时后，切换到下一个文件。

*Ring buffer with n files / n个文件的环形缓冲*

仅多文件：使用指定数量的文件为捕获文件构成一个环形缓冲。

*Stop capture after n file(s) / 经过n个文件，停止捕获*

仅多文件：切换给定次数到下一个文件后停止捕获。

#### 4.5.3. Stop Capture/停止捕获… 区

*… after n packet(s) / 经过n个数据包*

经过给定数量的数据包被捕获后停止捕获。

*… after n megabytes(s) / 经过n兆字节*

经过给定的 字节/千字节/兆字节/千兆字节后停止捕获。如果“Use multiple files/使用多文件”被选中，这个选项是灰色的。

*… after n minute(s) / 经过n分钟*

经过给定的秒/分钟/小时后停止捕获。

#### 4.5.4. Display Options/显示选项区

*Update list of packets in real time /  实时更新数据包列表*

这个选项允许您指定Wireshark实时更新数据包列表窗格。如果不指定，直到您停止捕获Wireshark不会显示任何数据包。当您选择该项，Wireshark在一个单独的进程中捕获，并将捕获的信息反馈给显示进程。

*Automatic scrolling in live capture / 实时捕获自动滚动*

这个选项允许您指定Wireshark在收到新的数据包后滚动数据包列表窗格，这样您总是能看到最新的数据包。如果不指定此项，Wireshark简单地增加新的数据包到列表的末尾，但并不滚动数据包列表窗格。如果“Update list of packets in real time/实时更新数据包列表”被禁用，该选项为灰色。

*Hide capture info dialog / 隐藏捕获信息对话框*

如果选中该选项，在  4.14节, “While a Capture is running/当捕获在运行 …” 描述的捕获信息对话框将被隐藏。

#### 4.5.5. Name Resolution/名称解析区

*Enable MAC name resolution/使能MAC名称解析*

这个选项允许您控制Wireshark是否将MAC地址翻译为名称。 参见  7.7节, “名称解析”。

*Enable network name resolution/使能网络层名称解析*

这个选项允许您控制Wireshark是否将网络层地址翻译为名称。参见  7.7节, “名称解析”。

*Enable transport name resolution/使能传输层名称解析*

这个选项允许您控制Wireshark是否将传输层地址翻译为协议。参见  7.7节, “名称解析”。

### 4.5.6. 按钮 ###

一旦您设置您想要的值，并选择您需要的选项，只需点击**Start/开始**来开始捕获或**Cancel/取消**来取消捕获。

如果您开始捕获，当您获取足够的捕获数据包后，Wireshark允许您停止捕获，详见4.14节, “当捕获正在运行 …”。

### 4.6. “Edit Interface Settings/编辑接口设置” 对话框 ###

如果您双击 图 4.3, ““Capture Options/捕获选项” 对话框” 中的接口，以下对话框会弹出来。

图 4.4.  “Edit Interface Settings/编辑接口设置” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-settings.png %} 

您可以在该对话框中设置以下字段：

*IP address / IP地址*
所选接口的IP地址。如果没有地址能够从系统中解析到， 将显示“none/无”。

*Link-layer header type / 链路层包头类型*
除非您是在很罕见的情况下，请保持该项为默认设置。详细的描述，参见  4.12节, “Link-layer header type/链路层包头类型”

*Wireless settings (Windows only) / 无线设置（仅Windows）*
在这里，您可以设置使用AirPCap适配器的无线捕获设置。有关详细说明请参见AirPCap用户指南。

*Remote settings (Windows only) / 远程设置（仅Windows）*
在这里，您可以进行远程捕获的设置。有关详细说明，参见 4.9节, ““Remote Capture Interfaces/远程捕获接口” 对话框”

*Capture packets in promiscuous mode / 使用混杂模式捕获数据包*
此复选框允许您指定Wireshark捕获时将接口置为混杂模式。如果不指定此项，Wireshark将只捕获您的计算机收到和发送的数据包（而不是您的局域网段中的所有数据包） 。
[Note]	注意
如果一些其他进程已经把接口置为混杂模式，您也将在混杂模式下捕获，即使您关闭此选项。
即使在混杂模式，您也未必能够看到您的局域网段的所有报文。 参见 Wireshark FAQ 获取更多信息。

*Limit each packet to n bytes / 限制每个数据包为n字节*
此字段允许您指定的被捕获的每个数据包的最大数量，并且有时被称为快照。如果禁用的话，该值被设置为最大的65535，这将足以满足大多数协议。一些经验法则：
- 如果您不确定，保持默认值即可。
- 如果您不需要或不想要数据包中所有的数据 - 例如，如果您只需要链路层，IP和TCP报头 - 您可能想选择一个小的快照长度，因为更少的CPU时间来复制数据包，更少的缓冲空间分配给数据包，如果流量十分大时，也许会有更少的数据包被丢弃。
- 如果您不捕获数据包中的所有数据，您可能会发现您想要的数据是在丢弃的部分或不可能进行重组，因为重组需要的数据丢失了。

*Buffer size: n megabyte(s) / 缓冲大小：n 兆字节*
输入捕捉时所使用的缓冲区的大小。这是用来保存捕获数据包的内核缓冲区的大小，直到它们被写入磁盘。如果您发现丢包，尝试增加该值。 

*Capture packets in monitor mode (Unix/Linux only) / 监控模式下捕获数据包*
此复选框允许您设置无线接口捕获所有可以接收的流量，不只是与它相关联的BSS的流量，即使您设置成混杂模式也可以发生。此外它可能需要打开该选项，可以从捕获的帧中查看IEEE 802.11头和/或射频信息。
[Note]	注意
在监控模式下，适配器可能会从它所关联的网络上解关联。

*Capture Filter / 捕获筛选器*
此字段允许您指定捕获筛选器。捕获筛选器的更多细节将在  4.13节, “Filtering while capturing/捕获时过滤”讨论。 它默认为空，或者没有筛选器。
您也可以点击Capture Filter/捕获筛选器按钮，Wireshark会弹出“Capture Filters/捕获筛选器”对话框，允许您创建或选择一个筛选器。请参见  6.6节, “Defining and saving filters/定义和保存筛选器”

*Compile BPF / 编译BPF*
该按钮可以编译捕获筛选器为BPF代码，并弹出窗口显示结果伪代码。这可以帮助理解您所创建的捕获筛选器的工作。
 
### 4.7. “Compile Results/编译结果” 对话框

此图显示了所选接口的编译结果。

图 4.5.  “Compile Results/编译结果” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-compile-selected-bpfs.png %} 

在左侧窗口中的接口名称被列出。当接口被选中时，结果被显示在右边的窗口中。

### 4.8. “Add New Interfaces/添加新接口” 对话框

作为管理接口的中心，此对话框有三个选项卡来添加或删除接口。

图 4.6.  “Add New Interfaces/添加新接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-manage-interfaces.png %} 

#### 4.8.1. 添加或删除管道

图 4.7. “Add New Interfaces - Pipes/添加新接口-管道” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-manage-interfaces-pipes.png %} 

要成功添加一个管道，该管道必须已经创建。点击 **New/新建**按钮，然后键入包含路径的管道名称。可替代地，使用**Browse/浏览**按钮可用于定位管道。使用**Save/保存**按钮，管道被添加到可用接口的列表。之后，其他管道可以被添加。

要从接口列表中删除管道，它首先必须被选中。然后单击**Delet/删除**按钮。

#### 4.8.2. 添加或隐藏本地接口

图 4.8. “Add New Interfaces - Local Interfaces/添加新接口-本地接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-manage-interfaces-local.png %} 

标签“Local Interfaces/本地接口”包含可用本地接口列表，包括不会在其他列表中显示的隐藏接口。

如果一个新的本地接口被添加，例如，一个无线接口被激活，它不会自动添加到列表中，以防止持续地对可用接口的列表的​​改变进行扫描。重新扫描可以更新列表。

隐藏接口的一种方法是修改偏好设置。如果“Hide/隐藏”复选框被激活，单击**Apply/应用**按钮，接口将不会出现在“Capture Interfaces/捕捉接口”对话框的列表中了。这些变化也保存在偏好设置文件中。

#### 4.8.3. 添加或隐藏远程接口

图 4.9.  “Add New Interfaces - Remote Interfaces/添加新接口-远程接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-manage-interfaces-remote.png %} 

在这个选项卡上，可以添加远程主机接口。其中一个或多个接口可以被隐藏。与本地接口相比，他们不会保存在偏好设置文件中。

要从接口列表中删除主机及它所有接口，它首先必须被选中。然后单击**Delet/删除**按钮。删除主机包括从列表中的所有接口，它必须被选定。然后单击删除按钮。

详细描述参见  4.9节, “ “Remote Capture Interfaces/远程捕获接口” 对话框”

### 4.9. “Remote Capture Interfaces/远程捕获接口” 对话框

除了在本地接口上捕获，Wireshark是能够跨越网络到达所谓的捕获守护程序或服务进程，来接收捕获的数据。

[Note]	仅微软Windows 
此对话框和功能仅适用于微软Windows操作系统。在Linux / Unix系统可以通过SSH隧道来达到相同的效果（安全）。

在Wireshark连接之前，远程数据包捕获协议服务必须首先在目标平台上运行。最简单的方法是在目标计算机上从 https://www.winpcap.org/install/ 安装WinPcap。 一旦安装完成后进入服务控制面板，找到远程数据包捕获协议服务并启动它。

[Note]	注意
请确保您可以外部访问目标平台的端口2002。这是远程数据包捕获协议服务的默认使用的端口。

要访问的远程捕获接口对话框使用 “Add New Interfaces - Remote/添加新接口-远程” 对话框。 参见 图 4.9, “ “Add New Interfaces - Remote Interfaces/添加新接口-远程接口” 对话框” 并选择 Add/添加。

#### 4.9.1. 远程捕获接口

图 4.10. “Remote Capture Interfaces/远程捕获接口” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-manage-interfaces-remote-plus.png %} 

您必须设置此对话框中的下列参数：

*Host / 主机*

输入远程数据包捕获协议服务正在监听的目标平台的IP地址或主机名。下拉式列表中包含先前已成功连接的主机。该列表可以从下拉列表中选择“Clear list/清除名单”来清空。

*Port / 端口号*

设置远程数据包捕获协议服务正在侦听的端口号。不设置的话将使用默认端口号 (2002)。

*Null authentication / 空验证*

如果您不需要需要身份验证来启动捕获的话，请选择此项。这取决于目标平台。像这样配置目标平台使得它不安全。 

*Password authentication / 密码验证*

这是在连接到目标平台的正常方式。设置连接到远程数据包捕获协议服务所需的凭据。 

#### 4.9.2. 远程捕获设置

远程捕获可以进一步微调，以匹配您的情况。图 4.4, “ “Edit Interface Settings/编辑接口设置” 对话框”中的 Remote Settings/远程设置按钮提供这个选项。它弹出图 4.11, “ “Remote Capture Settings/远程捕获设置” 对话框”所示的对话框。

图 4.11. “Remote Capture Settings/远程捕获设置” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-options-remote-settings.png %} 

您可以在此对话框中设置以下参数：

*Do not capture own RPCAP traffic / 不捕捉自己的RPCAP流量*

此选项设置捕获筛选器，以便从远程数据包捕获协议服务传回Wireshark的回流流量不会被捕获及发回。重复的流量递归会使链路饱和。

You only should switch this off when capturing on an interface other than the interface connecting back to Wireshark.

*Use UDP for data transfer / 使用UDP数据传输*

远程捕获控的制和数据流通过TCP来连接。此选项允许您选择一个UDP数据流进行数据传输。 

*Sampling option None / 抽样选项  无*

此选项指示远程数据包捕获协议服务发送回所有通过捕获筛选器的捕获数据包。这在远程捕获会话具有足够带宽的情况下，不是问题。

*Sampling option 1 of x packets / 抽样选项  每x个数据包1个*

该选项限制远程抓包协议服务只发送所捕获数据的一个子取样，以数据包的数量为单位。这样可以通过窄带宽的远程捕获会话来捕捉更高带宽的接口。

*Sampling option 1 every x milliseconds  / 抽样选项  每x毫秒1个*

该选项限制远程抓包协议服务只发送所捕获数据的一个子取样，以时间为单位。这样可以通过窄带宽的远程捕获会话来捕捉更高带宽的接口。

### 4.10. “Interface Details/接口详细信息” 对话框

当您选择从"Capture Interface/捕获接口"菜单选择“Details/详细信息”时，Wireshark弹出如 图 4.12, “ “Interface Details接口详细信息” 对话框”所示的“Interface Details/接口详细信息"对话框。 这个对话框显示所选接口的各种特性和统计信息。

[Note]	仅微软Windows
此对话框仅微软Windows下可用

图 4.12.  “Interface Details/接口详细信息” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-interface-details.png %} 

### 4.11. 捕获文件和文件格式

在捕获时，底层的libpcap捕获引擎会从网卡抓取数据包，并将数据包数据保存在（相对）小的内核缓冲区。此数据由Wireshark读取并保存到用户指定的捕获文件。

将数据包数据保存到捕获文件时，可以使用不同的操作模式。

[Tip]	提示
处理大文件（几百MB）可能会相当的缓慢。如果您打算做长期捕获或从一个高流量的网络中捕获，考虑使用“多文件”选项。可以将捕获数据包分布在几个较小的文件，这可以更好的处理。

使用多个文件可能会丢失上下文相关信息。Wireshark保持加载的数据包数据的上下文信息，因此它可以报告上下文相关的问题（如流错误），并保持上下文相关的协议信息（例如，其中数据交换在建立阶段，只在后面的数据包中涉及到）。因为它只为加载的文件保持这些信息，使用多文件模式中的一种可能会丢失这些上下文。如果建立阶段被保存在一个文件中，您想看到的在另一个文件中，您可能看不到一些有价值的上下文相关的信息。

有关用于捕捉文件的文件夹信息，可参见 附录 B, 文件和文件夹。

表 4.1. 捕捉选项中的捕获文件模式
| “File/文件” 选项	| “Use multiple files/使用多文件” 选项	| “Ring buffer with n files/n个文件的环形缓冲” 选项 | 模式	| 使用的结果文件名 |
|:------------------|:--------------------------------------|:---------------------------------------------------|:-------|:---------------|
| - | - | - | 单个临时文件 | wiresharkXXXXXX (where XXXXXX is a unique number) |
| foo.cap | - | - | 单个命名文件 | foo.cap |
| foo.cap | x | - | 多文件，连续  | foo_00001_20100205110102.cap,foo_00002_20100205110318.cap, … |
| foo.cap | x | x | 多文件，环形缓冲 | foo_00001_20100205110102.cap,foo_00002_20100205110318.cap, … |

*单个临时文件*

临时文件将被创建并使用（默认）。捕获停止后，该文件以后可以根据用户指定的名称保存。

*单个命名文件*

单个捕获文件将被使用。如果您想放置新的捕获文件到特定文件夹中可以选择该模式。 

*多文件，连续*

类似“单个命名文件”模式，当达到多文件切换条件（“Next file every /下个文件每…”的值），一个新的文件被创建并使用。

*多文件，环形缓冲*

类似“多文件，连续”，当达到多文件切换条件（“Next file every /下个文件每…”的值），将切换到下一个文件。如果没有达到“n个文件的环形缓冲”的值将新创建文件，否则会取代以前旧的使用文件（从而形成一个“环”）。

该模式将限制最大磁盘使用情况，甚至无限量的捕获输入数据，只保留最新捕获的数据。

### 4.12. 链路层包头类型

在大多数情况下，您不必修改链路层包头类型。一些例外如下：

如果您正在捕获以太网设备，可能会提供“Ethernet”或“DOCSIS”的选择。如果您正在从思科电缆调制解调器终端系统捕获流量，该系统是把DOCSIS流量放到以太网流量中，选择“DOCSIS”，否则选择“以太网”。

如果您在某些BSD版本的802.11设备上捕获，可能会提供“Ethernet”或“802.11”的选择。“Ethernet”将导致捕获的数据包有假的（“cooked”）以太网头部。“802.11”将会导致他们有完整的IEEE 802.11头。除非捕获信息需要被不支持802.11头的应用读取，您应当选择呢“802.11”。

如果您在Endace DAG卡连接到同步串口线上捕获，可能会被提供“PPP over serial”或“Cisco HDLC”。如果串口线的协议是PPP，选择“PPP over serial”，如果在串行线路的协议是思科HDLC，选择“Cisco HDLC”。

如果您在Endace DAG卡连接到ATM网络上捕获，可能会提供“RFC 1483 IP-over-ATM”或“Sun raw ATM”的选择。如果被捕捉的通信是RFC 1483 LLC封装IP，或者捕获需要被不支持SunATM头的应用读取，选择“RFC 1483 IP-over-ATM”，否则选择“Sun raw ATM ”。


### 4.13. 捕获时过滤

Wireshark使用libpcap筛选器语言作为捕获筛选器。语法的简要概述如下。完整的文档可以在 pcap-filter man page找到。您可以在找到很多捕捉筛选器的例子在 https://wiki.wireshark.org/CaptureFilters。

您可以在Wireshark 的“Capture Options/捕获选项” 对话框的“筛选器”字段中输入捕获筛选器， 如 图 4.3, “ “Capture Options/捕获选项” 对话框”显示。

捕获筛选采用了一系列由连词（连接原始表达式的形式和/或）和任选前面没有A capture filter takes the form of a series of primitive expressions connected by conjunctions (and/or) and optionally preceded by not:

    [not] primitive [and|or [not] primitive ...]

例子参见 例 4.1, “特定主机telnet流量的捕获筛选器”。

**例 4.1. 特定主机telnet流量的捕获筛选器**

特定主机telnet流量的捕获筛选器

    tcp port 23 and host 10.0.0.5

这个例子捕捉所有发往和来自主机10.0.0.5的Telnet流量，并展示了如何使用两个原语以及and/与连接。另一个例子显示在 例 4.2, “捕获所有不来自10.0.0.5的telnet流量”， 并展示了如何捕获所有除了来自10.0.0.5的Telnet流量。

**例 4.2. 捕获所有不来自10.0.0.5的telnet流量Capturing all telnet traffic not from 10.0.0.5**

捕获所有不来自10.0.0.5的流量

    tcp port 23 and not src host 10.0.0.5

原语是下列之一： 

*[src|dst] host <host>*

该原语允许您可以对主机的IP地址或名称进行过滤。您可以选择在原语之前使用 src|dst关键字来指定您只关心源或目的地址。如果这些不存在，那么指定的地址出现在源或目的地址的数据包都将被选中。 

*ether [src|dst] host <ehost>*

该原语允许您可以对以太网主机地址进行过滤。可以选择在关键字ether 和 host之间使用 src|dst关键字来指定您只关心源或目的地址。如果这些不存在，那么指定的地址出现在源或目的地址的数据包都将被选中。  

*gateway host <host>*

该原语允许您对使用host作为网关的数据包进行过滤。也就是说，以太网源或目的地址是host，但IP地址的源或目的地址不是host 。

*[src|dst] net <net> [{mask <mask>}|{len <len>}]*

该原语允许您对网络号进行过滤。您可以选择在原语之前使用 src|dst关键字来指定您只关心源或目的地址。如果这些不存在，那么指定的地址出现在源或目的地址的数据包都将被选中。此外，如果网络和你自身网段不同，你可以指定网络掩码或CIDR前缀。

*[tcp|udp] [src|dst] port <port>*

该原语允许您对TCP和UDP端口号进行过滤。您可以选择在原语之前使用 src|dst关键字来指定您只关心源或目的地址，或使用 tcp|udp关键字来指定TCP或UDP数据包。关键字tcp|udp 必须在 src|dst之前。

如果这些都没有指定，当指定的地址出现在源或目的端口字段，TCP和UDP协议数据包都会被选中。

*less|greater <length>*

此原语允许你过滤报文的长度小于或等于指定的长度，或者大于或等于指定的长。

*ip|ether proto <protocol>*

此原语允许您在以太网层或IP层对指定协议进行过滤。 

*ether|ip broadcast|multicast*

此原语允许您可以对以太网、IP广播或多播进行过滤。 

*<expr> relop <expr>*

该原语允许你创建复杂的过滤表达式来选择数据包的字节或字节范围复杂。请参考pcap-筛选器帮助页面 http://www.tcpdump.org/manpages/pcap-filter.7.html 了解更多详情。

#### 4.13.1. 自动远程流量过滤 ####

如果Wireshark是远程运行（例如使用SSH，导出的X11窗口，终端服务器，...），远程内容必须通过网络传输，加入了很多（通常是不重要的）数据包到真正感兴趣的流量。

为了避免这种情况，Wireshark试图判断它是否是远程连接（通过看一些特定的环境变量），并自动创建一个筛选器来匹配连接。

对下面的环境变量进行分析：

SSH_CONNECTION (ssh)
<remote IP> <remote port> <local IP> <local port>
SSH_CLIENT (ssh)
<remote IP> <remote port> <local port>
REMOTEHOST (tcsh, others?)
<remote name>
DISPLAY (x11)
[remote name]:<display num>
SESSIONNAME (terminal server)
<remote name>
在Windows上，它查询操作系统是否在远程桌面服务环境中运行。

### 4.14. 当捕获正在运行时 …

当捕获在运行时，显示下面的对话框：

图 4.13. “Capture Info/捕获信息” 对话框
{% img /Wireshark/manual-cn-img/ws-capture-info.png %} 

此对话框将告知您捕获的数据包的数量和自捕获开始的时间。其中选择哪些协议进行计数，是不能修改的。

[Tip]	提示
“Capture Info/捕获信息” 对话框可以使用“捕获选项” 对话框的“Hide capture info dialog / 隐藏捕获信息对话框” 选项来隐藏。

#### 4.14.1. 停止运行的捕获 ####

正在运行的捕获会话可以通过下列方式之一来停止：

1. 使用按键： “Capture Info/捕获信息” 对话框的[Stop/停止]按键。

[Note]	注意
如果“Hide capture info dialog / 隐藏捕获信息对话框” 选项被使用，“Capture Info/捕获信息” 对话框可能被隐藏 。


1. 使用 Capture/捕获  → Stop/停止 菜单项。
2. 使用工具栏的 Stop/停止 按键。
3. 按 Ctrl+E。
4. 如果停止条件满足的话，捕获将自动停止，例如捕获数据量达到最大值。

#### 4.14.2. 重新启动运行的捕获 ####

正在运行的捕获会话可以使用上一次相同的捕获选项进行重启，这将消除先前捕获的所有数据包。如果不感兴趣的数据包被捕获并没有必要保留他们，这各功能将很有用。

重启是一个便利功能，相当于停止捕获后又立即开始捕获。重启可以通过以下方式之一来触发：

使用 **Capture/捕获 → Restart/重启** 菜单项。
使用工具栏的 **Restart/重启** 按键。
