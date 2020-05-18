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


*注意：在后继章节中，将使用 **<font color=red>AXE</font>** 作为 “window.external.axe” 的缩写。*


---

## <span id = "axe_getArgv">axe.getArgv</span>
#### 定义和用法
用于提取执行 axeBrowser 时，指定的命令行参数值。


```javascript
window.external.axe.getArgv(arg_name)
```

| 参数 | 描述 |
| :--- | :--- |
| arg_name | 字符串，命令行参数的名称 |

#### 返回值
一个字符串，值为指定命令行参数的值。若没有指定该参数，则返回 null。若指定了该参数，但没有定义值，则返回空字符串。

#### 提示
由于特殊字符和命令行环境的存在，指定命令行参数时，请按实际情况进行转义。建议用双引号 “"”  将参数值包含起来。

#### 实例
命令行：
```
axeBrowser -home qq.com -p1 test1 -p2;
```

| 调用值 | 返回值 | 描述 |
| :--- | :--- | :--- |
| AXE.getArgv('home')   | 'qq.com'  | 指定了参数指定了值 |
| AXE.getArgv('p1')     | 'test1'   | 指定了参数指定了值 |
| AXE.getArgv('p2')     | ''        | 指定了参数，没有指定值，返回空字符串 |
| AXE.getArgv('home')   | null      | 没有指定参数，返回 null |

---

## <span id = "axe_log">axe.log</span>
#### 定义和用法
在命令行窗口中显示日志，如果命令行窗口没有打开将自动打开。支持多个参数，显示时多个参数间使用制表符分隔，并且在最后换行。


```javascript
window.external.axe.log(p1, p2, p3 ...)
```

| 参数 | 描述 |
| :--- | :--- |
| p1, p2, p3 ... | 要显示的内容，可以为变量或者表达式 |

#### 返回值
无

#### 提示
如果参数不是字符串类型，那么将试图自动转换为字符串后再显示。

#### 实例
脚本：
```javascript
window.external.axe.log();
window.external.axe.log('This is a string');
window.external.axe.log(null);
window.external.axe.log('String', 12345, null, 4+5, 'Str'=='Str');

```
输出：

```javascript

This is a string

String  12345   null    9       true
```

---

## <span id = "axe_exit">axe.exit</span>
#### 定义和用法
发送程序终止消息，立即退出 axeBrowser。


```javascript
window.external.axe.exit()
```

| 参数 | 描述 |
| :--- | :--- |
| 无|  ||

#### 返回值
无

#### 实例
```javascript
window.external.axe.exit();
```

---

## <span id = "axe_exec">axe.exec</span>
#### 定义和用法
**异步**调用外部程序，调用后将立即返回并执行后继代码。

```javascript
window.external.axe.exec(program, args = '')
```

| 参数      | 描述 |
| :---      | :--- |
| program   | 程序路径或系统命令 |
| args      | 调用外部程序时传递的参数，默认值为空字符串 |

#### 返回值
无

#### 实例
```javascript
window.external.axe.log('before');
window.external.axe.exec('notepad.exe');
window.external.axe.log('after');
```

---

## <span id = "axe_execWait">axe.execWait</span>
#### 定义和用法
**同步**调用外部程序，调用后脚本将挂起并等待外部程序执行完毕后，再执行后继代码。

```javascript
window.external.axe.execWait(program, args = '')
```

| 参数      | 描述 |
| :---      | :--- |
| program   | 程序路径或系统命令 |
| args      | 调用外部程序时传递的参数，默认值为空字符串 |

#### 返回值
无

#### 实例
```javascript
window.external.axe.log('before');
window.external.axe.execWait('notepad.exe');
window.external.axe.log('after');
```

---

## <span id = "axe_toString">axe.toString</span>
#### 定义和用法
扩展对象 axe 进行字符串序列化，返回 axe 扩展对象的名称和版本信息。

```javascript
window.external.axe.toString()
```

| 参数      | 描述 |
| :---      | :--- |
| 无   |||

#### 返回值
字符串，说明 axe 对象的名称和版本。

#### 实例
```javascript
alert(window.external.axe);
alert(window.external.axe.toString());
```

---

## <span id = "axe_setTitle">axe.setTitle</span>
#### 定义和用法
设置窗口标题，包括浏览器窗口标题和命令行终端窗口标题。命令行窗口会附加“[console]”字样。如果使用的 axeBrowser 没有注册，则还会附加“【未注册】”字样。

```javascript
window.external.axe.setTitle(title)
```

| 参数  | 描述 |
| :---  | :--- |
| title | 字符串，将设置为窗口的标题。 |

#### 返回值
无

#### 实例
```javascript
window.external.axe.setTitle('这是由 JavaScript 设置的窗口标题');
```

---

## <span id = "axe_scrollPos">axe.scrollPos</span>
#### 定义和用法
改变浏览器窗口的滚动条位置，可使用负数指定相对于右下角的坐标，-1,-1表示滚动到页面右、下角。

```javascript
window.external.axe.setTitle(title)
```

| 参数  | 描述 |
| :---  | :--- |
| x | 数值，横向滚动条的位置。 |
| y | 数值，纵向滚动条的位置。 |

#### 返回值
无

#### 实例
```javascript
window.external.axe.scrollPos(-1, -1);
```
滚动条移动到右下角的位置。

---

## <span id = "axe_file">axe.file</span>
所有相关本地文件操作的功能都归并在 axe.file 中。处于安全的考量，axe.file 仅支持对 axeBrowser 执行文件所在的文件夹或子文件夹内的文件进行操作。此限制为硬编码实现，通过对文件的路径和 axeBrowser 所在文件夹的路径进行比对进行来判断。

*若确有需求，请考虑调整 axeBrowser 的存放位置或以其他方式绕过（例如调用外部程序）。*

---

## <span id = "axe_file_readString">axe.file.readString</span>
#### 定义和用法
以字符串方式读取指定文件，注意该函数将一次性读取文件全部内容到内存后再返回，请不要读取过大的文件。

```javascript
window.external.axe.file.readString(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 要进行读操作的文件名 |

#### 返回值
字符串形式的文件本文内容。如果指定的文件读取失败（例如安全权限限制、文件不存在等），则返回 null。

#### 实例
```javascript
window.external.axe.file.readString('readme.txt');
```

---

## <span id = "axe_file_writeString">axe.file.writeString</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
window.external.axe.file.writeString(filename, content, ifAppend = false);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 要进行写操作的文件名  |
| content   | 要写入的文本内容      |
| ifAppend  | 是否追加模式，默认为否，即覆盖模式。 |

#### 返回值
写入成功返回 true，否则返回 false。

#### 实例
```javascript
window.external.axe.file.writeString('readme.txt', 'this is a test for append.', true);
window.external.axe.file.writeString('readme.txt', 'this is a test for overwrite.');
```
