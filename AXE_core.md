## <span id = "axe">\_\_AXE\_\_</span>
基础功能。

---


## <span id = "axe_clone">\_\_AXE\_\_.clone</span>
#### 定义和用法
以当前的工作目录、命令行参数再启动（克隆）一个相同的实例。


```javascript
__AXE__.clone()
```

#### 返回值
null

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

#### 返回值
null

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
null

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
null

#### 实例
```javascript
__AXE__.setScripts('after.js');
```
基础扩展，提供应用整体相关的功能。

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
null

#### 实例
```javascript
__AXE__.setEntryPoint('entrypoint');
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
null

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

