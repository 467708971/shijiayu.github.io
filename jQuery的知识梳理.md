# jQuery的知识梳理
## jQuery如何获取元素
jQuery获取元素可以分为两点来看  
1. 获  
获取,首先要获得,因此,使用jQuery的第一步,就是将一个选择表达式放入构造函数jQuery()中,包括但不限于： 
(以 \$ 代替 jQuery,window.$ = window.jQuery)
* $(document) //整个文档
* $('#xxx') //ID为xxx的元素
* $('.xxx') //Class为xxx的元素
* $('[name=xxx]') //name属性为xxx的元素
1. 取  
获得之后,就是取舍,于是jQuery还有个功能强大的选择器,用于对获得的结果进行筛选  
* $().has('x') //选择包含x元素的div元素  
* $().not('.x') //选择class不为x的div元素
* $().filter('.x') //选择class为x的div元素
* $().first() //选择第1个div元素
* $().eq(x) //选择第x+1个div元素
## jQuery的链式操作是怎样的
jQuery在选中元素后,就可以进行一系列操作,并且这些操作可以连在一起,形成一条链子
```
$('div').find('h2').first().html('Hi');
```
拆解下来,就成了
```
$('div')        //先找到div元素
    .find('h2') //再找到h2元素
    .first()    //再找第一个h2
    .html('Hi') //把里面的内容改成Hi
```
其原理就是每一步的jQuery操作返回的都是一个jQuery对象,也就可以将不同操作连在一起进行链式操作  
同样, jQuery还提供了.end()方法,它可以使结果集后退一步
```
$('div')
    .find('h2')
    .first()
    .html('Hi')
    .end()  //此处end就会退回到.find('h2')那一步
```
## jQuery如何创建元素
创建元素的方法很简单,就是将新的元素写入jQuery的构造函数当中去
## jQuery如何移动元素
移动元素的方法有4类共8种  
分为  
```
.insertAfter()和.after()    //在现存元素外部从后面插入元素
.insertBefore()和.before()  //在现存元素外部从前面插入元素
.appendTo()和.append()      //在现存元素内部从后面插入元素
.prepandTo()和.prepand()    //在现存元素内部从前面插入元素
```
例:  
```
$('移动的函数').insertAfter($('目标函数'))
```
## jQuery如何修改元素的属性
jQuery通过
```
$div.attr('xxx',?)
```
进行属性的读写  
例:
```
$div.attr('class','class01')    //改变div的所有元素的class的值为class01
```