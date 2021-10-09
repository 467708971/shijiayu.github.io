# CSS知识总结
## 浏览器渲染原理

浏览器渲染过程：

* 根据HTML构建HTML树(DOM)
* 根据CSS构建CSS树(CSSOM)
* 将两棵树合并成一个渲染树(render tree)
* Layout布局(文档流、盒模型、计算大小和位置)
* Paint绘制(把边框颜色、文字颜色、阴影等画出)
* Compose合成(根据层叠关系展示画面)

样式的三种更新方式：

1. JS/CSS > 样式 > 布局 > 绘制 > 合成

   案例：div.remove(),div.remove()会触发当前元素的消失,其他元素relayout
2. JS/CSS > 样式 > 绘制 > 合成

   案例：改变背景颜色,改变背景颜色直接repaint+composite
3. JS/CSS > 样式 > 合成

   案例：改变transform,改变transform只需要composite

## CSS动画的两种做法

transition：  
transition是一个过渡的属性，它需要用户去主动触发，其作用是补充除第一帧和最后一帧外的中间帧  
用法：  
transition: 属性名 | 时长 | 过渡方式 | 延时

animation：  
animation是一个动画属性，它只要网页加载完成时便自动执行，从而进行动画的播放  
用法：  
animation: 时长 | 过渡方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 | 动画名
