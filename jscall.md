# JavaScript 扩展
axeBrowser 在不断的更新和完善中，因此内置的扩展也会有修改和增减。在进行修改和增减时，会尽量的保持兼容性，使原有的脚本无需进行修改。请随时关注最新的文档说明。

---

## <span id = "axe">\_\_AXE\_\_</span>
axeBrowser 为浏览器提供了扩展，可以在 JavaScript 代码中通过预设变量 “\_\_AXE\_\_” 获得，并通过其进行功能扩展。

这个变量是否存在可以作为当前是否 axeBrowser 环境的判断依据。注册版可以修改这个预设变量的变量名。

例如：
```javascript
if (__AXE__ == null) {
    alert('请检查：当前运行环境似乎不是 axeBrowser ？');
} else {
    alert(__AXE__);
}
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
一个字符串，值为指定命令行参数的值。若没有指定该参数或参数为空字符串，则返回当前应用的整个命令行参数。若指定了该参数，但没有定义值，则返回空字符串。

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

## <span id = "axe_exec">\_\_AXE\_\_.exec</span>
#### 定义和用法
**异步**调用外部程序，调用后将立即返回并执行后继代码。

```javascript
__AXE__.exec(program, args = '')
```

| 参数      | 描述 |
| :---      | :--- |
| program   | 程序路径或系统命令 |
| args      | 调用外部程序时传递的参数，默认值为空字符串 |

#### 返回值
无

#### 实例
```javascript
__AXE__.log('before');
__AXE__.exec('notepad.exe');
__AXE__.log('after');
```

---

## <span id = "axe_execWait">\_\_AXE\_\_.execWait</span>
#### 定义和用法
**同步**调用外部程序，调用后脚本将挂起并等待外部程序执行完毕后，再执行后继代码。

```javascript
__AXE__.execWait(program, args = '')
```

| 参数      | 描述 |
| :---      | :--- |
| program   | 程序路径或系统命令 |
| args      | 调用外部程序时传递的参数，默认值为空字符串 |

#### 返回值
无

#### 实例
```javascript
__AXE__.log('before');
__AXE__.execWait('notepad.exe');
__AXE__.log('after');
```

---

## <span id = "axe_toString">\_\_AXE\_\_.toString</span>
#### 定义和用法
扩展对象 axe 进行字符串序列化，返回 axe 扩展对象的名称和版本信息。

```javascript
__AXE__.toString()
```

| 参数      | 描述 |
| :---      | :--- |
| 无   |||

#### 返回值
字符串，说明 axe 对象的名称和版本。

#### 实例
```javascript
alert(__AXE__);
alert(__AXE__.toString());
```

---

## <span id = "axe_setTitle">\_\_AXE\_\_.setTitle</span>
#### 定义和用法
设置窗口标题，包括浏览器窗口标题和命令行终端窗口标题。命令行窗口会附加“[console]”字样。如果使用的 axeBrowser 没有注册，则还会附加“【未注册】”字样。

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


## <span id = "axe_process_exec">\_\_AXE\_\_.process.exec</span>
#### 定义和用法
**异步**调用，执行指定的文件。
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
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值。


---

## <span id = "axe_process_execWait">\_\_AXE\_\_.process.execWait</span>
#### 定义和用法
**同步**调用，执行指定的文件，当前应用将等待至该调用执行完毕后方才继续。
该执行文件的工作目录为 axeBrowser.exe 所在的文件夹。
通过 args 来传递调用时的命令行参数，默认为空字符串''。

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
请注意通过 args 传递命令行参数时的特殊字符处理，例如通过双引号包括参数值。


---

## <span id = "axe_crypt">\_\_AXE\_\_.crypt</span>
所有编码解码相关的功能

---

## <span id = "axe_crypt_aes_encrypt">\_\_AXE\_\_.crypt.aes.encrypt</span>
#### 定义和用法
用 aes 算法进行加密。

```javascript
__AXE__.crypt.aes.encrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行加密的字符串 |
| key | 密钥 |

#### 返回值
经过加密的密文。

#### 实例
```javascript
__AXE__.crypt.aes.encrypt('contentToAES', 'secret');
```

---

## <span id = "axe_crypt_aes_decrypt">\_\_AXE\_\_.crypt.aes.decrypt</span>
#### 定义和用法
用 aes 算法进行解密

