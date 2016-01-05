title: Chapter 3. 用户界面
---
### 3.1. 介绍

现在，您已经安装了Wireshark并有可能热衷于开始捕捉您的第一个数据包。在接下来的章节中，我们将探讨：

- Wireshark的用户界面如何工作
- Wireshark如何捕获报文
- Wireshark如何查看报文
- Wireshark如何过滤报文
- ......和许多其他的事情！

### 3.2. 启动 Wireshark

您可以从您的shell或窗口管理器启动Wireshark。

[Tip]	重要用户提示
当启动Wireshark时，它可以使用命令行来指定可选设置。参考  10.2节, “从命令行启动Wireshark” 获取详细信息。

在下面的章节中会显示很多Wireshark的截图。Wireshark运行在许多不同的平台上有很多不同的窗口管理器，具有不同风格应用和不同版本的底层图形界面工具包被使用，您的屏幕可能与所提供的截图不同。但是，在功能上没有实质的差异，这些截图应该还是很好理解的。

### 3.3. 主窗口

让我们来看看Wireshark的用户界面 。图 3.1, “主窗口” 显示的是一些数据包被捕获或加载（如何做到这一点稍后将描述），您通常看到的界面。

图 3.1. 主窗口
{% img /Wireshark/manual-cn-img/ws-main.png %}

Wireshark的主窗口包含了常见GUI程序的部件。

1. 菜单 (参考  3.4节, “菜单”) 用于启动操作。 
1. 主工具栏 (参考 3.16节, ““主” 工具栏”) 提供快从菜单中速访问经常使用的项目。 
1. 筛选器工具栏 (参考 3.17节, “ “筛选器” 工具栏”)提供了一种直接操纵当前使用的显示筛选器的方式 (参考  6.3节, “浏览时过滤数据包”)。
1. 数据包列表窗格 (参考 3.18节, ““数据包列表” 窗格”) 显示捕获的每个数据包的摘要。点击此窗格中的数据包，您可以控制什么显示在其他两个窗格。 
1. 数据包详细信息窗格 (参考  3.19节, “The “数据包详细信息” 窗格”) 显示数据包列表窗格中选择的包的更详细的信息。
1. 数据包字节窗格 (参考 3.20节, “ “数据包字节” 窗格”)显示数据包列表窗格中选择的数据包的数据，并高亮显示在数据包详细信息窗格中选择的字段。 
1. 状态栏(参考 3.21节, “状态栏”)显示有关当前程序状态和捕获数据的一些详细信息。

[Tip]	提示
通过修改偏好设置可以定制主窗口的布局。参考 10.5节, “偏好设置” 获取详细信息。

#### 3.3.1. 主窗口导航

数据包列表和详细信息的导航可以完全从键盘进行。 表 3.1, “按键导航” 显示了可以让您在捕获文件中快速移动的按键列表。 参考 表 3.5, “跳转菜单项目” 获取额外的导航按键。

表 3.1. 按键导航

| 快捷方式   |描述           |
|:----------|:-------------|
| Tab, Shift+Tab | 屏幕元素之间移动，例如，从工具栏到数据包列表到数据包详细信息。|
| Down           | 移动到下一个数据包或详细项目。|
| Up             | 移动到上一个数据包或详细项目。|
| Ctrl+Down, F8  | 移动到下一个数据包，即使数据包列表不是焦点。|
| Ctrl+Up, F7    | 移动到前一个数据包，即使数据包列表不是焦点。 |
| Ctrl+.         | 移动到会话 (TCP, UDP or IP)的下一个数据包 |
| Ctrl+,         | 移动到会话 (TCP, UDP or IP)的前一个数据包 | 
| Left           | 在数据包详细信息中，关闭选中的树项目。如果已经关闭。跳转到父节点。 |
| Right          | 在数据包详细信息中，打开选中的树项目。 |
| Shift+Right    | 在数据包详细信息中，打开选中的树项目及所有的子树。 |
| Ctrl+Right     | 在数据包详细信息中，打开所有的树项目。 |
| Ctrl+Left      | 在数据包详细信息中，关闭所有的树项目。 |
| Backspace      | 在数据包详细信息中，跳转到父节点。 |
| Return, Enter  | 在数据包详细信息中，切换所选树项目。 |


另外，在主窗口中的任何地方输入将开始在显示筛选器填充。

### 3.4. 菜单

Wireshark的主菜单位于主窗口（Windows，Linux）的顶部或在您的主屏幕（OS X）的顶部。一个例子示于 图 3.2, “菜单”.

[Note]	注意
一些菜单项将被禁用（灰色（如果相应的功能不可用。例如，如果您还没有捕获或加载任何数据包，您不能保存捕捉文件。））

图 3.2. 菜单
{% img /Wireshark/manual-cn-img/ws-menu.png %}

主菜单包含以下项目：

***File/文件***

该菜单包含打开和合并捕获文件、保存/打印/导出捕获文件的全部或部分、以及从Wireshark退出。参见  3.5节, “ “File/文件” 菜单”。

***Edit/编辑***

该菜单包含查找数据包、时间基准、标记一个或多个数据包、处理配置文件、设置您的偏好； （剪切、复制和粘贴功能当前没有实现）。参见  3.6节, ““Edit/编辑” 菜单”。

***View/视图***

该菜单控制捕获的数据的显示，包括数据包的着色，字体的缩放，在单独的窗口显示数据包，在数据包相信信息中展开和收缩信息。 参考  3.7节, ““View/视图” 菜单”。

***Go/跳转***

该菜单包跳转到特定的数据包的选择项。参见 3.8节, ““Go/跳转” 菜单”。

***Capture/捕获***

这个菜单可以启动、停止捕获和编辑捕获筛选器。参见  3.9节, ““捕获” 菜单”。

***Analyze/分析***

该菜单包含操作显示筛选器、启用或禁用协议解析器、配置用户指定解码器、追踪TCP流。参见 3.10节, “ “Analyze/分析” 菜单”。

***Statistics***

本菜单包含显示各种统计窗口，包括已捕捉数据包的概要，显示协议阶层统计等等。参见  3.11节, “ “Statistics/统计” 菜单”。

***Telephony/电话***

