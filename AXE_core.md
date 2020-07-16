## <span id = "axe">\_\_AXE\_\_</span>


## <span id = "axe_clone">\_\_AXE\_\_.clone</span>
#### 定义和用法
以当前的工作目录、命令行参数再启动（克隆）一个相同的实例。


```javascript
__AXE__.clone()
```

| 参数 | 描述 |
| :--- | :--- |
| 无|  ||

#### 返回值
无

#### 实例
```javascript
__AXE__.clone();
```

---


## <span id = "axe_exit">\_\_AXE\_\_.exit</span>
#### 定义和用法
发送程序终止消息，立即退出 axeBrowser。


```javascript
__AXE__.exit()
```

| 参数 | 描述 |
| :--- | :--- |
| 无|  ||

#### 返回值
无

#### 实例
```javascript
__AXE__.exit();
```

---

## <span id = "axe_getArgv">\_\_AXE\_\_.getArgv</span>
#### 定义和用法
用于提取执行 axeBrowser 时，指定的命令行参数值。


```javascript
__AXE__.getArgv(arg_name)
```

| 参数 | 描述 |
| :--- | :--- |
| arg_name | 字符串，命令行参数的名称 |

#### 返回值
指定命令行参数的值。若该指定名称的命令行参数不存在，返回 null。如果存在但没有赋值，返回 ""。

若调用参数未指定名称或名称为 ""，则返回整个命令行参数。

#### 提示
由于特殊字符和命令行环境的存在，指定命令行参数时，请按实际情况进行转义。建议用双引号 “"”  将参数值包含起来。

#### 实例
命令行：
```
axeBrowser -home axebrowser.com -p1 test1 -p2;
```

| 调用值 | 返回值 | 描述 |
| :--- | :--- | :--- |
| \_\_AXE\_\_.getArgv('home')   | 'axebrowser.com'  | 指定了参数指定了值 |
| \_\_AXE\_\_.getArgv('p1')     | 'test1'   | 指定了参数指定了值 |
| \_\_AXE\_\_.getArgv('p2')     | ''        | 指定了参数，没有指定值，返回空字符串 |
| \_\_AXE\_\_.getArgv('home')   | null      | 没有指定参数，返回 null |
| \_\_AXE\_\_.getArgv()   | -home axebrowser.com -p1 test1 -p2      | 整个命令行参数 |


---


## <span id = "axe_log">\_\_AXE\_\_.log</span>
#### 定义和用法
在命令行窗口中显示日志，如果命令行窗口没有打开将自动打开。支持多个参数，显示时多个参数间使用制表符分隔，并且在最后换行。


```javascript
__AXE__.log(p1, p2, p3 ...)
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
__AXE__.log();
__AXE__.log('This is a string');
__AXE__.log(null);
__AXE__.log('String', 12345, null, 4+5, 'Str'=='Str');

```
输出：

```javascript

This is a string

String  12345   null    9       true
```

---

## <span id = "axe_setHome">\_\_AXE\_\_.setHome</span>
#### 定义和用法
设置要打开的首页网址。可以通过在 prescript 中调用本方法来动态设置要打开的首页网址。
打开网址时，如果设置了首页则以设置为准，未设置以命令行参数 -home 为准，如果依然没有，则打开默认首页。

```javascript
__AXE__.setHome(url)
```

| 参数  | 描述 |
| :---  | :--- |
| url | 首页网址 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setHome('axeBrowser.com');
```

---


## <span id = "axe_setScripts">\_\_AXE\_\_.setScripts</span>
#### 定义和用法
设置要打开网址后运行的脚本。可以通过在 prescript 中调用本方法来动态设置要执行的脚本。
执行网址后脚本时，如果调用设置了脚本则以设置为准，未设置以命令行参数 -script 为准。

```javascript
__AXE__.setScripts(file_name)
```

| 参数  | 描述 |
| :---  | :--- |
| file_name | 脚本文件名 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setScripts('after.js');
```

---


## <span id = "axe_setEntryPoint">\_\_AXE\_\_.setEntryPoint</span>
#### 定义和用法
设置要打开网址后运行的脚本的入口函数。可以通过在 prescript 中调用本方法来动态设置要执行的脚本入口函数。
执行网址后脚本时，如果调用设置了脚本则以设置为准，未设置以命令行参数 -entrypoint 为准。

```javascript
__AXE__.setEntryPoint(fn_name)
```

| 参数  | 描述 |
| :---  | :--- |
| fn_name | 入口函数名 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setEntryPoint('entrypoint');
```

---

## <span id = "axe_setTimeout">\_\_AXE\_\_.setTimeout</span>
#### 定义和用法
设置应用执行时间。可以通过在 prescript 中调用本方法来动态设置应用的执行时间。
如果设置了则以设置为准，未设置以命令行参数 -timeout 为准。达到了最长执行时间后，应用会自动退出。

```javascript
__AXE__.setTimeout(timeout_ms)
```

| 参数  | 描述 |
| :---  | :--- |
| timeout_ms | 时间，毫秒 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setTimeout(60000);
```


