# <span id = "axe_crypt">\_\_AXE\_\_.crypt</span>
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


## <span id = "axe_crypt_base64_encodeUrl">\_\_AXE\_\_.crypt.base64.encodeUrl</span>
#### 定义和用法
对网址字符串进行 base64 编码

```javascript
__AXE__.crypt.base64.encodeUrl(content);
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

## <span id = "axe_crypt_des_encrypt">\_\_AXE\_\_.crypt.des.encrypt</span>
#### 定义和用法
用 des 算法进行加密。

```javascript
__AXE__.crypt.des.encrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行加密的字符串 |
| key | 密钥 |

#### 返回值
经过加密的密文。

#### 实例
```javascript
__AXE__.crypt.des.encrypt('contentToDES', 'secret');
```

---

## <span id = "axe_crypt_des_decrypt">\_\_AXE\_\_.crypt.des.decrypt</span>
#### 定义和用法
用 des 算法进行解密

```javascript
__AXE__.crypt.des.decrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行解密的字符串 |
| key | 密钥 |

#### 返回值
经过解密的明文。

#### 实例
```javascript
__AXE__.crypt.des.decrypt('contentToDES', 'secret');
```


---


## <span id = "axe_crypt_md2">\_\_AXE\_\_.crypt.md2</span>
#### 定义和用法
计算 MD2 值

```javascript
__AXE__.crypt.md2(content, upperCase, if16bit);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串，默认为空字符串 ''。 |
| upperCase  | 返回结果是否为大写，默认为 false，即返回小写的摘要。 |
| if16bit  | 是否返回16位结果，默认为 false，即返回32位的结果。 |

#### 返回值
字符串，指定字符串的 MD2 值。

#### 实例
```javascript
__AXE__.crypt.md2('contentToMD2');
```

---


## <span id = "axe_crypt_md4">\_\_AXE\_\_.crypt.md4</span>
#### 定义和用法
计算 MD4 值

```javascript
__AXE__.crypt.md4(content, upperCase, if16bit);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要计算摘要的字符串，默认为空字符串 ''。 |
| upperCase  | 返回结果是否为大写，默认为 false，即返回小写的摘要。 |
| if16bit  | 是否返回16位结果，默认为 false，即返回32位的结果。 |

#### 返回值
字符串，指定字符串的 MD4 值。

#### 实例
```javascript
__AXE__.crypt.md4('contentToMD4');
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


## <span id = "axe_crypt_rc4_encrypt">\_\_AXE\_\_.crypt.rc4.encrypt</span>
#### 定义和用法
用 rc4 算法进行加密。

```javascript
__AXE__.crypt.rc4.encrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行加密的字符串 |
| key | 密钥 |

#### 返回值
经过加密的密文。

#### 实例
```javascript
__AXE__.crypt.rc4.encrypt('contentToRC4', 'secret');
```

---

## <span id = "axe_crypt_rc4_decrypt">\_\_AXE\_\_.crypt.rc4.decrypt</span>
#### 定义和用法
用 rc4 算法进行解密

```javascript
__AXE__.crypt.rc4.decrypt(content, key);
```

| 参数      | 描述 |
| :---      | :--- |
| content  | 要进行解密的字符串 |
| key | 密钥 |

#### 返回值
经过解密的明文。

#### 实例
```javascript
__AXE__.crypt.rc4.decrypt('contentToRC4', 'secret');
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
| level  | 压缩级别（从1到9）。1最快，9压缩比最大，默认为 8。 |

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

quotedPrintable.encode
quotedPrintable.decode