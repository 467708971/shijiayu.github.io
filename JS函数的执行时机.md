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