---


## <span id = "axe_restart">\_\_AXE\_\_.restart</span>
#### 定义和用法
重新启动当前应用。实际上，是先克隆（clone）一个新的副本，然后将原有的退出（exit）。


```javascript
__AXE__. restart()
```

| 参数 | 描述 |
| :--- | :--- |
| 无|  ||

#### 返回值
无

#### 实例
```javascript
__AXE__.restart();
```


---


## <span id = "axe_toString">\_\_AXE\_\_.toString</span>
#### 定义和用法
返回 \_\_AXE\_\_ 扩展对象的名称和版本信息。

```javascript
__AXE__.toString()
```

| 参数      | 描述 |
| :---      | :--- |
| 无   |||

#### 返回值
返回 \_\_AXE\_\_ 扩展对象的名称和版本信息。

#### 实例
```javascript
alert(__AXE__);
alert(__AXE__.toString());
```

---

## <span id = "axe_setTitle">\_\_AXE\_\_.setTitle</span>
#### 定义和用法
设置窗口标题，包括浏览器窗口标题和命令行窗口标题，非 VIP 版会附加“【免费版】”字样。
请注意，如果当前没有打开命令行窗口，那么不会设置命令行窗口的标题。

```javascript
__AXE__.setTitle(title)
```

| 参数  | 描述 |
| :---  | :--- |
| title | 字符串，将设置为窗口的标题。 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setTitle('这是由 JavaScript 设置的窗口标题');
```


---


## <span id = "axe_getHeight">\_\_AXE\_\_.getHeight</span>
#### 定义和用法
获取主窗口高度

```javascript
__AXE__.getHeight()
```

#### 返回值
主窗口高度

#### 实例
```javascript
__AXE__.getHeight();
```

---


## <span id = "axe_setHeight">\_\_AXE\_\_.setHeight</span>
#### 定义和用法
设置主窗口高度

```javascript
__AXE__.setHeight(height)
```

| 参数  | 描述 |
| :---  | :--- |
| height | 主窗口高度 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setHeight(600);
```


---


## <span id = "axe_getWidth">\_\_AXE\_\_.getWidth</span>
#### 定义和用法
获取主窗口宽度

```javascript
__AXE__.getWidth()
```

#### 返回值
主窗口宽度

#### 实例
```javascript
__AXE__.getWidth();
```

---


## <span id = "axe_setWidth">\_\_AXE\_\_.setWidth</span>
#### 定义和用法
设置主窗口宽度

```javascript
__AXE__.setWidth(width)
```

