<div styl="width:100%;text-align:center;"><image src="./image/wxDraw.gif"></div>
# wxDraw

> 轻量的小程序canvas动画库

## 是什么
  canvas 是HTML5的一个重要元素，它能够高效的绘制图形，但是过于底层，且粗糙的Api，导致开发者很难使用它来做较为复杂的图形，
  而且它的即时绘制无记忆特性，使得它内部的图形并不支持动画更不支持一切交互事件。

  这样的问题出现在所有支持canvas的客户端上同样出现在 **微信小程序**中的canvas中，
  由于小程序由jsCore支持，并没有window对象，并且canvas的Api与标准的canvas的Api有所出入，所以市面上绝大部分canvas库与它无缘。

  而**wxDraw**也就应运而生，专门用于处理小程序上canvas的**图形创建**，**图形动画**，以及**交互问题**的。

  ## 特性
   - **简单** 不需要你会canvas,会用jQuery就会使用wxDraw。
   - **灵活** 所有图形，随时随地都可以进行属性修改、图形添加以及图形销毁。
   - **事件支持** 小程序支持的事件只要是合理的都支持。
   - **缓动动画支持** wxDraw支持链式调用动画『就像jQuery的animate一样』，并且支持几乎所有的缓动函数。

