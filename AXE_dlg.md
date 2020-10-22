## <span id = "axe_dlg">\_\_AXE\_\_.dlg</span>
各种常用的对话框，消息框等交互小窗口。



---


## <span id = "axe_dlg_openFile">\_\_AXE\_\_.dlg.openFile</span>
#### 定义和用法
打开文件选择对话框，进行文件选择，并返回选取的文件名。
如果没有选择（退出）则返回 null。

```javascript
__AXE__.dlg.openFile(fileType, title, filename)
```

| 参数  | 描述 |
| :---  | :--- |
| fileType | 文件类型 |
| title | 窗口标题 |
| filename | 默认选择的文件名 |

fileType 指定文件类型（后缀名），用“文件说明|通配符”的方式来说明，支持多个，中间用“|”分隔。
例如：“所有文件|\*.\*”、“所有文件|\*.\*|文本文件|\*.txt”；

#### 返回值
未选择（例如点击取消按钮或者按 ESC 键）返回 null，否则返回选取的文件名称。

#### 实例
```javascript
__AXE__.dlg.openFile('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件', 'after.js');
__AXE__.dlg.openFile('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件');
__AXE__.dlg.openFile(null, null, 'after.js');
```

---

## <span id = "axe_dlg_openFileEx">\_\_AXE\_\_.dlg.openFileEx</span>
#### 定义和用法
打开文件选择对话框，进行文件选择，并返回选取的文件名数组，支持多选。
未选择（例如点击取消按钮或者按 ESC 键）返回 null。

```javascript
__AXE__.dlg.openFileEx(fileType, title, dir)
```

| 参数  | 描述 |
| :---  | :--- |
| fileType | 文件类型 |
| title | 窗口标题 |
| dir | 默认文件夹 |

fileType 指定文件类型（后缀名），用“文件说明|通配符”的方式来说明，支持多个，中间用“|”分隔。
例如：“所有文件|\*.\*”、“所有文件|\*.\*|文本文件|\*.txt”；

#### 返回值
未选择（例如点击取消按钮或者按 ESC 键）返回 null。
否则返回数组，其中的元素为选取的文件名称。

#### 实例
```javascript
__AXE__.dlg.openFileEx('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件');
```


---


## <span id = "axe_dlg_saveFile">\_\_AXE\_\_.dlg.saveFile</span>
#### 定义和用法
文件保存对话框，返回选取的文件名。
如果没有选择（退出）则返回 null。

```javascript
__AXE__.dlg.saveFile(fileType, title, filename)
```

| 参数  | 描述 |
| :---  | :--- |
| fileType | 文件类型 |
| title | 窗口标题 |
| filename | 默认文件名 |

fileType 指定文件类型（后缀名），用“文件说明|通配符”的方式来说明，支持多个，中间用“|”分隔。
例如：“所有文件|\*.\*”、“所有文件|\*.\*|文本文件|\*.txt”；

#### 返回值
未选择（例如点击取消按钮或者按 ESC 键）返回 null。否则返回选取的文件名称。

#### 实例
```javascript
__AXE__.dlg.saveFile('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件');
```


---




## <span id = "axe_dlg_openDir">\_\_AXE\_\_.dlg.openDir</span>
#### 定义和用法
打开文件夹选择框，返回选取的文件夹名称。
如果没有选择（退出）则返回 null。

```javascript
__AXE__.dlg.openDir(dir, title, label)
```

| 参数  | 描述 |
| :---  | :--- |
| dir | 文件夹名称 |
| title | 窗口标题 |
| label | 标题 |

#### 返回值
取消 null
否则返回选取的文件夹名称。

#### 实例
```javascript
__AXE__.dlg.openDir();
```


---


## <span id = "axe_dlg_openDirEx">\_\_AXE\_\_.dlg.openDirEx</span>
#### 定义和用法
打开文件夹选择框，返回选取的文件夹名称，支持多选。
如果没有选择（退出）则返回 null。

```javascript
__AXE__.dlg.openDirEx(dir, title, label, multi)
```

| 参数  | 描述 |
| :---  | :--- |
| dir | 文件夹名称 |
| title | 窗口标题 |
| label | 标题 |
| multi | 是否多选 |

#### 返回值
取消 null
否则返回选取的文件夹名称数组。

#### 实例
```javascript
__AXE__.dlg.openDirEx();
```


---


## <span id = "axe_dlg_msgboxInfo">\_\_AXE\_\_.dlg.msgboxInfo</span>
#### 定义和用法
显示信息提示对话框，如果设定了超时时间，则超时自动关闭。

```javascript
__AXE__.dlg.msgboxInfo(text, title, timeout)
```

| 参数  | 描述 |
| :---  | :--- |
| text | 提示信息内容 |
| title | 窗口标题 |
| timeout | 超时时间（毫秒） |

#### 返回值
1

#### 实例
```javascript
__AXE__.dlg.msgboxInfo(`显示的信息提示内容`, `信息提示窗口的标题`);
__AXE__.dlg.msgboxInfo(`这个提示窗口 5 秒后自动关闭`, `信息提示窗口的标题`, 5000);
```


---


## <span id = "axe_dlg_msgboxErr">\_\_AXE\_\_.dlg.msgboxErr</span>
#### 定义和用法
显示错误提示对话框

```javascript
__AXE__.dlg.msgboxErr(text, title)
```

| 参数  | 描述 |
| :---  | :--- |
| text | 提示信息内容 |
| title | 窗口标题 |

#### 返回值
1

#### 实例
```javascript
__AXE__.dlg.msgboxErr(`显示的信息提示内容`, `信息提示窗口的标题`);
```


---


## <span id = "axe_dlg_msgboxOkCancel">\_\_AXE\_\_.dlg.msgboxOkCancel</span>
#### 定义和用法
显示选择对话框，用户可以选择“确认”或“取消”

```javascript
__AXE__.dlg.msgboxOkCancel(text, title)
```

| 参数  | 描述 |
| :---  | :--- |
| text | 提示信息内容 |
| title | 窗口标题 |

#### 返回值
用户选择确认返回 true，其他情况返回 false

#### 实例
```javascript
__AXE__.dlg.msgboxOkCancel(`显示的信息提示内容`, `信息提示窗口的标题`);
```
