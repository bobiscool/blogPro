!> 注意:  以下教程都是假定你有一定的小程序开发经验基础上的

### 创建目录
首先你得有一个小程序项目（什么！😱你连小程序项目怎么搭都不知道 [😒点这里](https://mp.weixin.qq.com/debug/wxadoc/dev/api/)

目录就像这样（其实就是小程序的starter项目）

![](/image/开发目录.png)

### 引入文件
 将**wxdraw.min.js**或者**wxdraw.js**放到utils目录下  [下载压缩版](https://github.com/bobiscool/wxDraw/releases)

!> 注意 **小程序** 对于有过多的中文注释以及过多的log的代码解析有点问题
   ,会导致小程序即使在pc端模拟运行没有问题，但在手机上运行时加载失败。所以建议发布时使用min版本。

![](/image/addJs.png)



### 添加canvas标签

打开你要添加canvas的页面，添加上的canvas

![](/image/addCanvas.png)

wxml文件内部这样写

```html

<!--index.wxml-->
<view class="container">
 <canvas
  style="width: 400px; height: 500px;border:1px;position:absolute;top:0;left:0; solid black;"
  canvas-id="first"
  disable-scroll=true
  bindtouchstart="bindtouchstart"
  bindtouchmove="bindtouchmove"
  bindtouchend="bindtouchend"
  bindtap="bindtap"
  bindlongpress="bindlongpress"
  ></canvas>

</view>
<!--  为了省时间 我就写行间样式了-->
<!--  小程序所有标签都 不能进行DOM操作，绑定事件需要行间绑定-->
```

### 添加必要的js

![](/image/addCanvasjs.png)

在js文件开头写上,引入wxDraw对象以及Shape对象

```js
var  wxDraw= require("../../../../util/wxdraw.js").wxDraw;
var Shape = require("../../../../util/wxdraw.js").Shape;
```

然后在Page函数里面添加与上述 对应的几个事件

!> 如果 你需要canvas里面的图形可以响应事件，请你务必加上以下几个函数

```js

Page({
  data: {
    userInfo: {},
    hasUserInfo: false,
    wxCanvas:null //    需要创建一个对象来接受wxDraw对象

  },
  bindtouchstart:function(e){
    // 检测手指点击开始事件
    this.wxCanvas.touchstartDetect(e);

  },
  bindtouchmove:function(e){
    // 检测手指点击 之后的移动事件
    this.wxCanvas.touchmoveDetect(e);
  },
  bindtouchend:function(){
     //检测手指点击 移出事件
    this.wxCanvas.touchendDetect();
  },
  bindtap:function(e){
    // 检测tap事件
    this.wxCanvas.tapDetect(e);
  },
  bindlongpress:function(e){
       // 检测longpress事件
    this.wxCanvas.longpressDetect(e);
  },
  onLoad:function(){
     ...
  }
```