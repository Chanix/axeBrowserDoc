# axeBrowser 简介与说明

axeBrowser is a <font color=red>browser</font>, <font color=red>**A**</font>utomatically, e<font color=red>**X**</font>tendedly, <font color=red>**E**</font>asily.

axeBrowser 是一个浏览器，可以**方便**的进行功能**扩展**和**自动化**操作。

使用 JavaScript，HTML 和 CSS 快速搭建 Window 桌面应用程序，省下更多的时间用来陪伴、娱乐和成长。

JavaScript/HTML/CSS + AXEBrowser = Windows application ! 


[免费下载](history.md)

## 用途和作用
axeBrowser 本质上是一个通过浏览器控件提供 javascript 运行环境的脚本执行工具，从某种意义上而言和 Electron 很类似。开发者可以使用 JavaScript，HTML 和 CSS 快速搭建 Window 桌面应用程序，省下更多的时间用来陪伴、娱乐和成长。

- 对作者而言，开发 axeBrowser 是为了满足自动化测试和日常小工具的需求；
- 一些用户用来自动化操作，提高工作效率；
- 一些用户用来运行和分发一些 Windows 应用；
- ……

具体能做什么，取决于您的想象力，您可以在范例中看到一些例子。

## 功能和特点
- 内置 JavaScript 运行环境；
- 提供内置扩展对象供 JavaScript 调用，扩展功能；
- 多种运行模式（命令行模式、应用模式，调试模式）；
- Javascript 可操作所有 DOM、window 等浏览器中才有的对象。

## 已知功能限制
axeBrowser 的功能限制主要源于两个方面，开发工具（32位程序）和内置的浏览器（miniblink）。
- 仅支持 Windows （xp 以上版本）；
- 不支持涉及视频、音频（不包括 flash 播放器）；
- 单个进程最大 2G 内存；

## 风险与安全漏洞
为了更好的实现功能扩展和自动化操作，axeBrowser 没有遵循浏览器的沙盒安全策略。对于安全软件来说，axeBrowser 既然是浏览器，而又存在调用本地资源的行为，那么就存在安全漏洞。因此很多杀毒和防护软件会报告存在病毒木马行为。这是软件的功能和运行机制决定的，并非含病毒。

axeBrowser 提供了脚本运行环境，但无法保证执行的脚本的功能和目的。如果 axeBrowser 执行了存在恶意代码的脚本，那么就会造成安全隐患，可能带来非常严重的后果。

## 许可与费用
axeBrowser 是免费软件，使用 MIT 协议。再次重申，对于本软件的使用和可能造成的后果请您自行承担。当然，如果您觉得对您有用，愿意请我喝杯茶，那会是一种更大的激励。

- **使用本软件即表明您已经明确了解风险并对可能造成的后果自行负责。正如用菜刀进行非法行为是使用者的问题，非刀的问题，更不是制造商的问题。**
- **对于软件的使用和可能造成的后果，axeBrowser 不进行任何明示的或者暗示的担保，亦不承担任何责任和义务（无论是法律上的或者是道义上的）。**
- **仅保证，尽可能开发并完善 axeBrowser。**

## 更多信息
软件主页：http://www.axeBrowser.com
Q 群: 422269945