该菜单包含显示电话相关的统计窗口，包括媒体分析、流程图、显示协议阶层统计等等。参见  3.12节, “ “Telephony/电话” 菜单”。

***Tools/工具***

该菜单包含Wireshark中提供各种工具，例如创建防火墙ACL规则。参见  3.13节, ““Tools/工具” 菜单”。

***Internals/内部***

该菜单包含显示Wireshark相关的内部信息项。参见  3.14节, “ “Internals/内部” 菜单”。

***Help/帮助***

该菜单包含用户帮助信息，比如获得一些基本的帮助，各种命令行工具的手册页面，在线访问一些网页，以及关于对话框。参见  3.15节, ““Help/帮助” 菜单”。

这些菜单项在后面的章节中有更详细的描述。

[Tip]	重要用户提示
大多数菜单项具有键盘快捷键。例如，您可以同时按Control（或Strg在德国）和K键打开捕获对话框。

### 3.5. “File/文件” 菜单

Wireshark的文件菜单包含的字段显示在 表 3.2, “文件菜单项”。

图 3.3.  “File/文件” 菜单
{% img /Wireshark/manual-cn-img/ws-file-menu.png %}
表 3.2. 文件菜单项

| 菜单项	  | 快捷方式	     |描述                  |
|:----------------|:-----------------|:---------------------|
| Open…          | Ctrl+O         | 这个菜单项会弹出文件打开对话框，让您载入捕捉文件进行查看。更详细的内容在 5.2.1节, ““打开捕获文件” 对话框”。|
| Open Recent     |                | 该菜单项显示包含最近打开捕获文件的子菜单。点击子菜单中的项目，将直接打开相应的捕获文件。 |
| Merge…         |                | 此菜单项会弹出合并文件对话框，允许合并捕捉文件到当前加载的文件。更详细的内容在 5.4节, “合并捕获文件”。 |
| Import from Hex Dump…|       | 此菜单项将打开导入文件对话框，允许您导入包含hex dump的文本文件到一个新的临时捕获文件。更详细的内容在  5.5节, “导入 hex dump”. |
| Close       | Ctrl+W         | 这个菜单项关闭当前的捕获。如果您还没有保存捕获信息，会要求您首先进行保存。（这可以通过偏好设置来禁用）。 |
| Save        | Ctrl+S         | 该菜单项保存当前的捕获。如果您没有设置默认的捕获文件名 ​​（或许带有-w <capfile>选项），Wireshark弹出“另存捕获文件为”对话框 (进一步内容在  5.3.1节, “ “另存捕获文件为” 对话框”)。如果您已经保存了当前捕获信息，该菜单项将显示为灰色。当捕获正在进行时，您不能保存实时捕获信息。您必须先停止捕获，然后保存。 |
| Save As…    | Shift+Ctrl+S   | 该菜单项允许您保存当前捕获文件到任何您希望的文件。它弹出“另存捕获文件为”对话框。 (进一步内容在  5.3.1节, “ “另存捕获文件为” 对话框”)。 |
| File Set → List Files|       | 该菜单项允许您显示一个文件组的列表。它弹出“Wireshark文件组列表”对话框。(进一步内容在  5.6节, “文件组”). |
| File Set → Next File|        | 如果当前加载的文件是文件组的一部分，跳转到该组中的下一个文件。如果它不是文件组的一部分，或者是该组的最后一个文件，这个项目将显示为灰色。 |
| File Set → Previous File|    | 如果当前加载的文件是文件组的一部分，跳转到该组中的前一个文件。如果它不是文件组的一部分，或者是该组的第一个文件，这个项目将显示为灰色。 |
| Export → File… |             | 该菜单项可以导出所有（或部分）捕获文件中的数据包到文件。它弹出“Wireshark导出”对话框。 (进一步内容在  5.7节, “导出数据”)。 |
| Export → Selected Packet Bytes…| Ctrl+H | 该菜单项可以将在数据包字节窗格中当前选择的字节导出到一个二进制文件。它弹出Wireshark的“导出”对话框。 (进一步内容在  5.7.7节, “"导出选择的数据包字节" 对话框”) |
| Export → Objects → HTTP |    | 该菜单项可以导出所有或部分捕获的HTTP对象到本地文件。它弹出Wireshark的HTTP对象列表。 (进一步内容在  5.7.8节, “"导出对象" 对话框”) |
| Export → Objects → DICOM |   | 该菜单项可以导出所有或部分捕获的DICOM对象到本地文件。它弹出Wireshark的DICOM对象列表。 (进一步内容在  5.7.8节, “ "导出对象" 对话框”) |
| Export → Objects → SMB |     | 该菜单项可以导出所有或部分捕获的SMB对象到本地文件。它弹出Wireshark的SMB对象列表。 (进一步内容在  5.7.8节, “ "导出对象" 对话框”) |
| Print…      | Ctrl+P         | 此菜单项允许您打印捕获文件中的所有（或部分）数据包。它弹出Wireshark的“打印”对话框。 (进一步内容在  5.8节, “打印数据包”)。 |
| Quit        | Ctrl+Q         | 此菜单项允许您从Wireshark的退出。如果您以前没有保存它，Wireshark将要求保存捕获文件（这可以通过偏好设置来禁用）。 |


### 3.6.  “Edit/编辑” 菜单

Wireshark Edit/编辑 菜单包含字段显示在 表 3.3, “Edit/编辑 菜单项”。

图 3.4.  “Edit/编辑” 菜单
{% img /Wireshark/manual-cn-img/ws-edit-menu.png %}

表 3.3. Edit/编辑 菜单项

