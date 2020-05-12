# JavaScript 扩展
axeBrowser 在不断的更新和完善中，因此内置的扩展也会有修改和增减。在进行修改和增减时，会尽量的保持兼容性，使原有的脚本无需进行修改。请随时关注最新的文档说明。

---

## <span id = "axe">axe</span>
axeBrowser 为浏览器提供了一个扩展对象 axe。JavaScript 可以通过 window.external.axe 获得，并通过这个扩展对象对功能进行扩展。

可以通过这个扩展对象，判断当前是否属于 axeBrowser 环境并获取详细信息。

例如：
```javascript
var AXE = window.external.axe;
if (AXE == null) {
    alert('请检查：当前运行环境似乎不是 axeBrowser ？');
} else {
    alert(AXE);
}
```

---

## <span id = "axe_getArgv">axe.getArgv</span>
#### 定义和用法
getArgv 用于提取执行 axeBrowser 时，指定的命令行参数值。

##### 语法
```javascript
window.external.axe.getArgv(arg_name)
```

| 参数 | 描述 |
| :--- | :--- |
| arg_name| 命令行参数的名称 |

#### 返回值
一个字符串，值为指定命令行参数的值。若没有指定该参数值，则返回 null。

#### 提示
由于特殊字符和命令行环境的存在，指定命令行参数时，请按实际情况进行转义。建议用 " 将参数值包含起来。

#### 实例
执行命令行为
```
axeBrowser -home qq.com -p1 test;
```

```javascript
window.external.axe.getArgv('home');
window.external.axe.getArgv('p1');

qq.com
test
```

---

## <span id = "axe_log">axe.log</span>
在命令行窗口中打印日志，如果命令行窗口没有打开将自动打开。本函数变量为变长，接受多个参数。打印日志时，多个参数之间用制表符分隔。

axe.log(str);

axe.log(str1, str2, str3 ...);

```javascript
window.external.axe.log('This line is a log.');
window.external.axe.log('This line is 1st', '2nd', '3rd');

This line is a log.
This line is 1st    2nd 3rd
```

---

## <span id = "axe_exit">axe.exit</span>
#### 定义和用法
立即退出 axeBrowser。

##### 语法
```javascript
window.external.axe.exit()
```

| 参数 | 描述 |
| :--- | :--- |
| 无|  |

#### 返回值
无。


#### 实例
```javascript
window.external.axe.exit();
```

---

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
## <span id = "axe_scrollPos">axe.scrollPos</span>
浏览器窗口移动到指定位置，参数为x，y坐标。可以使用负数， (-1, -1) 即为右下角。

```javascript
window.external.axe.scrollPos(-1, -1);
```
## <span id = "axe_file_readString">axe.file.readString</span>
axe.file.readString(filename);

以字符串方式读取指定文件，注意该函数将一次性读取文件到内存后再返回，请不要读取过大的文件。出于安全考虑，文件必须位于 axeBrowser 执行文件所在的文件夹或子文件夹内。

## <span id = "axe_file_writeString">axe.file.writeString</span>
axe.file.writeString(filename, content, if_append);

写入文件。出于安全考虑，文件必须位于 axeBrowser 执行文件所在的文件夹或子文件夹内。

