# 内置扩展
axeBrowser 提供了一个扩展用的对象 axe。可以通过这个对象作为桥梁为js提供一些扩展功能。在 js 中通过 windows.eternal.axe 来进行调用。axeBrowser 在不断的更新和完善中，因此扩展也会有修改和增减。请随时关注最新的文档说明。

## <span id = "log">log</span>
指定运行模式，默认为 debug。

| 值 | 说明 |
|--- |------|
| console | 命令行模式，仅显示终端字符界面窗口。主要在作为自动化工具时使用。|
| app | 应用模式，图形窗口模式。不显示浏览器功能界面。主要在作为窗口应用时使用。 |
| debug | 调试模式，打开图形窗口，提供简单的浏览器功能界面。主要在开发调试时使用。 |