|菜单项           | 快捷方式       | 描述                 |
|:----------------|:---------------|:---------------------|
| Copy → 描述     | Shift+Ctrl+D   | 该菜单项将复制详细信息视图中所选项目的描述到剪贴板。 |
| Copy → Fieldname| Shift+Ctrl+F   | 该菜单项将复制详细信息视图中所选项目的字段名到剪贴板。 |
| Copy → Value    | Shift+Ctrl+V   | 该菜单项将复制详细信息视图中所选项目的值到剪贴板。 |
| Copy → As Filter| Shift+Ctrl+C   | 此菜单项将使用详细视图中所选的项目来创建一个显示筛选器。这个显示筛选器被复制到剪贴板。 |
| Find Packet…    | Ctrl+F         | 此菜单项将弹出一个对话框，允许您通过很多条件来查找数据包。进一步内容在  6.8节, “查找数据包”。 |
| Find Next       | Ctrl+N         | 此菜单项试图找到下一个匹配“查找数据包...”设置的数据包。 |
| Find Previous   | Ctrl+B         | 此菜单项试图找到前一个匹配“查找数据包...”设置的数据包。 |
| Mark/Unmark Packet | Ctrl+M      | 此菜单项标记当前选定的数据包。详情参见  6.10节, “标记数据包”  |
| Mark All Displayed Packets | Shift+Ctrl+M | 此菜单项标记所有显示的数据包。 |
| Unmark All Displayed Packets | Ctrl+Alt+M | 此菜单项取消标记所有显示的数据包。 |
| Next Mark       | Shift+Alt+N| 查找下一个标记数据包。 |
| Previous Mark   | Shift+Alt+B| 查找前一个标记数据包。 |
| Ignore/Unignore Packet       | Ctrl+D     | 此菜单项标记当前选择数据包为忽略。详情参考  6.11节, “忽略数据包” 。 |
| Ignore All Displayed         | Shift+Ctrl+D | 此菜单项标记所有显示数据包为忽略。 |
| Unignore All Displayed       | Ctrl+Alt+D   | 此菜单项取消标记所有忽略数据包。 |
| Set/Unset Time Reference     | Ctrl+T       | 此菜单项设置当前选择数据包为时间基准。 参见  6.12.1节, “数据包时间参考” 获取更多关于时间参考数据包的信息。 |
| Unset All Time References    | Ctrl+Alt+T   | 此菜单项删除所有的数据包时间参考。 |
| Next Time Reference          | Ctrl+Alt+N   | 此菜单项试图找到下一个时间参考数据包。 |
| Previous Time Reference      | Ctrl+Alt+B   | 此菜单项试图找到前一个时间参考数据包。 |
| Configuration Profiles…      | Shift+Ctrl+A | 此菜单项打开配置文件对话框。更多详细信息参考  10.6节, “配置文件”。 |
| Preferences…                 | Shift+Ctrl+P | 此菜单项将弹出一个对话框，允许您设置偏好选项中的参数来控制Wireshark。您还可以保存您的偏好设置，这样Wireshark下一次启动时您可以使用它。更多详细信息参考  10.5节, “偏好设置”。 |


### 3.7. “View/视图” 菜单

The Wireshark View 菜单 contains the fields shown in Table 3.4, “View 菜单项”.

图 3.5. The “View” Menu
{% img /Wireshark/manual-cn-img/ws-view-menu.png %}

表 3.4. View/视图 菜单项

| 菜单项	  | 快捷方式	   | 描述                 |
|:----------------|:---------------|:---------------------|
| Main Toolbar    |                | 此菜单项隐藏或显示主工具栏，参见  3.16节, “ “主” 工具栏”。|
| Filter Toolbar  |                | 此菜单项隐藏或显示筛选器工具栏，参见 3.17节, “ “筛选器”工具栏”。|
| Wireless Toolbar|                | 此菜单项隐藏或显示无线工具栏。在一些平台上可能不存在该项。|
| Statusbar       |                | 此菜单项隐藏或显示无线状态栏，参见  3.21节, “状态栏”。|
| Packet List     |                | 此菜单项隐藏或显示数据包列表窗格，参见  3.18节, “ “数据包列表” 窗格”。|
| Packet Details  |                | 此菜单项隐藏或显示数据包详细信息窗格，参见：  3.19节, “ “数据包详细信息” 窗格”。|
| Packet Bytes    |                | 此菜单项隐藏或显示数据包字节窗格, 参见  3.20节, ““数据包字节” 窗格”。|
| Time Display Format → Date and Time of Day: 1970-01-01 01:02:03.123456  | | 选择此项告诉Wireshark以 "Date and Time of Day"格式来显示时间戳，请参见 6.12节, “时间显示格式和参考”。字段 "Time of Day", "Date and Time of Day", "自捕获开始以来的秒数", "自上一个捕获数据包以来的秒数" 和 "自上一个显示数据包以来的秒数" 是互斥的。|
| Time Display Format → Time of Day: 01:02:03.123456                      | | 选择此项告诉Wireshark以 " Time of Day"格式来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Seconds Since Epoch (1970-01-01): 1234567890.123456 |   | 选择此项告诉Wireshark以 "自1970-01-01 00:00:00 以来的秒数"格式来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Seconds Since Beginning of Capture: 123.123456    | | 选择此项告诉Wireshark以 " 自捕获开始以来的秒数"格式来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Seconds Since Previous Captured Packet: 1.123456  | | 选择此项告诉Wireshark以 " 自上一个捕获数据包以来的秒数"格式来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Seconds Since Previous Displayed Packet: 1.123456 | | 选择此项告诉Wireshark以 " 自上一个显示数据包以来的秒数"格式来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Automatic (File Format Precision) | | 选择此项告诉Wireshark使用捕获文件给出的精度来显示时间戳，参见 6.12节, “时间显示格式和参考”。字段 "自动", "秒" 和 "…秒" 是互斥的。|
| Time Display Format → Seconds: 0             | | 选择此项告诉Wireshark以秒的精度来显示时间戳，参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → …seconds: 0….          | | 选择此项告诉Wireshark以秒、十分之一秒、百分之一秒、毫秒、毫秒、微秒、纳秒的精度来显示时间戳， 参见 6.12节, “时间显示格式和参考”。|
| Time Display Format → Display Seconds with hours and minutes |  | 选择此项告诉Wireshark带小时和分钟的秒来显示时间戳。|
| Name Resolution → Resolve Name               | | 此项可以让您仅触发当前包的名称解析，参见 7.7节, “名称解析”。|
| Name Resolution → Enable for MAC Layer       | | 此项允许您控制Wireshark是否讲MAC地址转换为名称， 参见  7.7节, “名称解析”。|
| Name Resolution → Enable for Network Layer   | | 此项允许您控制Wireshark是否将网络地址转换为名称， 参见  7.7节, “名称解析”。|
| Name Resolution → Enable for Transport Layer | | 此项允许您控制Wireshark是否将传输层地址转换为名称，参见  7.7节, “名称解析”。|
| Colorize Packet List        |                 | 此项允许您控制Wireshark是否对数据包列表着色。启用着色，会在捕获/加载捕获文件时减慢新包的显示。|
| Auto Scroll in Live Capture |                 | 当新数据包出现时，此项允许您指定Wireshark滚动数据包列表窗格，所以您一直看到的是最新的数据包。如果不指定此项，Wireshark只是添加新的数据包到列表的末尾，但并不滚动数据包列表窗格。|
| Zoom In                     | Ctrl++          | 放大数据包数据（增加字体大小）。|
| Zoom Out                    | Ctrl+-          | 缩小数据包数据（减小字体大小）。|
| Normal Size                 | Ctrl+=          | 设置缩放级别恢复到100％（设置字体大小恢复正常）。|
| Resize All Columns          | Shift+Ctrl+R    | 调整所有列的宽度，以便将内容适配它。调整大小可能需要大量时间，特别是如果一个大的捕获文件被加载时。|
| Displayed Columns           |                 | 此菜单项列出了所有配置的列。这些列现在可以在数据包列表中显示或隐藏。|
| Expand Subtrees             | Shift+→         | 此菜单项展开当前在数据包详细信息树选中的子树。|
| Collapse Subtrees           | Shift+←         | 此菜单项折叠当前在数据包详细信息树选中的子树。|
| Expand All      | Ctrl+→                      | Wireshark保持一个所有协议的扩展子树，并使用它来确保当显示一个数据包时正确的子树被扩展。此菜单项展开所有捕获数据包的所有子树。|
| Collapse All    | Ctrl+←     | 此菜单项折叠在捕获列表中的所有数据包的树视图。|
| Colorize Conversation |      | 此菜单项会弹出一个子菜单，让您在基于当前选定的数据包的地址对数据包列表窗格中的数据包着色。这使得易于区分属于不同的会话数据包。  10.3节, “数据包着色”。|
| Colorize Conversation → Color 1-10         |   | 这些菜单项能够基于当前选择的会话，使能十个临时着色筛选器中的一个。|
| Colorize Conversation → Reset coloring     |   | 此菜单项将清除所有临时着色规则。|
| Colorize Conversation → New Coloring Rule… |   | 此菜单项打开对话窗口，在该窗口中可以基于当前选定的会话创建一个永久的着色规则。|
| Coloring Rules… |                              | 此菜单项将弹出一个对话框，根据您选择的过滤表达式让您对数据包列表窗格中的数据包进行着色。它对标识特定类型的数据包非常有用，参见  10.3节, “数据包着色”。|    
| Show Packet in New Window       |              | 此菜单项可以在一个单独的窗口中打开选中的数据包。该单独的窗口中只显示树状视图和字节视图窗格。|
| Reload                          | Ctrl+R       | 此菜单项让您重新加载当前捕获文件。|

