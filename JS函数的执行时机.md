# JS函数的执行时机
## 代码解释
```
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
这段代码在输出时会打印出6、6、6、6、6、6而不是0、1、2、3、4、5；  
因为
```
let i = 0
```
只有一个 i，那么最后 setTimeout 打出的将会是 i 的最新值，而这个最新值在for循环执行到 i = 6 时才会停止，所以 i 的最新值是 6 而不是 5  
## 打印0、1、2、3、4、5的方法
将
```
let i = 0
```
移到for循环内，使得每次for循环创建一个新的i
```
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
## 额外内容
除了使用 for let 配合，还有其他方法可以打印出 0、1、2、3、4、5  
```
第一次尝试：
把console.log移动到setTimeout的外面
let i = 0
for(i = 0; i<6; i++){
    console.log(i)
  setTimeout(()=>{ },0)
}

无效
```
```
第二次尝试：
去掉箭头函数
let i = 0
for(i = 0; i<6; i++){
  setTimeout( console.log(i) , 0 )
}

无效
```
```
第三次尝试
闭包
let i = 0
for(i = 0; i<6; i++){
(function (i){
  setTimeout(()=>{
    console.log(i)
  },0)
})(i)
}

有效
```
## setTimeout()为何会最后执行
setTimeout()运行机制：将setTimeout中的代码移出本次执行，等到下一轮事件循环时，再检查是否到了setTimeout的指定的时间，到时间了就执行，没到时间就等待下一轮事件循环。也就是说，setTimeout必须等到本次循环所有代码执行完毕，才能执行  
但是，setTimeout也不一定按照时间来执行的，setTimeout中的回调是异步执行，它会等待循环队列中的同步代码执行完毕后，再取出setTimeout进行执行
## setTimeout()回调时如何找到 i 变量
由setTimeout()调用的代码运行在与所在函数完全分离的执行环境上。这会导致，这些代码中包含的 this 关键字在非严格模式会指向 window (或全局)对象；
但是箭头函数不会创建自己的this,它只会从自己的作用域链的上一层继承this；所以最后获得了i的全局变量let i