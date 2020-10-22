# <span id = "axe_string">\_\_AXE\_\_.string</span>
字符串处理相关功能


---


## <span id = "axe_string_format">\_\_AXE\_\_.string.format</span>
#### 定义和用法
格式化字符串，提供类似其他语言中 %s %d 之类的格式化功能。
就个人而言，苦 js 无 string.format 久矣……

参见 [aardio 格式化字符串](https://www.kancloud.cn/ymk18/aau/content/libraries/kernel/string/format.md)

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