3.8.  “Go/跳转” 菜单

Wireshark Go/跳转菜单包含的字段显示在 表 3.5, “Go/跳转 菜单项”。

图 3.6.  “Go/跳转” 菜单
{% img /Wireshark/manual-cn-img/ws-go-menu.png %}

表 3.5. Go 菜单项

| 菜单项  	  | 快捷方式	   | 描述                 |
|:----------------|:---------------|:---------------------|
| Back            | Alt+←          | 跳转到数据包历史中最近访问的数据包，就像Web浏览器的历史页面一样。 |
| Forward 	  | Alt+→ 	   | 跳转到数据包历史中下一个访问的数据包，就像Web浏览器的历史页面一样。 |
| Go to Packet…   | Ctrl+G         | 弹出一个窗口，允许您指定一个数据包序号，然后跳转到该数据包。详细信息参见  6.9节, “跳转到特定数据包” 。 |
| Go to Corresponding Packet |     | 跳转到当前所选协议字段对应的数据包。如果选择的字段没有对应的数据包，这个项是灰色的。 |
| Previous Packet | Ctrl+↑         | 移动到列表中的前一个数据包。即使数据包列表不是键盘焦点，也可以用于移动到前一个数据包。 |
| Next Packet     | Ctrl+↓ 	   | 移动到列表中的下一个数据包。即使数据包列表不是键盘焦点，也可以用于移动到下一个数据包。 |
| First Packet    | Ctrl+Home 	   | 跳转到捕获文件的第一个数据包。 |
| Last Packet     | Ctrl+End 	   | 跳转到捕获文件的最后一个数据包。 |
| Previous Packet In Conversation  | Ctrl+, | 移动到当前回话的前一个数据包。即使数据包列表不是键盘焦点，也可以用于移动到前一个数据包。 |
| Next Packet In Conversation 	   | Ctrl+. | 移动到当前回话的下一个数据包。即使数据包列表不是键盘焦点，也可以用于移动到下一个数据包。 |

### 3.9. “Capture/捕获” 菜单

Wireshark Capture/捕获菜单包含的字段显示在 表 3.6, “Capture/捕获菜单项”。

图 3.7.  “Capture/捕获” 菜单
{% img /Wireshark/manual-cn-img/ws-capture-menu.png %}

表 3.6. Capture/捕获 菜单项

| 菜单项	  | 快捷方式	   | 描述                 |
|:----------------|:---------------|:---------------------|
| Interfaces…     | Ctrl+I | 此菜单项将弹出一个对话框，显示在网络接口上Wireshark知道的事情，参见T  4.4节, “ “捕获接口” 对话框”) 。 |
| Options…        | Ctrl+K | 此菜单项将打开“捕获选项”对话框 (进一步讨论在  4.5节, “ “捕获选项” 对话框”) ”），并允许您开始捕获数据包。 |
| Start           | Ctrl+E | 立即使用和上一次相同的设置启动捕获数据包。 |
| Stop            | Ctrl+E | 此菜单项停止当前正在运行的捕获， 参见  4.14.1节, “停止运行的捕获”)。. |
| Restart         | Ctrl+R | 此菜单项停止当前正在运行的捕获然后使用相同的选项重新开始，这仅仅是为了方便。 |
| Capture Filters… |       | 此菜单项将弹出一个对话框，允许您创建和编辑捕获筛选器。您可以命名筛选器，并可以将它们保存以备将来使用。关于这个问题的更多细节在  6.6节, “定义和保存筛选器” |


