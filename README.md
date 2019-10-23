# 谷歌插件获取Cookie与UserAgent

## 打包插件
```bash
npm install
node package.js
```

## 谷歌导入插件
在扩展程序中, 开启`开发者模式`, 点击`加载已解压的扩展程序`, 导入`extension`文件夹
![](./imgs/install.jpg)

## 国产浏览器
直接将`crx/GetCookiesAndUserAgent.crx`拖入浏览器即可安装
搜狗浏览器为例
![](./imgs/install2.jpg)

## 功能
### 1.右键复制当前页Cookies

>演示图片
![](./imgs/1.gif)


### 2.右键复制当前页UserAgent

>演示图片
![](./imgs/2.gif)


### 3.右键将Cookies和UserAgent发送到主页面
主页面需要先发送 message 给插件, 缓存页面 tabId
```javascript
window.parent.postMessage({type: 'tab', level: 'main'}, '*');
```
然后在要获取Cookie与UserAgent的页面右键选择"发送Cookies和UA到主页面"

>演示图片
![](./imgs/3.gif)