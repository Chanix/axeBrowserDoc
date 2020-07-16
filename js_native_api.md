# JavaScript 扩展（Native API）
axeBrowser 提供了扩展对象供 JavaScript 调用，通过该对象，提供了大量 JavaScript 原来无法实现的功能，例如本地资源的访问、跨域调用等等。

JavaScript 通过预设变量 “**<font color=red>\_\_AXE\_\_</font>**” 获得该扩展对象。这个变量亦可作为判断是否 axeBrowser 环境的依据，VIP 版可以修改该预设变量的变量名。


例如：
```javascript
if ('undefined' == typeof(__AXE__) || null == __AXE__) {
    alert('请检查：当前运行环境似乎不是 axeBrowser ？');
} else {
    alert(__AXE__);
}
```


*axeBrowser 在不断的更新和完善中，因此扩展也会有修改和增减。在进行修改和增减时，会尽量的保持兼容性，使原有的脚本无需进行修改。请随时关注最新的文档说明。*