### 3.10. “Analyze/分析” 菜单

WiresharkAnalyze/分析菜单包含的字段显示在 表 3.7, “Analyze/分析 菜单项”.

图 3.8. “Analyze/分析” 菜单
{% img /Wireshark/manual-cn-img/ws-analyze-menu.png %}

表 3.7. Analyze/分析 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| Display Filters…       |                | 此菜单项弹出一个对话框，允许您创建和编辑显示筛选器。您可以命名筛选器，并可以保存他们以备将来使用。关于这个问题的更多细节在  6.6节, “定义和保存筛选器” |
| Display Filter Macros… |                | 此菜单项将弹出一个对话框，允许您创建和编辑显示筛选器宏。您可以命名筛选器宏，并可以将它们保存以备将来使用。关于这个问题的更多细节在：  6.7节, “定义和保存筛选器宏” |
| Apply as Column        |                | 此菜单项将数据包详细信息窗格所选的协议字段作为数据包列表的列。 |
| Apply as Filter → …    |                | 这些菜单项将改变当前的显示筛选器，并立即应用更改的筛选器。根据所选择的菜单项，当前显示筛选器字符串将被在数据包详细信息窗格所选协议字段取代或追加。 |
| Prepare a Filter → …   |                | 这些菜单项将改变当前的显示筛选器，但不会应用更改的筛选器。根据所选择的菜单项，当前显示筛选器字符串将被在数据包详细信息窗格所选协议字段取代或追加。 |
| Enabled Protocols…     | Shift+Ctrl+E   | 此菜单项允许用户启用/禁用协议解码器， 参见  10.4.1节, “ “启用协议” 对话框” |
| Decode As…             |                | 此菜单项允许用户可以强制Wireshark将某些数据包作为一个特定的协议解码，参见  10.4.2节, “用户指定解码器” |
| User Specified Decodes… |               | 此菜单项允许用户可以强制Wireshark将某些数据包作为一个特定的协议解码，参见参见  10.4.3节, “显示用户指定解码” |
| Follow TCP Stream      |                | 此菜单项将弹出一个单独的窗口显示所有捕获的TCP报文段，属于选定的数据包的同一个TCP连接。参见  7.2节, “追踪TCP 流” |
| Follow UDP Stream      |                | 和“追踪TCP流”功能相同，但适用于UDP流。 |
| Follow SSL Stream      |                | 和“追踪TCP流”功能相同，但适用于UDP流。XXX - 如何提供SSL密钥？ |
| Expert Info            |                | 打开一个对话框，显示关于数据包捕获的一些专家信息。信息的数量将取决于协议，从非常详细到不存在。XXX - 从这里添加一个新的章节关于这一点，从这里链接 |
| Conversation Filter → … |                | 在这个菜单中，您能找到多种协议的会话筛选器。 |


### 3.11. “Statistics/统计” 菜单

Wireshark Statistics/统计 菜单包含的字段显示在： 表 3.8, “Statistics/统计 菜单项”.

图 3.9. “Statistics/统计” 菜单
{% img /Wireshark/manual-cn-img/ws-statistics-menu.png %}

所有菜单项将弹出显示具体的统计信息的新窗口。 

表 3.8. Statistics/统计 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| Summary | | 显示有关捕获数据的信息，参见  8.2节, “汇总窗口”。 |
| Protocol Hierarchy | | 显示一个层次的协议统计信息树，参见： 8.3节, “"协议层次" 窗口”。 |
| Conversations | | 显示会话的列表（两个端点之间的流量），参见  8.4.1节, “ “会话”窗口 ”。 |
| Endpoints | | 显示端点（到/从地址的流量/）列表，参见：  8.5.1节, “"端点" 窗口”。 |
| Packet Lengths… | | 参见  8.10节, “协议特定统计窗口” |
| IO Graphs | | 显示用户指定的图形（如，一段时间过程中的数据包数量），参见  8.6节, “"IO 图" 窗口”。 |
| Service Response Time | | 显示请求和相应的响应之间的时间， 参见  8.7节, “服务响应时间”。 |
| ANCP | | 参见  8.10节, “协议特定统计窗口” |
| Colledtd… | | 参见  8.10节, “协议特定统计窗口” |
| Compare… | | 参见  8.10节, “协议特定统计窗口” |
| Flow Graph… | | 参见  8.10节, “协议特定统计窗口” |
| HTTP | | HTTP 请求/响应的统计数据，参见  8.10节, “协议特定统计窗口” |
| IP Addresses… | | 参见  8.10节, “协议特定统计窗口” |
| IP Destinations… | | 参见  8.10节, “协议特定统计窗口” |
| IP Protocol Types… | | 参见  8.10节, “协议特定统计窗口” |
| ONC-RPC Programs | | 参见  8.10节, “协议特定统计窗口” |
| Sametime | | 参见  8.10节, “协议特定统计窗口” |
| TCP Stream Graph | | 参见  8.10节, “协议特定统计窗口” |
| UDP Multicast Streams | | 参见  8.10节, “协议特定统计窗口” |
| WLAN Traffic | | 参见  8.9节, “WLAN 流量统计” |
| BOOTP-DHCP | | 参见  8.10节, “协议特定统计窗口” |


3.12. “Telephony/电信” 菜单

Wireshark Telephony/电话 菜单包含的字段显示在： 表 3.9, “Telephony/电话 菜单项”.

图 3.10. “Telephony/电话” 菜单
{% img /Wireshark/manual-cn-img/ws-telephony-menu.png %}

所有菜单项将弹出显示电话相关的统计信息的新窗口。

