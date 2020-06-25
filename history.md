# 下载与历史

## 正在进行中的工作：
- 升级 miniblink 和相关控件；
- 脚本文件的简单保护；

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

[GitHub 下载](https://raw.githubusercontent.com/Chanix/axeBrowserDoc/master/download/axeBrowser-20200626.zip) | 
[gitee 下载](https://gitee.com/chanix/axeBrowserDoc/raw/master/download/axeBrowser-20200626.zip) 


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
