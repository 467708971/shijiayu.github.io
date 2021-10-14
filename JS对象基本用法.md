# JS对象基本用法
## 声明对象的两种语法
```
let obj = { 'name': 'frank', 'age': 18 }
let obj = new Object({'name': 'frank'})

console.log({ 'name': 'frank, 'age': 18 })
//用来声明一个匿名的对象
```
## 如何删除对象的属性
```
delete obj.xxx 或delete obj['xxx']
//即可删除obj的xxx属性
```
## 如何查看对象的属性
```
Object.keys(obj)
//查看所有的key

Object.values(obj)
//查看所有的值

Object.entries(obj)
//查看所有的key和值

console.dir(obj)
//通过目录的形式查看所有属性

obj['key'] / obj.key
//查看单个属性
```
## 如何修改和增加对象的属性
改自身属性：
```
obj['xxx'] = 'xxxx'
```
批量修改属性：
```
Object.assign(obj,{ p1:1 , p2:2 , p3:3 , ......})
```
添加对象的属性：(与修改一致，有则改之，无则添加)
```
let person = Object.create(common) 
//以common为原型创建person
```
添加方法1：在下面继续添加
```
let person = Object.create(common)
person.name = 'frank'
person.age = 18
......
```
添加方法2：直接在Object.create中添加
```
let person = Object.create(common ,{
    name : {value : 'frank' , age : 18 , ......}
})
```
## 'name' in obj和obj.hasOwnProperty('name')的区别
'name' in obj没法区分属性是自己的还是原型共有的，所以要使用obj.hasOwnProperty('name')，当它自身拥有这个属性时，obj.hasOwnProperty('name')会返回false