表 3.9. Telephony/电话 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| IAX2 | | 参见 9.6节, “协议特定统计窗口”  |
| SMPP Operations… | | 参见 9.6节, “协议特定统计窗口”  |
| SCTP | | 参见 9.6节, “协议特定统计窗口”  |
| ANSI | | 参见 9.6节, “协议特定统计窗口”  |
| GSM | | 参见 9.6节, “协议特定统计窗口”  |
| H.225… | | 参见 9.6节, “协议特定统计窗口”  |
| ISUP Messages… | | 参见 9.6节, “协议特定统计窗口” |
| LTE | | 参见 9.6节, “协议特定统计窗口” |
| MTP3 | | 参见 9.6节, “协议特定统计窗口” |
| RTP | | 参见  9.2节, “RTP 分析” |
| SIP… | | 参见 9.6节, “协议特定统计窗口” |
| UCP Messages… | | 参见 9.6节, “协议特定统计窗口” |
| VoIP Calls… | | 参见 9.3节, “VoIP 呼叫” |
| WAP-WSP… | | 参见 9.6节, “协议指定统计窗口” |

### 3.13. “Tools/工具” 菜单

Wireshark 的Tools/工具菜单包含的字段显示在：表 3.10, “Tools/工具 菜单项”.

图 3.11.  “Tools/工具” 菜单
{% img /Wireshark/manual-cn-img/ws-tools-menu.png %}

表 3.10. Tools/工具 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| Firewall ACL Rules     |                | 这允许您为许多防火墙产品创建命令行ACL规则，包括Cisco IOS、Linux Netfilter（iptables）、OpenBSD PF和Windows防火墙（通过netsh）。规则支持MAC地址、IPv4地址、TCP和UDP端口以及IPv4 +端口的组合。这些规则假设将应用于一个外部接口。|
| Lua                    |                | 这些选项允许您使用内置在Wireshark内的Lua解释器。参见Wireshark的开发者指南中的“Wireshark中支持的Lua”。|


### 3.14. “Internals/内部” 菜单

Wireshark 的Internals/内部菜单包含的字段显示在： 表 3.11, “Internals/内部 菜单项”.

图 3.12.  “Internals/内部” 菜单
{% img /Wireshark/manual-cn-img/ws-internals-menu.png %}

表 3.11. Internals/内部 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| Dissector tables | | 该菜单项显示子解析器关系表对话框。 |
| Supported Protocols (slow!) | | 此菜单项显示支持的协议和协议字段的对话框。 |

3.15. “Help/帮助” 菜单

Wireshark Help/帮助 菜单包含的字段显示在 表 3.12, “Help/帮助 菜单项”.

图 3.13. “Help/帮助” 菜单
{% img /Wireshark/manual-cn-img/ws-help-menu.png %}

表 3.12. Help/帮助 菜单项

| 菜单项	         | 快捷方式	  | 描述                 |
|:-----------------------|:---------------|:---------------------|
| Contents |  F1  | 此菜单项打开基本的帮助系统。 |
| Manual Pages → … | | 此菜单项启动网页浏览器来显示本地安装的HTML手册页面。 |
| Website | | 此菜单项启动网页浏览器显示网站页面： https://www.wireshark.org/。 |
| FAQ’s | | 此菜单项启动网页浏览器显示FAQ页面。 |
| Downloads | | 此菜单项启动网页浏览器显示网站的下载页面： https://www.wireshark.org/. |
| Wiki | | 此菜单项启动网页浏览器显示网站的Wiki页面： https://wiki.wireshark.org/。 |
| Sample Captures | | 此菜单项启动网页浏览器显示网站的捕获样例页面：https://wiki.wireshark.org/。 |
| About Wireshark | | 此菜单项会弹出一个信息窗口，提供各种Wireshark的详细信息项，比如它是如何编译的、加载的插件、使用的文件夹... |
 
 [Note]	注意
您的Wireshark版本可能不支持打开Web浏览器。如果是这样的情况下，相应的菜单项将是隐藏的。

如果您的电脑调用Web浏览器出现故障，没有任何反应，或浏览器启动但没有页面显示，请查看在偏好设置对话框中的网页浏览器设置。

### 3.16. “Main/主” 工具栏

主工具栏提供从菜单中快速访问经常使用的项目。该工具栏不能由用户进行定制，如果需要更多的屏幕上空间以显示更数据包数据，它可以在视图菜单中进行隐藏。

在菜单中，只有在当前程序状态可用的项目才可使用。其他将显示为灰色（例如，如果您还没有加载捕获文件的话将无法保存它）。

图 3.14. “Main/主” 工具栏
{% img /Wireshark/manual-cn-img/ws-main-toolbar.png %}

表 3.13. Main/主 工具栏项目

