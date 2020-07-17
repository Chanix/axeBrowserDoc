# <span id = "axe_env">\_\_AXE\_\_.env</span>
环境变量相关


## <span id = "axe_env_get">\_\_AXE\_\_.env.get</span>
#### 定义和用法
获取环境变量值。

```javascript
__AXE__.env.get(envname);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |

#### 返回值
指定环境变量值，若未指定返回空。

#### 实例
```javascript
__AXE__.log('环境变量 PATH：', __AXE__.env.get('path'));
```

## <span id = "axe_env_set">\_\_AXE\_\_.env.set</span>
#### 定义和用法
设置环境变量值。

```javascript
__AXE__.env.set(envname, value);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |
| value  | 环境变量的值  |

#### 返回值
设置环境变量。

#### 实例
```javascript
__AXE__.env.set('TTT', 'ttt');
```

## <span id = "axe_env_add">\_\_AXE\_\_.env.add</span>
#### 定义和用法
设置环境变量值（仅当该环境变量不存在时）。

```javascript
__AXE__.env.add(envname, value);
```

| 参数      | 描述 |
| :---      | :--- |
| envname  | 环境变量的名称  |
| value  | 环境变量的值  |

#### 返回值
设置环境变量。

#### 实例
```javascript
__AXE__.env.add('TTT', 'ttt');
```

