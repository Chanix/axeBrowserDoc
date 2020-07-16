# <span id = "axe_hotkey">\_\_AXE\_\_.hotkey</span>
通过本模块在 Javascript 中自定义热键和按下热键时要执行的脚本代码，脚本代码在匿名函数中运行。
由于实际环境不同，因此设置热键不一定成功。

热键名称请这样来定义【控制键+按键名称】，例如 “CTRL+C”，“ALT+F1” 等。如果不需要控制键则留空，例如 “+F1” 代表 F1 功能键单独按下。热键名称不区分大小写，建议根据自己的习惯来统一。


---


## <span id = "axe_hotkey_set">\_\_AXE\_\_.hotkey.set</span>
#### 定义和用法
定义某热键执行的脚本代码。

```javascript
__AXE__.hotkey.set(key_name, script_code);
```

| 参数      | 描述 |
| :---      | :--- |
| key_name  | 热键的名称 |
| script_code | 执行的代码 |

#### 返回值
true    热键设置成功
false   热键设置失败

#### 实例
```javascript
__AXE__.hotkey.set('ctrl+s', `alert('CTRL+S 被按下');`);
```

---


## <span id = "axe_hotkey_unset">\_\_AXE\_\_.hotkey.unset</span>
#### 定义和用法
取消指定热键定义。

```javascript
__AXE__.hotkey.unset(key_name);
```

| 参数      | 描述 |
| :---      | :--- |
| key_name  | 热键的名称 |

#### 返回值
无

#### 实例
```javascript
__AXE__.hotkey.unset('ctrl+s');
```


---


## <span id = "axe_hotkey_isset">\_\_AXE\_\_.hotkey.isset</span>
#### 定义和用法
检查指定的热键是否已经定义

```javascript
__AXE__.hotkey.isset(key_name);
```

| 参数      | 描述 |
| :---      | :--- |
| key_name  | 热键的名称 |

#### 返回值
true    已设置
false   未设置

#### 实例
```javascript
__AXE__.hotkey.isset('ctrl+s');
```

---


## <span id = "axe_hotkey_clear">\_\_AXE\_\_.hotkey.clear</span>
#### 定义和用法
取消所有热键。

```javascript
__AXE__.hotkey.clear();
```

#### 返回值
无

#### 实例
```javascript
__AXE__.hotkey.clear();
```

---

