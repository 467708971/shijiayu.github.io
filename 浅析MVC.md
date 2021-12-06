# 浅析MVC
## MVC的三个对象
1. Model(模型)  
   model负责数据管理
2. View(视图)  
   view负责界面
3. Controller(控制器)  
   controller负责其他
```JavaScript
model = {
   let a = 1
   let b = 2
   let c = 3
}
view = {
   http: `
   <div>....</div>
   <div>....</div>
   `
}
controller = {
   其他
}
```
## EventBus的API及作用
_self.getEventBus   
&emsp;&emsp;方法：getEventBus:function(){}   
&emsp;&emsp;描述：直接返回前端EventBus对象，不推荐直接使用。  
<br>
_self.subscribeEvent  
&emsp;&emsp;方法：subscribeEvent:function(event,fn,pointcut){}  
&emsp;&emsp;描述：注册事件，并指定实现方法和插入点  
&emsp;&emsp;参数：event：字符串形式事件名，命名规则为Event或ActionEvent结尾  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;fn：实现方法  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;插入点类型：after、overwrite、before  
<br>
_self.unSubscribeEvent  
&emsp;&emsp;方法：unSubscribeEvent:function(event){}  
&emsp;&emsp;描述：取消注册事件  
&emsp;&emsp;参数：event：字符串形式事件名，命名规则为Event或ActionEvent结尾  
<br>
_self.fireEvent  
&emsp;&emsp;方法：fireEvent:function(event){}  
&emsp;&emsp;描述：触发某个具体事件，执行这个事件对于的实现方法队列  
&emsp;&emsp;参数：event：字符串形式事件名，命名规则为Event或ActionEvent结尾  
&emsp;&emsp;其他参数：可以增加一些后续参数  
## 表驱动编程
表驱动编程是一种<font color=#ADD8E6>编程模式</font>，相当于不用逻辑语句来执行类似if...else...的操作  
栗子：  
```JavaScript
function fn(value){
   if(value === 1){
      return 9
   }else if(value === 2){
      return 8
   }else if(value === 3){
      return 7
   }else{
      return 0
   }
}

而表驱动编程是另一种表现手法

function fn(value){
   let values = {
      1:9,
      2:8,
      3:7
   }
   return values[value];
}
```
不难看出，表驱动编程在后续的添加方面有着巨大优势，使用表驱动编程的目的就是要让**数据与逻辑分离**，进而减少逻辑的使用
## 我对模块化的理解
模块化就像是你在玩乐高拼图，对于那些大件的乐高，最轻松的方法是先将整个拼图区块化，然后一个一个区块进行拼装，最后进行一个统一的组装。  
当我看到M的时候，我会知道M的内容的作用是什么，当我看到V和C的时候，我也会知道V和C的内容是什么，当MVC组合起来之后，就成了完整的一块拼图了。  
模块化的优点有易读、简洁和易修改，但是完成模块化需要额外的时间，内容上的优化也需要一定的知识储备