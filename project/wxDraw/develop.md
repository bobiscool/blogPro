# 开发指南

## 开发环境
- 设备 Macbook pro
- 系统 OSX
- 包管理器 npm 3.10.10
- 打包工具 rollup version 0.50.0
- 微信调试 微信开发者工具 v1.01.17
- 基础库 1.6
- 实体测试机 一加3
- 其他辅助 babel

## src目录简述
<pre>
├── index.js // 引入文件 wxDraw老巢
├── animation  //动画控制中心
│   ├── animation.js
│   ├── animationFrag.js
│   ├── animationFragWraper.js
│   ├── animationFrame.js
│   ├── animationFunc.js
│   ├── animationTimer.js
│   └── specialAtrribute.js
├── handler //没用到 事件处理都放到了shape里面
│   └── event.js
├── shape   //图形中心  用户想自定义图形在此处加
│   ├── circle.js
│   ├── cshape.js
│   ├── ellipse.js
│   ├── line.js
│   ├── mixins
│   │   ├── commonAttr.js
│   │   ├── commonMethods.js
│   │   ├── getCurvePoints.js
│   │   └── points.js
│   ├── path.js
│   ├── polygon.js
│   ├── rect.js
│   ├── shape.js
│   ├── shapeBase.js
│   └── text.js
├── store  //仓库
│   └── store.js
└── util //工具库
    ├── eventBus.js
    ├── matrix.js //矩阵计算
    ├── patch.js
    └── utils.js
</pre>

