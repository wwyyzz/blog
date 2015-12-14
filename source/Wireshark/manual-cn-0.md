title: 前言
---

### 1.前言

Wireshark 是一种网络管理员都会使用到的程序，但由于一直缺乏文档资料阻碍了他们从Wireshark中得到他们想要。本文档是wireshark团队提高Wireshark的可用性努力的一部分。

我们希望本书能对您有所帮助，同时期待您的意见。

### 2. 谁应该阅读这个文档？

任何使用Wireshark的人员都是本文档的目标受众。

本书将解释所有Wireshark提供的基本及高级特性。Wireshark已经成为一个非常复杂的程序，本书将不会解释Wireshark的每一个特性。

本书的目的不是解释网络监听的一般概念，也不会提供特性网络协议的细节。很多关于这些主题的有用信息可以在Wireshark的Wiki上找到：https://wiki.wireshark.org/
通过阅读本书，您将学习如何安装Wireshark，如何使用图形用户界面的基本元素（如菜单）和并不总是显而易见的隐藏在高级功能后的内容。它将指导您解决一些Wireshark的初级（有时甚至是高级）用户常见的问题。 

### 3. 致谢

作者要感谢整个Wireshark团队的协助。作者要特别感谢：

- Gerald Combs，启动 Wireshark项目并资助完成本文档。
- Guy Harris， 提供很多有用的帮助并极大耐心来评审本文档。
- Gilbert Ramirez，一直以来提供鼓励及有用的帮助。

作者还想感谢以下人对本文档的帮助反馈：

- Pat Eyler，他在提高生成回溯的案例的建议。
- Martin Regner，他的各种建议和修正。
- Graeme Hewson,，对于很多语法的修正。

作者要感谢哪些Wireshark项目的帮助页面和README的作者，本文档的以下章节从中借鉴良多：

 - Section D.8, “mergecap: Merging multiple capture files into one” 从 Scott Renfro的 mergecap帮助页面中派生。
-  Section D.9, “text2pcap: Converting ASCII hexdumps to network captures”从 Ashok Narayanan的text2pcap帮助页面派生。

### 4. 关于本文档

本书最初在Wireshark基金资助下，由 Richard Sharpe 开发。由Ed Warnicke 更新，最新的重新设计和更新由 Ulf Lamping完成。

本书最早由DocBook/XMLIt完成写作并由Gerald Combs转换为AsciiDoc。

在这本书中，您会发现一些特别标注的部分：

[Warning] 警告
您应该关注警告，否则可能发生数据丢失。
[Note]	注意
注意会给您指出常见错误和可能不明显的事情。
[Tip]	提示
提示有助于您的日常工作中使用Wireshark。

### 5. 在哪里得到本文档的最新版本？

本文档的最新版本在 https://www.wireshark.org/docs/。

### 6. 提供关于本文档的反馈

如果您对此文件有任何意见，请通过  wireshark-dev[AT]wireshark.org发送给作者。
