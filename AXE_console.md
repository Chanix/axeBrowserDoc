# <span id = "axe_console">\_\_AXE\_\_.console</span>
主控台窗口相关的功能


---


## <span id = "axe_console_COLOR">\_\_AXE\_\_.console.\_COLOR\_???</span>
主控台窗口颜色定义，可用于字符显示的前景色和背景色。

| 名称      | 说明 |
| :---      | :--- |
|	\_\_AXE\_\_.console._COLOR_BLUE			| 蓝色      |
|	\_\_AXE\_\_.console._COLOR_BLACK		| 黑色      |
|	\_\_AXE\_\_.console._COLOR_DARKBLUE		| 暗蓝色    |
|	\_\_AXE\_\_.console._COLOR_DARKGREEN	| 暗绿色    |
|	\_\_AXE\_\_.console._COLOR_DRAKCYAN		| 暗青色    |
|	\_\_AXE\_\_.console._COLOR_DARKRED		| 暗红色    |
|	\_\_AXE\_\_.console._COLOR_DARKMAGENTA	| 暗紫色    |
|	\_\_AXE\_\_.console._COLOR_DRAKYELLOW	| 暗黄色    |
|	\_\_AXE\_\_.console._COLOR_GRAY			| 灰色      |
|	\_\_AXE\_\_.console._COLOR_DARKGRAY		| 深灰色    |
|	\_\_AXE\_\_.console._COLOR_GREEN		| 绿色      |
|	\_\_AXE\_\_.console._COLOR_CYAN			| 青色      |
|	\_\_AXE\_\_.console._COLOR_RED			| 红色      |
|	\_\_AXE\_\_.console._COLOR_MAGENTA		| 紫色      |
|	\_\_AXE\_\_.console._COLOR_YELLOW		| 黄色      |
|	\_\_AXE\_\_.console._COLOR_WHITE		| 白色      |

---


## <span id = "axe_console_clear">\_\_AXE\_\_.console.clear</span>
#### 定义和用法
清屏。

```javascript
__AXE__.console.clear();
```

#### 返回值
null

#### 实例
```javascript
__AXE__.console.clear();
```


---


## <span id = "axe_console_close">\_\_AXE\_\_.console.close</span>
#### 定义和用法
关闭控制台

```javascript
__AXE__.console.close();
```

#### 返回值
null

#### 实例
```javascript
__AXE__.console.close();
```


---


## <span id = "axe_console_pause">\_\_AXE\_\_.console.pause</span>
#### 定义和用法
暂停，按任意键继续（若当前主控台窗口未打开，则自动打开）

```javascript
__AXE__.console.pause(ifClose, text);
```

| 参数      | 描述 |
| :---      | :--- |
| ifClose  | 按键后是否关闭主控台窗口，默认为 false |
| text  | 提示内容，默认为 “请按任意键继续 ...  ” |


#### 返回值
用户按键键码

#### 实例
```javascript
__AXE__.console.pause();  // 缩略形式，等价于 __AXE__.console.pause(false, '请按任意键继续 ... ');
__AXE__.console.pause(true, '按任意键后继续并关闭主控台窗口');
__AXE__.console.pause(false, '按任意键后继续但不关闭主控台窗口');
```


---


## <span id = "axe_console_getTitle">\_\_AXE\_\_.console.getTitle</span>
#### 定义和用法
获取主控台窗口的窗口标题

```javascript
__AXE__.console.getTitle();
```

#### 返回值
主控台窗口的窗口标题

#### 实例
```javascript
__AXE__.console.getTitle();
```


---


## <span id = "axe_console_setTitle">\_\_AXE\_\_.console.setTitle</span>
#### 定义和用法
设置主控台窗口的窗口标题（若当前主控台窗口未打开，则自动打开）

```javascript
__AXE__.console.setTitle(text);
```

| 参数      | 描述 |
| :---      | :--- |
| text  | 欲设置的窗口标题内容，默认为空字符串 '' |


#### 返回值
null

#### 实例
```javascript
__AXE__.console.setTitle('新的主控台窗口标题');
```


---


## <span id = "axe_console_open">\_\_AXE\_\_.console.open</span>
#### 定义和用法
打开主控台窗口，若已打开则不进行任何操作，默认启用 UTF-8 编码。

启用 UTF-8 编码在 win10 以下系统可能出现显示不正常的问题。

```javascript
__AXE__.console.open(ifUtf8);
```

| 参数      | 描述 |
| :---      | :--- |
| ifUtf8  | 是否启用 UTF-8 编码，默认为 true |

#### 返回值
null

#### 实例
```javascript
__AXE__.console.open();         // 等价于 __AXE__.console.open(true);
__AXE__.console.open(true);     //
__AXE__.console.open(false);    //
```


---


## <span id = "axe_console_log">\_\_AXE\_\_.console.log</span>
#### 定义和用法
在主控台窗口中显示日志。支持多个参数，显示时多个参数间使用制表符分隔，并且在最后换行。
（若当前主控台窗口未打开，则自动打开）

```javascript
__AXE__.console.log(p1, p2, p3 ...)
```

| 参数 | 描述 |
| :--- | :--- |
| p1, p2, p3 ... | 要显示的内容，可以为变量或者表达式 |

#### 返回值
null

#### 提示
如果参数不是字符串类型，那么将试图自动转换为字符串后再显示。

#### 实例
脚本：
```javascript
__AXE__.console.log();
__AXE__.console.log('This is a string');
__AXE__.console.log(null);
__AXE__.console.log('String', 12345, null, 4+5, 'Str'=='Str');

```
输出：

```javascript

This is a string

String  12345   null    9       true
```


---


## <span id = "axe_console_colorlog">\_\_AXE\_\_.console.colorlog</span>
#### 定义和用法
用自定义前景色和背景色在主控台窗口中显示日志。
（若当前主控台窗口未打开，则自动打开）


```javascript
__AXE__.console.colorlog(text_color, back_color, p1, p2, p3 ...)
```

| 参数 | 描述 |
| :--- | :--- |
| text_color | 前景色 |
| back_color | 背景色 |
| p1, p2, p3 ... | 要显示的内容，可以为变量或者表达式 |

前景色和背景色，请使用 \_\_AXE\_\_.console 中以 \_COLOR\_ 开头的常量，例如：\_\_AXE\_\_.console.\_COLOR\_RED。

背景色可以为 null，即使用当前的背景色。

除了可指定颜色，其他和 log 一致，不再赘述。


---