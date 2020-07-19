## <span id = "axe_dlg">\_\_AXE\_\_.dlg</span>
各种常用的对话框，消息框等交互小窗口。

## <span id = "axe_dlg_parameter_note">参数说明</span>
  * 本模块经常使用到一些参数，需要按照约定来传参：
  * 本模块很多参数可以忽略，如果是最后一个参数，可以直接忽略，反之则需要用 null 来占位；
  * 若忽略了某些参数，则自动使用默认值；

### fileType 
指定文件类型（后缀名），用“文件说明|通配符”的方式来说明，支持多个，中间用“|”分隔。
例如：“所有文件|\*.\*”、“所有文件|\*.\*|文本文件|\*.txt”；

### title
对话框窗口的标题，可以忽略；

### filename
文件名称


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
| title | 对话框窗口标题 |
| filename | 默认选择的文件名 |

#### 返回值
取消 null
否则返回选取的文件名称。

#### 实例
```javascript
__AXE__.dlg.openFile('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件', 'after.js');
__AXE__.dlg.openFile('所有文件|*.*|文本文件|*.txt|JavaScript|*.js', '请选择文件');
__AXE__.dlg.openFile(null, null, 'after.js');
```

---

## <span id = "axe_dlg_openFileEx">\_\_AXE\_\_.dlg.openFileEx</span>
#### 定义和用法
打开文件选择对话框，进行文件选择，并返回选取的文件名，支持多选。
如果没有选择（退出）则返回 null。

```javascript
__AXE__.dlg.openFileEx(fileType, title, dir)
```

| 参数  | 描述 |
| :---  | :--- |
| fileType | 文件类型 |
| title | 对话框窗口标题 |
| dir | 默认文件夹 |

#### 返回值
取消 null
否则返回数组，元素为选取的文件名称。

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
| title | 对话框窗口标题 |
| filename | 默认文件名 |

#### 返回值
取消 null
否则返回选取的文件名称。

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
