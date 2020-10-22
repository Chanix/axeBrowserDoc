## <span id = "axe_process">\_\_AXE\_\_.process</span>
进程相关的功能。

---

## <span id = "axe_process_execAXE">\_\_AXE\_\_.process.execAXE</span>
#### 定义和用法
异步调用，执行一个 axeBrowser 的实例。
该实例的执行文件为当前的 axeBrowser.exe，工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串 ''。

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
__AXE__.process.execAXE('-home www.qq.com');
__AXE__.process.execAXE(__AXE__.getArgv());
```
#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值，具体请参阅 PowserShell、cmd 的相关文档。


---

## <span id = "axe_process_execAXEWait">\_\_AXE\_\_.process.execAXEWait</span>
#### 定义和用法
同步调用，执行一个 axeBrowser 的实例。当前应用将等待至该调用执行完毕后方才继续。
该实例的执行文件为当前的 axeBrowser.exe，工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串 ''。

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
__AXE__.process.execAXEWait('-home www.qq.com');
__AXE__.process.execAXEWait(__AXE__.getArgv());
```
#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值，具体请参阅 PowserShell、cmd 的相关文档。


---


## <span id = "axe_process_exec">\_\_AXE\_\_.process.exec</span>
#### 定义和用法
异步调用，执行指定的文件。
该执行文件的工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串''。

```javascript
__AXE__.process.exec(file, args);
```
#### 返回值
调用成功返回 true，其他返回 false。

#### 实例
```javascript
__AXE__.process.exec('cmd', '/C timeout /t 30');
__AXE__.process.exec('notepad');
```

#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值，具体请参阅 PowserShell、cmd 的相关文档。


---

## <span id = "axe_process_execWait">\_\_AXE\_\_.process.execWait</span>
#### 定义和用法
同步调用，执行指定的文件，当前应用将等待至该调用执行完毕后方才继续。
该执行文件的工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串 ''。

```javascript
__AXE__.process.execWait(file, args);
```
#### 返回值
调用成功返回 true，其他返回 false。

#### 实例
```javascript
__AXE__.process.execWait('cmd', '/C timeout /t 30');
__AXE__.process.execWait('notepad');
```
#### 提示
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值，具体请参阅 PowserShell、cmd 的相关文档。


---