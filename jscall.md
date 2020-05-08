# JavaScript 扩展
axeBrowser 在不断的更新和完善中，因此内置的扩展也会有修改和增减。在进行修改和增减时，会尽量的保持兼容性，使原有扩展代码无需进行修改。请随时关注最新的文档说明。


## <span id = "axe">axe</span>
axeBrowser 为浏览器提供了一个扩展对象 axe。JavaScript 可以通过 window.external.axe 获得，并通过这个扩展对象对功能进行扩展。

可以通过这个扩展对象，判断当前是否属于 axeBrowser 环境并获取详细信息。

例如：
```javascript
var _axe = window.external.axe;
if (_axe == null) {
    alert('请检查：当前运行环境似乎不是 axeBrowser ？');
} else {
    alert(_axe);
}
```



## <span id = "axe_getArgv">axe.getArgv</span>
获取指定的命令行参数值，如果该命令行参数没有指定，则返回空。

```
axeBrowser -home qq.com -p1 test;
```

```javascript
window.external.axe.getArgv('home');
window.external.axe.getArgv('p1');

qq.com
test
```

## <span id = "axe_log">axe.log</span>
在命令行窗口中打印日志，如果命令行窗口没有打开将自动打开。本函数变量为变长，接受多个参数。打印日志时，多个参数之间用制表符分隔。

```javascript
window.external.axe.log('This line is a log.');
window.external.axe.log('This line is 1st', '2nd', '3rd');

This line is a log.
This line is 1st    2nd 3rd
```


## <span id = "axe_exit">axe.exit</span>
立即退出 axeBrowser。

```javascript
window.external.axe.exit();
```

## <span id = "axe_exec">axe.exec</span>
异步调用外部程序，调用后将立即返回并执行后继代码，不等待被调用的外部程序执行完毕。
接收两个参数，第一个为要调用的程序名，第二个为其调用参数。

```javascript
window.external.axe.exec('notepad.exe');
```

## <span id = "axe_execWait">axe.execWait</span>
同步调用外部程序，调用后将等待外部程序执行完毕后，再执行后继代码。
接收两个参数，第一个为要调用的程序名，第二个为其调用参数。

```javascript
window.external.axe.exitWait('ping', '127.0.0.1');
```
## <span id = "axe_toString">axe.toString</span>
返回 axe 扩展对象的具体信息。

```javascript
console.log(window.external.axe);

axeBrowser 1.0.0.0
```

## <span id = "axe_setTitle">axe.setTitle</span>
设置窗口标题，包括浏览器窗口标题和命令行终端窗口标题。

```javascript
window.external.axe.setTitle('这是由 JavaScript 设置的窗口标题');
```