| 工具栏图标    	| 工具栏项目          |	对应菜单项            |	描述      |
|:----------------------|:--------------------|:----------------------|:----------|
| {% img /Wireshark/manual-cn-img/toolbar/capture_interfaces_24.png %}  | Interfaces… |  Capture → Interfaces…  | 此项目打开“捕获接口列表”对话框， (进一步讨论在  4.3节, “开始捕获”)。 |
| {% img /Wireshark/manual-cn-img/toolbar/capture_options_24.png %}    | Options…    | Capture → Options…  | 此项目打开“捕获选项”对话框(进一步讨论在  4.3节, “开始捕获”)，并允许您开始捕获数据包。 |
| {% img /Wireshark/manual-cn-img/toolbar/capture_start_24.png %}  |Start  | Capture → Start | 此项目使用最近的选项开始捕获数据包。 |
| {% img /Wireshark/manual-cn-img/toolbar/capture_stop_24.png %} | Stop | Capture → Stop | 此项目停止当前正在运行的实时捕获进程，(进一步讨论在  4.3节, “开始捕获”)。 |
| {% img /Wireshark/manual-cn-img/toolbar/capture_restart_24.png %}  | Restart | Capture → Restart | 此项目停止当前正在运行的实时捕获进程，并再次重新启动它，为了方便起见。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_open_24.png %}  | Open… | File → Open… | 此项目打开“打开文件”对话框，让您载入捕获文件进行查看。它更详细地讨论，进一步讨论在  5.2.1节, “ “打开捕获文件” 对话框”。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_save_as_24.png %}  | Save As… | File → Save As… | 此项目可以让您保存当前捕捉文件到您希望的任何文件。它弹出“另存捕获文件为”对话框 (详细的讨论在  5.3.1节, ““另存捕获文件为” 对话框”)。 如果您目前有一个临时捕获文件，保存图标将代替他显示。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_close_24.png %}    | Close | File → Close | 此项目关闭当前捕获。如果您还没有保存捕获信息，您会被要求先保存它。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_refresh_24.png %}  | Reload  | View → Reload  | 此项目允许您重新加载当前捕获文件。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_print_24.png %}   | Print… | File → Print… | 此项目可让您打印所有（或部分）的捕获文件中的数据包。它弹出Wireshark“打印对话框” (详细的讨论在  5.8节, “打印数据包”)。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_search_24.png %}  | Find Packet… | Edit → Find Packet… | 此项目弹出一个对话框，让您查找数据包。关于查找数据包的进一步信息在  6.8节, “查找数据包”。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_left_arrow_24.png %} | Go Back | Go → Go Back | 此项目在数据包历史中向后跳转。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_right_arrow_24.png %}  | Go Forward | Go → Go Forward | 此项目在数据包历史中向前跳转。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_jump_to_24.png %}  | Go to Packet… | Go → Go to Packet…  | 此项目打开一个对话框，允许您跳转到指定序号的数据包。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_top_24.png %}  | Go To First Packet | Go → First Packet  | 此项目跳转到捕获文件的第一个数据包。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_bottom_24.png %} | Go To Last Packet | Go → Last Packet | 此项目跳转到捕获文件的最后一个数据包。 |
| {% img /Wireshark/manual-cn-img/toolbar/colorize_24.png %} | Colorize | View → Colorize   | 着色数据包列表（或不着色）。 |
| {% img /Wireshark/manual-cn-img/toolbar/autoscroll_24.png %} | Auto Scroll in Live Capture | View → Auto Scroll in Live Capture  | 当实时捕获时，自动滚动数据包列表。（或不滚动） |
| {% img /Wireshark/manual-cn-img/toolbar/stock_zoom_in_24.png %}   | Zoom In | View → Zoom In  | 放大数据包数据（增加字体大小）。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_zoom_out_24.png %}  | Zoom Out  | View → Zoom Out  | 缩小数据包数据（减小字体大小）。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_zoom_1_24.png %}  | Normal Size | View → Normal Size  | 设置缩放级别恢复到100％。 |
| {% img /Wireshark/manual-cn-img/toolbar/resize_columns_24.png %}  | Resize Columns  | View → Resize Columns  | 调整列宽，让内容适配。 |
| {% img /Wireshark/manual-cn-img/toolbar/capture_filter_24.png %} | Capture Filters… |  Capture → Capture Filters… |  此项打开一个对话框，允许您创建和编辑捕获筛选器。您可以命名筛选器，并可以将它们保存以备将来使用。关于这个问题的更多细节在：  6.6节, “定义和保存筛选器”。 |
| {% img /Wireshark/manual-cn-img/toolbar/display_filter_24.png %}  | Display Filters…  | Analyze → Display Filters…  | 此项打开一个对话框，允许您创建和编辑显示筛选器。您可以命名筛选器，并可以将它们保存以备将来使用。关于这个问题的更多细节在：  6.6节, “定义和保存筛选器”。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_colorselector_24.png %}  | Coloring Rules…  | View → Coloring Rules…  | 此菜单项将弹出一个对话框，根据您选择的过滤表达式让您对数据包列表窗格中的数据包进行着色。它对标识特定类型的数据包非常有用，参见  10.3节, “数据包着色”。 |
| {% img /Wireshark/manual-cn-img/toolbar/stock_preferences_24.png %}  | Preferences…  | Edit → Preferences  | 此菜单项将弹出一个对话框，允许您设置偏好选项中的参数来控制Wireshark。您还可以保存您的偏好设置，这样Wireshark下一次启动时您可以使用它。更多详细信息参考  10.5节, “偏好设置” |
| {% img /Wireshark/manual-cn-img/toolbar/stock_help_24.png %}  | Help  | Help → Contents  | 此菜单项打开帮助对话框。|
 
### 3.17. “Filter/筛选器” 工具栏

筛选器工具栏，可以让您快速编辑和应用显示筛选器。显示筛选器的详细信息在  6.3节, “浏览时过滤数据包”。

图 3.15. “Filter/筛选器” 工具栏
{% img /Wireshark/manual-cn-img/ws-filter-toolbar.png %}


表 3.14. 筛选器工具栏项目

| 工具栏图标   |工具栏项目	|描述      |
|:-------------|:---------------|:---------|
| {% img /Wireshark/manual-cn-img/toolbar/display_filter_24.png %} | Filter: | 筛选器结构对话框，描述见 图 6.8, “ “捕获筛选器” 和 “显示筛选器” 对话框”。|
|              | Filter input   | 该地区输入或编辑显示过滤字符串，见  6.4节, “建立显示筛选器表达式Building display filter expressions”。当您输入时，对于过滤字符串的语法检查被执行。如果您输入一个不完整的或无效的字符串，背景将变成红色，而当您输入一个有效的字符串将变成绿色。您可以点击下拉箭头，从列表中选择一个以前输入的过滤字符串。即使程序重新启动，在下拉列表中的条目将仍然可用。当您在这个领域改变一些东西，不要忘记按Apply按钮（或回车/返回键），将这个过滤字符串应用于显示。这个字段也用于显示当前生效的筛选器。|
| {% img /Wireshark/manual-cn-img/toolbar/stock_add_24.png %} | Expression… | 中间标记为“添加表达式...”的按钮会打开一个对话框，让您从协议字段列表编辑显示筛选器，说明在  6.5节, ““过滤表达式” 对话框”|
| {% img /Wireshark/manual-cn-img/toolbar/stock_clear_24.png %}      | Clear | 重置当前的显示筛选器，并清除编辑区域。|
| {% img /Wireshark/manual-cn-img/toolbar/stock_apply_20.png %}      | Apply | 将编辑区域中的当前值作为新的显示筛选器。应用在大型捕获文件上的显示筛选器可能需要相当长的时间。|


### 3.18. “Packet List/数据包列表”窗格

数据包列表窗格显示在当前捕获文件中的所有数据包。