| 参数  | 描述 |
| :---  | :--- |
| width | 主窗口宽度 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setWidth(800);
```


---


## <span id = "axe_isFullScreen">\_\_AXE\_\_.isFullScreen</span>
#### 定义和用法
当前主窗口是否为全屏显示状态。

```javascript
__AXE__.isFullScreen
```

#### 返回值
true 全屏，false 非全屏

#### 实例
```javascript
if (__AXE__.isFullScreen) { alert('当前为全屏显示状态'); };
```


---


## <span id = "axe_setFullScreen">\_\_AXE\_\_.setFullScreen</span>
#### 定义和用法
设置主窗口全屏显示，参数为 true 设置为全屏显示，false 取消全屏显示。可以通过 isFullScreen 来获取当前的显示状态。

注意，窗口必须显示才可以进行全屏设置，如果窗口处于最小化状态，调用无效。

```javascript
__AXE__.setFullScreen(fullscreen)
```

| 参数  | 描述 |
| :---  | :--- |
| fullscreen | 是否全屏 |

#### 返回值
无

#### 实例
```javascript
__AXE__.setFullScreen(true);
__AXE__.setFullScreen(false);
```




































---




## <span id = "axe_scrollPos">\_\_AXE\_\_.scrollPos</span>
#### 定义和用法
改变浏览器窗口的滚动条位置，可使用负数指定相对于右下角的坐标，-1,-1表示滚动到页面右、下角。

```javascript
__AXE__.scrollPos(x, y)
```

| 参数  | 描述 |
| :---  | :--- |
| x | 数值，横向滚动条的位置。 |
| y | 数值，纵向滚动条的位置。 |

#### 返回值
无

#### 实例
```javascript
__AXE__.scrollPos(-1, -1);
```
滚动条移动到右下角的位置。

---

## <span id = "axe_file">\_\_AXE\_\_.file</span>
所有相关本地文件操作的功能都归并在 __AXE__.file 中。

---

## <span id = "axe_file_readString">\_\_AXE\_\_.file.readString</span>
#### 定义和用法
以字符串方式读取指定文件，注意该函数将一次性读取文件全部内容到内存后再返回，请不要读取过大的文件。

```javascript
__AXE__.file.readString(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 要进行读操作的文件名 |

#### 返回值
字符串形式的文件本文内容。如果指定的文件读取失败（例如安全权限限制、文件不存在等），则返回 null。

#### 实例
```javascript
__AXE__.file.readString('readme.txt');
```

---

## <span id = "axe_file_writeString">\_\_AXE\_\_.file.writeString</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
__AXE__.file.writeString(filename, content, ifAppend = false);
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
__AXE__.file.writeString('readme.txt', 'this is a test for append.', true);
__AXE__.file.writeString('readme.txt', 'this is a test for overwrite.');
```


---

## <span id = "axe_win_clip_read">\_\_AXE\_\_.win.clip.read</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
__AXE__.win.clip.read();
```

#### 返回值
剪贴板中的内容（字符串）。

#### 实例
```javascript
__AXE__.win.clip.read();
```


---

## <span id = "axe_win_clip_write">\_\_AXE\_\_.win.clip.write</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
__AXE__.win.clip.write(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要写入剪贴板的内容（字符串）  |

#### 返回值
无。

#### 实例
```javascript
__AXE__.win.clip.write('axeBrowser is great!');
```

---

## <span id = "axe_win_getProcessId">\_\_AXE\_\_.win.getProcessId</span>
#### 定义和用法
获取当前应用的进程id。

```javascript
__AXE__.win.getProcessId();
```

#### 返回值
进程id。

#### 实例
```javascript
__AXE__.log('当前进程号：', __AXE__.win.getProcessId());
```

---

## <span id = "axe_win_getThreadId">\_\_AXE\_\_.win.getThreadId</span>
#### 定义和用法
获取当前应用主窗口的线程id。

```javascript
__AXE__.win.getThreadId();
```

#### 返回值
进程id。

#### 实例
```javascript
__AXE__.log('当前线程号：', __AXE__.win.getThreadId());
```

---

## <span id = "axe_win_getenv">\_\_AXE\_\_.win.getenv</span>
#### 定义和用法
获取环境变量值。

```javascript
__AXE__.win.getenv(envname);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |

#### 返回值
指定环境变量值，若未指定返回空。

#### 实例
```javascript
__AXE__.log('环境变量 PATH：', __AXE__.win.getenv('path'));
```

## <span id = "axe_win_setenv">\_\_AXE\_\_.win.setenv</span>
#### 定义和用法
设置环境变量值。

```javascript
__AXE__.win.getenv(envname, value);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |
| value  | 环境变量的值  |

#### 返回值
设置环境变量。

#### 实例
```javascript
__AXE__.win.setenv('TTT', 'ttt');
```

## <span id = "axe_win_addenv">\_\_AXE\_\_.win.addenv</span>
#### 定义和用法
设置环境变量值（仅当该环境变量不存在时）。

```javascript
__AXE__.win.addenv(envname, value);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |
| value  | 环境变量的值  |

#### 返回值
设置环境变量。

#### 实例
```javascript
__AXE__.win.addenv('TTT', 'ttt');
```


## <span id = "axe_process">\_\_AXE\_\_.process</span>
所有进程相关的功能

## <span id = "axe_process_execAXE">\_\_AXE\_\_.process.execAXE</span>
#### 定义和用法
**异步**调用，执行一个 axeBrowser 的实例。
该实例的执行文件为当前的 axeBrowser.exe，工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串''。

```javascript
__AXE__.process.execAXE(args);
```

| 参数      | 描述 |
| :---      | :--- |
| args  | 命令行参数，默认为 ''。  |

#### 返回值
调用成功返回 true，其他返回 false。

#### 实例
```javascript
__AXE__.process.execAXE();
__AXE__.process.execAXE('-home axebrowser.com');
__AXE__.process.execAXE(__AXE__.getArgv());
```
#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值。


---

## <span id = "axe_process_execAXEWait">\_\_AXE\_\_.process.execAXEWait</span>
#### 定义和用法
**同步**调用，执行一个 axeBrowser 的实例。当前应用将等待至该调用执行完毕后方才继续。
该实例的执行文件为当前的 axeBrowser.exe，工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串''。

```javascript
__AXE__.process.execAXEWait(args);
```

| 参数      | 描述 |
| :---      | :--- |
| args  | 命令行参数，默认为 ''。  |

#### 返回值
调用成功返回 true，其他返回 false。

#### 实例
```javascript
__AXE__.process.execAXEWait();
__AXE__.process.execAXEWait('-home axebrowser.com');
__AXE__.process.execAXEWait(__AXE__.getArgv());
```
#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值。


---


