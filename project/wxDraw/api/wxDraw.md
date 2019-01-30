## wxDraw对象
> 用于创建wxDraw画布

参数说明：

| 参数  | 类型   | 必填   | 说明   |
| :--- | :----: | ----: |:---:  |
| context		| Object |  是   |canvas标签context|
| x		| Number |  是   |canvas标签的绝对位置left|
| y    | Number |  是   |canvas标签的绝对位置top|
| w    | Number |  是   |canvas标签的宽|
| h    | Number |  是   |canvas标签的长|

!>  小程序所有标签都 不能进行DOM操作，所以**不能**用js直接获取canvas的位置以及大小，所以必须在初始化时候设置好准确的位置以及大小。


```js
    this.wxCanvas = new wxDraw(context,0,0,400,500);
```


## 方法


### add
添加图形对象

| 参数  | 类型   | 必填   | 说明   |
| :--- | :----: | ----: |:---:  |
|shape		| Object |  是   |图形对象|

### clear
清除画布

!> 在页面不加载的时候 请一定要使用这方法 我也不知道为啥页面不加载了，但是小程序里面的变量都还在，所以一定要用这个来清除变量。