图 3.16.  “数据包列表” 窗格

{% img /Wireshark/manual-cn-img/ws-list-pane.png %}

在数据包列表中的每一行对应于捕获文件中的一个数据包。如果选择在此窗格中的一行，更详细信息将显示在“数据包详细信息”和“数据包字节”窗格中。

当解析一个数据包时，Wireshark将从协议解析器中获取的信息放置为列信息。更高级别的协议可能会覆盖低级别协议的信息，您通常会看到只有最高级别的信息。

例如，让我们来看看一个数据包包含TCP信息，封装在IP和以太网中。以太网解析器将写入其数据（如以太网地址），IP解析器将用自身信息来覆盖他（如IP地址），TCP解析器将覆盖IP信息，等等。

有很多不同的列。可以通过首选项设置来选择哪些列被显示，参见  10.5节, “首选项”。

默认列会显示：

- **序号** 在捕获文件中数据包的序号。即使使用显示滤波器，这个数字也不会改变。
- **时间** 数据包的时间戳。此时间戳的显示格式是可以改变的，请参见 6.12节, “时间显示格式和时间参考”。
- **源** 这个数据包的始发地址。
- **目的地** 这个数据包的去往地址。
- **协议** 短的（可能是缩写）版本的协议名称。
- **信息** 对数据包内容的附加​​信息。
有一个上下文菜单（单击鼠标右键）提供，详情请参阅在图 6.4, “ “数据包列表” 窗格弹出菜单” 。

### 3.19. “ Packet Details/数据包详细信息” 窗格

数据包详细信息窗格中以更详细的格式显示当前数据包（在“数据包列表”窗格中选择）。

图 3.17. “数据包详细信息” 窗格

{% img /Wireshark/manual-cn-img/ws-details-pane.png %}

此窗格显示在“数据包列表”窗格中选择的数据包的协议和协议字段。数据包的协议和字段信息使用树行结果显示，可展开和折叠。

有一个上下文菜单（单击鼠标右键）可用，详情请参阅  6.5图, “ “数据包详细信息” 窗格弹出菜单” 图6.5，“弹出菜单中的”包详细信息“窗格”。

有些特别显示的协议字段。

- **生成的字段** Wireshark的本身会生成由括号括起来的附加​​协议字段。这些字段中的信息是从捕捉文件中已知的其他报文的上下文派生的。例如，Wireshark进行每个TCP流的序列/确认的分析，这显示在TCP协议的[SEQ / ACK分析] 字段中。
- **链接** 如果Wireshark检测和捕获文件中的另一个数据包的存在关联关系，它会生成一个链接到那个数据包。链接带有下划线并以蓝色显示。如果双击，Wireshark将跳转到相应数据包。

### 3.20. “Packet Bytes/数据包字节” 窗格

数据包字节窗格以hexdump风格显示当前数据包（在“数据包列表”窗格中选择）的数据。
图 3.18. “数据包字节” 窗格

{% img /Wireshark/manual-cn-img/ws-bytes-pane.png %}

As usual for a hexdump, the left side shows the offset in the packet data, in the middle the packet data is shown in a hexadecimal representation and on the right the corresponding ASCII characters (or . if not appropriate) are displayed.

Depending on the packet data, sometimes more than one page is available, e.g. when Wireshark has reassembled some packets into a single chunk of data, 参见 Section 7.6, “Packet Reassembly”. In this case there are some additional tabs shown at the bottom of the 窗格 to let you select the page you want to 参见.

图 3.19. 带标签的“数据包字节” 窗格

{% img /Wireshark/manual-cn-img/ws-bytes-pane-tabs.png %}

[Note]	注意
额外页面可能包含来自多个数据包选取的数据。

标签的上下文菜单（点击鼠标右键），将显示所有可用的页面列表。如果窗格的尺寸太小来显示所有标签，这是有帮助的。

3.21. 状态栏

状态栏用来显示提示信息。

在一般情况下，在左侧将显示上下文相关的信息，中间部分将显示数据包的当前数量，右侧将显示选择的配置文件。拖动文本区域之间的手柄来改变大小。

图 3.20. 初始状态栏
{% img /Wireshark/manual-cn-img/ws-statusbar-empty.png %}
当没有加载捕获文件，例如Wireshark刚启动的时候，显示该状态栏。

图 3.21. 加载捕获文件的状态栏

{% img /Wireshark/manual-cn-img/ws-statusbar-loaded.png %}

- **彩色子弹** 左侧显示了当前加载捕获文件中找到的最高级别专家信息。将鼠标悬停在该图标将显示专家信息级别的文字描述，单击该图标会弹出相关“专家信息”对话框。有关专家信息的详细说明，请参见  7.3节, “专家信息”。
- **左侧** 显示有关捕获文件的信息，它的名字、大小以及它被捕获时经过时间。
- **中间部分** 显示了捕获文件中数据包的当前数量。显示下面的值：
  -数据包：捕获的数据包数量
  -显示：当前正在显示的数据包数量
  -标记：标记的数据包数量
  -丢弃：丢弃的数据包数量（仅当Wireshark的无法捕获到的所有数据包时显示）
  -忽略：忽略的数据包数量（仅当数据包被忽略时显示）
- **右侧** 显示所选配置文件。点击这部分的状态栏会弹出一个菜单，列出所有可用的配置文件，从该列表中选择后将改变配置文件。

图 3.22. 带有配置文件菜单的状态栏

{% img /Wireshark/manual-cn-img/ws-statusbar-profile.png %}


对于配置配置文件的详细说明，请参见  10.6节, “配置文件”。

图 3.23. 带有选择协议字段的状态栏

{% img /Wireshark/manual-cn-img/ws-statusbar-selected.png %}

如果您从“数据包详细信息”窗格中选择了协议字段，将显示此项。

[Tip]	提示
括号中间的值（本例为arp.opcode）可被用作显示过滤字符串，表示所选择的协议字段。

图 3.24. 带有显示筛选器信息的状态栏

{% img /Wireshark/manual-cn-img/ws-statusbar-filter.png %}

这是您试图使用一个有意想不到结果的显示筛选器时的显示信息。详情参考  6.4.4节, “常见错误”。
