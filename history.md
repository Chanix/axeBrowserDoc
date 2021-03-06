# 下载与历史

## 正在进行中的工作：
- 进一步完善 demo；
- 进一步加强 js API；
- 进一步完善文档；

## 2021/02/09
- 版本升级至 1.0.5；
- 升级 miniblink 至 2021-1-14；
- 发布版中增加 demo 文件夹，未来相关的范例都会放在这里；
- 新增范例：获取 Bing 每日壁纸；
- 祝各位春节愉快！

[GitHub 下载](https://raw.githubusercontent.com/Chanix/axeBrowserDoc/master/download/axeBrowser-20210209.zip) | 
[gitee 下载](https://gitee.com/chanix/axeBrowserDoc/raw/master/download/axeBrowser-20210209.zip)


## 2021/01/18
- 新增与调整扩展：
    - 文件系统            [\_\_AXE\_\_.fsys](AXE_fsys.md#axe_fsys)
    - 鼠标                [\_\_AXE\_\_.mouse](AXE_mouse.md#axe_mouse)
- 修正命令行参数 proxy 处理错误，该错误导致无法正常设置代理服务器；
- 调整 \_\_AXE\_\_.exit()，更优雅的终结运行，避免咚咚咚，听着好烦~~；

## 2020/10/22
- 修正装载提示窗体失败的错误；
- 改进伪随机数算法和种子设置，尽量的“真”随机一些；
- 继续修正 \_\_AXE\_\_.exit() 偶尔卡死，无法正常关闭应用的问题（嗯……继续……）；
- 提示捐助窗口，增加定时关闭功能，减少对流程的干扰；
- 重构代码，拆分功能类与模块，优化代码，不再那么面条了；
- 整理现有文档，部分扩展模块的调整和完善；

## 2020/09/23
- 优化代码逻辑，减小程序体积；
- 修正处理 timeout 参数时的一处缺陷，该缺陷导致特定情况下程序无法退出；
- 新增与调整扩展：
    - 控制台            [\_\_AXE\_\_.console](AXE_console.md#axe_console)
    - 字符串处理        [\_\_AXE\_\_.string](AXE_string.md#axe_string)
- 脚本文件的简单保护，保护开发者；
    axeBrowser -toolkit protect_script -f <filename>
- 新增命令行小工具，通过命令行参数 toolkit 进行调用；


## 2020/07/22
- 版本升级至 1.0.4；
- 取消 CTRL+、CTRL-、CTRL0 对界面缩放的热键；
        缩放有可能造成与开发者的意图相冲突；
        界面应当由开发者来决定，不应画蛇添足；
        可通过调用 \_\_AXE\_\_.setDpi 来设置缩放功能；
- 修正内部网页资源的引用错误；
- 完善并整理文档；
- 新增与调整扩展（此版本变化较大，请以最新文档为准）：
    - 基础扩展          [\_\_AXE\_\_](AXE_core.md#axe)；
    - 控制台            [\_\_AXE\_\_.console](AXE_console.md#axe_console)
    - 自定义热键        [\_\_AXE\_\_.hotkey](AXE_hotkey.md#axe_hotkey)；
    - 剪贴板            [\_\_AXE\_\_.clipboard](AXE_clipboard.md#axe_clipboard)
    - 编码解码          [\_\_AXE\_\_.crypt](AXE_process.md#axe_crypt)
    - 对话框            [\_\_AXE\_\_.dlg](AXE_dlg.md#axe_dlg)
    - 环境变量          [\_\_AXE\_\_.env](AXE_clipboard.md#axe_env)
    - 进程相关          [\_\_AXE\_\_.process](AXE_process.md#axe_process)
    - 文件系统          [\_\_AXE\_\_.fsys](AXE_fsys.md#axe_fsys)
- 移除 window.external.axe；


## 2020/07/01
- 优化 app 运行模式下的窗体显示；
- 整理和完善运行流程、运行模式；
- 新增常用编码、加密算法，参见 [\_\_AXE\_\_.crypt](AXE_crypt.md#axe_crypt)；
- 新增进程相关的扩展函数，参见 [\_\_AXE\_\_.process](AXE_process.md#axe_process)；


## 2020/06/26
- 各位端午节快乐！
- 版本升级至 1.0.3；
- 重构和整理代码；
- 取消 VLC 支持库的分发；
        axeBrowser 依然内置 VLC 支持，但不再分发支持库；
        大部分场景不需要，完全支持必须再加上近百兆的库文件；
        需要的用户请自行添加相应的库和支持文件；
- 取消 Flash 支持库的分发；
        axeBrowser 依然内置 Flash 支持，但不再分发支持库；
        Adobe 于 2020/12/31 取消 Flash 的支持与维护；
        需要的用户请自行添加相应的库和支持文件；
- 修改完善内置网页内容；


## 2020/06/18
- 新增扩展：
    - 获取当前进程id    [\_\_AXE\_\_.win.getProcessId](jscall.md#axe_win_getProcessId)
    - 获取当前线程id    [\_\_AXE\_\_.win.getThreadId](jscall.md#axe_win_getThreadId)
    - 获取环境变量      [\_\_AXE\_\_.win.getenv](jscall.md#axe_win_getenv)
    - 设置环境变量      [\_\_AXE\_\_.win.setenv](jscall.md#axe_win_setenv)
    - 增加环境变量      [\_\_AXE\_\_.win.addenv](jscall.md#axe_win_addenv)
- 增加应用的图标（白板太难看，随便找了一个先顶上，有更好的请与我联系）
- 整理与规范内置页面（axe://）；
- 调整自动缩放策略，默认提供 dpi 自动缩放，通过命令行参数 nodpi 来设置取消；
- 完善运行流程，增加打开网址前执行脚本，新增命令行参数：
    - 打开前脚本        [prescript](todo.md)
    - 打开前脚本入口    [preentrypoint](todo.md)
- 优化 \_\_AXE\_\_.exec 的处理流程，原流程无必要的增加了脚本的控制难度；

## 2020/06/08
- 调整内嵌 miniblink 版本，提升健壮性；
        原 20.3.3 存在经常性崩溃（win10下），事件查看器中一直报 node.dll 错误。
        降级至 19.11.11 后明显的减少了崩溃；
        但此两版本皆存在 cookies 处理错误，没有正确的处理等号；
        导致某些站点出现 “cookies or request too large” 的情况，正在测试验证升级方案中。
- 扩展对象调用方式修改，在 JavaScript 中直接访问变量 \_\_AXE\_\_ 即可;
        原因：window.external 已从 Web 标准中删除；
        window.external.axe 仍可使用，但请尽量使用新的调用方式，其将会在未来的版本中移除；
- 新增扩展：剪贴板；
    - [\_\_AXE\_\_.win.clip.read](jscall.md#axe_win_clip_read)
    - [\_\_AXE\_\_.win.clip.write](jscall.md#axe_win_clip_write)

## 2020/06/01
- 增加 VLC 支持（32位）；
- 提升稳定运行时间，查找崩溃原因；
- 修正命令行参数 referer 处理错误（该错误导致某些情况下设置失败）；
- 修正打开主页网址时，网址输入框显示延迟的错误；
- 增加命令行参数 dpi，提供自动缩放选择，改善高分辨率下的窗口显示；
- 完善设置窗口标题的处理逻辑，注册版将不再显示版本信息，便于二次开发应用的分发；
- 修正浏览器网址输入框的显示错误；
- 调整和美观窗体布局；

## 2020/05/25
- 修正标题显示网址错误；
- 增加 flash 支持（32位）；
- 取消读写文件时的路径限制（用户反馈既然可以绕过，何必再脱裤子放屁~~~）；
- 重构扩展功能 “设置窗口标题”；
- 重构 dll 与 控件 包装调用代码；
- 提升稳定运行时间（水平有限，导致未能无缝整合，程序运行一段时间后可能会随机崩溃出现）；

## 2020/05/21
- 增加命令行参数 width，指定浏览器的宽度；
- 增加命令行参数 height，指定浏览器的高度；
- 修正注册码可能验证失败的问题；
- 提升稳定运行时间（由于个人水平问题，程序运行一段时间后，有发生崩溃的情况）；
- 取消百度网盘提供下载；

## 2020/05/18
- 彻底重新整理和编译，初始化版本。