```javascript
__AXE__.crypt.aes.decrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行解密的字符串 |
| key | 密钥 |

#### 返回值
经过解密的明文。

#### 实例
```javascript
__AXE__.crypt.aes.decrypt('contentToAES', 'secret');
```


---


## <span id = "axe_crypt_base64_encode">\_\_AXE\_\_.crypt.base64.encode</span>
#### 定义和用法
对字符串进行 base64 编码

```javascript
__AXE__.crypt.base64.encode(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要编码的字符串 |

#### 返回值
经过编码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.encode('contentToBase64');
```


---


## <span id = "axe_crypt_base64_decode">\_\_AXE\_\_.crypt.base64.decode</span>
#### 定义和用法
对字符串进行 base64 解码

```javascript
__AXE__.crypt.base64.decode(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要解码的字符串 |

#### 返回值
经过解码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.decode('Y29udGVudFRvQmFzZTY0');
```


---


## <span id = "axe_crypt_base64_encodeHex">\_\_AXE\_\_.crypt.base64.encodeHex</span>
#### 定义和用法
对字符串进行 base64 编码，返回16进制编码。

```javascript
__AXE__.crypt.base64.encodeHex(content);
```

| 参数     | 描述 |
| :---     | :--- |
| content  | 要编码的字符串 |

#### 返回值
经过编码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.encodeHex('contentToBase64');
```


---


## <span id = "axe_crypt_base64_decodeHex">\_\_AXE\_\_.crypt.base64.decodeHex</span>
#### 定义和用法
对16进制编码进行解码

```javascript
__AXE__.crypt.base64.decodeHex(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要解码的字符串 |

#### 返回值
经过解码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.decodeHex('63 6f 6e 74 65 6e 74 54 6f 42 61 73 65 36 34');
```

---


## <span id = "axe_crypt_base64_encodeUrlBase64">\_\_AXE\_\_.crypt.base64.encodeUrlBase64</span>
#### 定义和用法
对网址字符串进行 base64 编码

```javascript
__AXE__.crypt.base64.encodeUrlBase64(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要编码的字符串 |

#### 返回值
经过编码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.encodeUrl('http://axeBrowser.com');
```


---


## <span id = "axe_crypt_base64_decodeUrl">\_\_AXE\_\_.crypt.base64.decodeUrl</span>
#### 定义和用法
对进行过编码的网址进行解码

```javascript
__AXE__.crypt.base64.decodeUrl(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要解码的字符串 |

#### 返回值
经过解码后的字符串

#### 实例
```javascript
__AXE__.crypt.base64.decodeUrl('aHR0cDovL2F4ZUJyb3dzZXIuY29t');
```


---


## <span id = "axe_crypt_md5">\_\_AXE\_\_.crypt.md5</span>
#### 定义和用法
计算 MD5 值 

```javascript
__AXE__.crypt.md5(content, upperCase, if16bit);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串，默认为空字符串 ''。 |
| upperCase  | 返回结果是否为大写，默认为 false，即返回小写的摘要。 |
| if16bit  | 是否返回16位结果，默认为 false，即返回32位的结果。 |

#### 返回值
字符串，指定字符串的 MD5 值。

#### 实例
```javascript
__AXE__.crypt.md5('contentToMD5');
```

---


## <span id = "axe_crypt_sha1">\_\_AXE\_\_.crypt.sha1</span>
#### 定义和用法
计算 sha1 值 

```javascript
__AXE__.crypt.sha1(content, upperCase);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串 |
| upperCase  | 返回结果是否为大写，默认为 true，即大写。 |

#### 返回值
字符串，指定字符串的 sha1 值。

#### 实例
```javascript
__AXE__.crypt.sha1('contentToSha1');
```

---


## <span id = "axe_crypt_sha256">\_\_AXE\_\_.crypt.sha256</span>
#### 定义和用法
计算 sha256 值 

```javascript
__AXE__.crypt.sha1(content, upperCase);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串 |
| upperCase  | 返回结果是否为大写，默认为 true，即大写。 |

#### 返回值
字符串，指定字符串的 sha256 值。

#### 实例
```javascript
__AXE__.crypt.sha256('contentToSha256');
```

---


## <span id = "axe_crypt_sha384">\_\_AXE\_\_.crypt.sha384</span>
#### 定义和用法
计算 sha384 值 

```javascript
__AXE__.crypt.sha384(content, upperCase);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串 |
| upperCase  | 返回结果是否为大写，默认为 true，即大写。 |

#### 返回值
字符串，指定字符串的 sha384 值。

#### 实例
```javascript
__AXE__.crypt.sha384('contentToSha384');
```

---


## <span id = "axe_crypt_sha512">\_\_AXE\_\_.crypt.sha512</span>
#### 定义和用法
计算 sha512 值 

```javascript
__AXE__.crypt.sha512(content, upperCase);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串 |
| upperCase  | 返回结果是否为大写，默认为 true，即大写。 |

#### 返回值
字符串，指定字符串的 sha512 值。

#### 实例
```javascript
__AXE__.crypt.sha512('contentToSha512');
```

---


## <span id = "axe_crypt_zlib_gzCompress">\_\_AXE\_\_.crypt.zlib.gzCompress</span>
#### 定义和用法
使用 gzip 算法压缩字符串

```javascript
__AXE__.crypt.zlib.gzCompress(content, level);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要压缩的字符串 |
| level  | 压缩级别（从1到9）。1最快，9压缩比最大，默认为 9。 |

#### 返回值
经过压缩后的字符串

#### 实例
```javascript
__AXE__.crypt.zlib.gzCompress('contentGzip');
__AXE__.crypt.zlib.gzCompress('contentGzip', 1);
```

---


## <span id = "axe_crypt_zlib_gzUncompress">\_\_AXE\_\_.crypt.zlib.gzUncompress</span>
#### 定义和用法
使用 gzip 算法解压字符串

```javascript
__AXE__.crypt.zlib.gzUncompress(content);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要解压的内容 |

#### 返回值
经过解压后的内容

#### 实例
```javascript
__AXE__.crypt.zlib.gzUncompress('contentGzip');
```

---



