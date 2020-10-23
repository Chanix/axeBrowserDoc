# <span id = "axe_fsys">\_\_AXE\_\_.fsys</span>
文件系统相关的功能


---


## <span id = "axe_fsys_canRead">\_\_AXE\_\_.fsys.canRead</span>
#### 定义和用法
指定文件是否可读

```javascript
__AXE__.fsys.canRead(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
可读返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.canRead('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_canWrite">\_\_AXE\_\_.fsys.canWrite</span>
#### 定义和用法
指定文件是否可写

```javascript
__AXE__.fsys.canWrite(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
可写返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.canWrite('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_canReadWrite">\_\_AXE\_\_.fsys.canReadWrite</span>
#### 定义和用法
指定文件是否可读写

```javascript
__AXE__.fsys.canReadWrite(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
可读写返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.canReadWrite('C:\\Windows\\regedit.exe');
```

---


## <span id = "axe_fsys_exists">\_\_AXE\_\_.fsys.exists</span>
#### 定义和用法
指定文件或文件夹是否存在

```javascript
__AXE__.fsys.exists(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名或文件夹名  |

#### 返回值
存在返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.exists('C:\\Windows\\');
__AXE__.fsys.exists('C:\\Windows\\regedit.exe');
__AXE__.fsys.exists('C:\\Windows.old\\');
```


---


## <span id = "axe_fsys_isDir">\_\_AXE\_\_.fsys.isDir</span>
#### 定义和用法
指定的路径是否文件夹

```javascript
__AXE__.fsys.isDir(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名或文件夹名  |

#### 返回值
是文件夹返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.isDir('C:\\Windows\\');
__AXE__.fsys.isDir('C:\\Windows\\regedit.exe');
```

---


## <span id = "axe_fsys_isFile">\_\_AXE\_\_.fsys.isFile</span>
#### 定义和用法
指定的路径是否文件夹

```javascript
__AXE__.fsys.isFile(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名或文件夹名  |

#### 返回值
是文件返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.isFile('C:\\Windows\\');
__AXE__.fsys.isFile('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_isHidden">\_\_AXE\_\_.fsys.isHidden</span>
#### 定义和用法
指定文件是否隐藏模式

```javascript
__AXE__.fsys.isHidden(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
文件为隐藏模式返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.isHidden('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_isReadonly">\_\_AXE\_\_.fsys.isReadonly</span>
#### 定义和用法
指定文件是否只读模式

```javascript
__AXE__.fsys.isReadonly(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
文件为只读模式返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.isReadonly('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_isSystemFile">\_\_AXE\_\_.fsys.isSystemFile</span>
#### 定义和用法
指定文件是否为系统文件

```javascript
__AXE__.fsys.isSystemFile(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
文件为系统文件返回 true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.isSystemFile('C:\\Windows\\regedit.exe');
```


---


## <span id = "axe_fsys_fullpath">\_\_AXE\_\_.fsys.fullpath</span>
#### 定义和用法
返回指定文件的全路径名

```javascript
__AXE__.fsys.fullpath(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
指定文件的全路径名

#### 实例
```javascript
__AXE__.fsys.fullpath('C:\\Windows\\regedit.exe');
```

---


## <span id = "axe_fsys_flistFiles">\_\_AXE\_\_.fsys.listFiles</span>
#### 定义和用法
返回指定文件夹下符合要求的所有文件名称

```javascript
__AXE__.fsys.listFiles(dir, wildcard, recursive);
```

| 参数      | 描述 |
| :---      | :--- |
| dir  | 文件夹名  |
| wildcard  | 文件名通配符  |
| recursive  | 是否包含子文件夹  |

#### 返回值
返回指定文件夹下符合要求的所有文件名称

#### 实例
```javascript
__AXE__.fsys.listFiles('C:\\Windows\\debug\\');
```


---


## <span id = "axe_fsys_readFileToString">\_\_AXE\_\_.fsys.readFileToString</span>
#### 定义和用法
读取指定文件，以字符串形式返回其内容。

```javascript
__AXE__.fsys.readFileToString(filename);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |

#### 返回值
文件内容（字符串）

#### 实例
```javascript
__AXE__.fsys.readFileToString('C:\\Windows\\System32\\drivers\\etc\\hosts');
```


---


## <span id = "axe_fsys_writeStringToFile">\_\_AXE\_\_.fsys.writeStringToFile</span>
#### 定义和用法
将内容写入文件。

```javascript
__AXE__.fsys.writeStringToFile(filename, content, ifAppend);
```

| 参数      | 描述 |
| :---      | :--- |
| filename  | 文件名  |
| content  | 写入的内容  |
| ifAppend  | 是否追加模式，默认为否，即覆盖模式  |

#### 返回值
成功返回  true，其他返回 false

#### 实例
```javascript
__AXE__.fsys.writeStringToFile('D:\\test.txt', 'this is a test', false);
```
