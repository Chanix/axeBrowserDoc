# 获取bing每日壁纸并保存

将以下内容保存为 get_bing_bg.js，存放在 axeBrowser.exe 所在文件夹：
```javascript
// 设置变量 AXE，方便调用。
// 显示日志，运行开始。
__AXE__.log('>>> START');

// 设置窗口标题
__AXE__.setTitle('获取并保存Bing背景壁纸');

// 获得背景图的网址
var imgurl = document.getElementById('bgLink').href;

// 拼凑出保存的文件名：YYYY-MM-DD.jpg
var dateToday = new Date();
var filename = dateToday.getFullYear() + '-' + (dateToday.getMonth() + 1) + '-' + dateToday.getDate() + '.jpg';

// 同步调用 curl.exe（Win10 中自带） 来下载并保存图片。
__AXE__.execWait('curl', '"' + imgurl + '" -o "' + filename + '"');

// 显示日志，运行完毕。
__AXE__.log('<<< END');

// 退出 axeBrowser
__AXE__.exit();
```

打开命令行窗口，切换到 axeBrowser.exe 所在文件夹，执行命令：
```
.\axeBrowser -home "https://cn.bing.com" -script "get_bing_bg.js" -runas console
```
