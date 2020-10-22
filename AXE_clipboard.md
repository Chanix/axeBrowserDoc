# <span id = "axe_clipboard">\_\_AXE\_\_.clipboard</span>
剪贴板相关的功能。


---


## <span id = "axe_clipboard_read">\_\_AXE\_\_.clipboard.read</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
__AXE__.clipboard.read();
```

#### 返回值
剪贴板中的内容（字符串）。

#### 实例
```javascript
__AXE__.clipboard.read();
```


---


## <span id = "axe_clipboard_write">\_\_AXE\_\_.clipboard.write</span>
#### 定义和用法
将指定的内容以字符串方式写入文件，可以指定追加或者覆盖模式。执行时会自动创建所需的所有文件夹。

```javascript
__AXE__.clipboard.write(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要写入剪贴板的内容（字符串）  |

#### 返回值
null

#### 实例
```javascript
__AXE__.clipboard.write('axeBrowser is great!');
```
