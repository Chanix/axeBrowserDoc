# 命令行参数
axeBrowser 在不断的更新和完善中，因此命令行参数也会有修改和增减。请随时关注最新的文档说明。

## <span id = "runas">runas</span>
指定运行模式，默认为 debug。

| 值 | 说明 |
|--- |------|
| console | 命令行模式，仅显示终端字符界面窗口。主要在作为自动化工具时使用。|
| app | 应用模式，图形窗口模式。不显示浏览器功能界面。主要在作为窗口应用时使用。 |
| debug | 调试模式，打开图形窗口，提供简单的浏览器功能界面。主要在开发调试时使用。 |

## <span id = "home">home</span>
指定自动首页网址，默认为 axeBrowser.com。完成初始化后，axeBrowser 会自动打开这个网址。

## <span id = "script">script</span>
指定自动装载的 JavaScript 脚本或 JavaScript 脚本列表。（文件名之间以 "," 或 ";" 进行分隔。）默认为空。
打开首页后，axeBrowser 会按照先后顺序读取文件内容，并合并为一段代码在浏览器环境中的匿名函数中执行。

程序会在每个 js 文件内容的末尾加上 “\n;\n”，避免问题。

可以利用脚本列表，将不同功能的 JavaScript 代码放在不同的 js 文件中，以达到“模块化”的目的（注：打了双引号的，不是真的模块化）。

举个例子：
```
axeBrowser -script js1.js,js2.js,js3.js
```

js1.js
```javascript
__AXE__.log('this is js1.js')

```

js2.js
```javascript

__AXE__.log('this is js2.js');
```

js3.js
```javascript
__AXE__.log('this is js3.js');

```

最终合并并执行的 JavaScript 代码是：
```javascript
__AXE__.log('this is js1.js')

;

__AXE__.log('this is js2.js');
;
__AXE__.log('this is js3.js');

;

```

## <span id = "entrypoint">entrypoint</span>
指定自动调用的 JavaScript 入口函数的函数名，默认为空。该函数必须在 script 参数指明的脚本中被预先定义。入口函数不支持参数。

举个例子：

```
axeBrowser -script js1.js -entrypoint doStart
```

```javascript
function fn_test_log(a, b) {
    __AXE__.log(a, b);
}

function doStart() {
    fn_test_log('111', '222');
}
```

最终合并并执行的 JavaScript 代码是：
```javascript
function fn_test_log(a, b) {
    __AXE__.log(a, b);
}

function doStart() {
    fn_test_log('111', '222');
}

;
doStart();

```

## <span id = "referer">referer</span>
指定浏览器访问首页时使用的来源地址（即 header 中的 referer），默认为空。

## <span id = "useragent">useragent</span>
指定访问资源时使用的用户代理标识。默认值为：默认内嵌浏览器控件的值 + axeBrowser/版本号。

## <span id = "proxy">proxy</span>
指定访问资源时使用的代理服务器地址，默认为空（即不使用代理服务器）。

## <span id = "wait_mode">wait_mode</span>
指定等待首页加载完毕的模式。axeBrowser 将在首页装载完毕后，进行后继的调用脚本、调用入口函数等工作。默认值为 waitdoc。

| 值 | 说明 |
|--- |------|
| nowait | 不等待。 |
| wait | 指定本参数后，可以通过 -wait_url 和 -wait_timeout 来指定等待的网址和超时时间。默认 wait_url 为空，wait_timeout 为 5000 毫秒。 |
| waitdoc | 等 document 元素加载完毕。 |

注意，本参数需要按照具体使用环境来选择。详细说明请参见其他相关文档。举个例子：在很多动态装载的网页中， 虽然网页装载已经完成了，满足 waitdoc 条件，但还需运行 js 代码才有进一步的内容。在这种情况下，就可能需要使用 wait 模式来等待一段时间。



## <span id = "timeout">timeout</span>
指定执行超时时间，单位为毫秒，默认为空。运行超过指定时间后将应用自动退出。超时时间从程序初始化完成后开始计算。

## <span id = "width">width</span>
设置浏览器窗口的宽度。参数值为一个整数，取值范围为 100 ~ 65535。

## <span id = "height">height</span>
设置浏览器窗口的高度。参数值为一个整数，取值范围为 100 ~ 65535。

## <span id = "dpi">dpi</span>
打开 dpi 自动缩放功能，改善高分辨率下的显示。

## <span id = "help">help</span>
显示简要帮助
