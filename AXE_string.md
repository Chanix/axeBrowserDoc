# <span id = "axe_string">\_\_AXE\_\_.string</span>
字符串处理

## <span id = "axe_string_format">\_\_AXE\_\_.string.format</span>
#### 定义和用法
格式化字符串，提供类似其他语言中 %s %d 之类的格式化功能。

就个人而言，苦 js 无 string.format 久矣……

```javascript
__AXE__.string.format(format_str, ...);
```

| 参数 | 描述 |
| :--- | :--- |
| format_str | 格式字符串 |
| ... | 对应格式化字符串中的参数 |

#### 返回值
返回经过格式化后的字符串

#### 实例
```javascript
__AXE__.string.format('This is test for %s 111 %s 222 %s', 'FORMAT', 'para1', 2);
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
无。

#### 实例
```javascript
__AXE__.clipboard.write('axeBrowser is great!');
```
