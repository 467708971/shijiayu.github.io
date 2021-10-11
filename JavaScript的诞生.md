# JavaScript的诞生
## 啥是JavaScript语言
&emsp;&emsp;JavaScript，当今世界的一门主流语言，被大多数浏览器支持。  
&emsp;&emsp;JavaScript，孕育期只有10天的一门语言，被大多数人嫌弃。  
## 第一版的JavaScript是个四不像
```
JavaScript == C语言的语法 + Java的数据类型和内存管理 + Scheme的"函数一等公民权" + Self语言基于原型(prototype)的继承机制;
```
所以JavaScript是两种风格的混合产物————(简化的)函数式编程 + (简化的)面向对象编程。  
也正因为这种四不像的杂糅融合，导致JavaScript产生的问题很多。
## JavaScript的设计缺陷、
1. JS不适合开发大型程序  
   JS没有自己的命名空间，也就很难进行模块化操作；更让使用者难受的是，JS允许同名函数的重复定义，后定义的重名函数会覆盖前定义的重名函数，就很难进行模块化编程。
2. JS的标准库很小  
   较小的标准库意味着只能进行基本的操作，没有庞大标准库的支撑很难进行复杂程序的开发。  
3. JS开发周期短  
   JS从构思到设计完成只用了10天，还是在设计者不情愿的情况下出世，所以考虑的比较简单

既然JS缺陷这么大，为什么它还是世界主流语言呢？  
## JS的优点
&emsp;&emsp;JS有着强大的编程能力，让它专精与中小型程序的开发，而且不是不能，只是不合适，JS有进行大型程序开发的能力，但是对于开发大型程序，我们有着更好的选择，没必要在JS这条路上走到底。  
&emsp;&emsp;较小的标准库也不是无法克服的问题，我自己的库小，我可以用别人的库，第三方的函数库可以帮助JS克服大多数的问题  
&emsp;&emsp;在不安装任何插件的情况下，JS还是所有浏览器默认支持的前端交互语言  
&emsp;&emsp;JS如今也在不断完善自己，弥补这当初设计时的漏洞

## 相关文章
1. <a href='http://www.ruanyifeng.com/blog/2011/06/birth_of_javascript.html'>JavaScript诞生记</a>——2011.06.24
2. <a href='http://www.ruanyifeng.com/blog/2011/06/10_design_defects_in_javascript.html'>JavaScript的10个设计缺陷</a>——2011.06.30
3. <a href='https://zh.wikipedia.org/wiki/JavaScript'>Java Wiki</a>