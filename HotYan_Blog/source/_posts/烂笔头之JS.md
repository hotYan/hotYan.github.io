---
title: 烂笔头之JS
date: 2018-05-31 19:13:13
tags:
- notes
- JS
- 面试
categories: 好记性不如烂笔头
---
## 关于JS <span style="font-size:.5em">[持续更新]</span>
> JS笔记 


<!--more-->
## JS定义
- JavaScript是一种弱类型、动态的、解释型的脚本语言

- JavaScript是客户端和服务器端脚本语言
- JavaScript也是面向对象编程语言
## 组成
- ECMAScript

- DOM:文档对象模型
- BOM:浏览器对象模型

## JS数据类型
- 基本类型:string、number、boolean、nudefined、null

- 复杂数据类型（引用数据类型）:Object、Function、Array、Data、RegExp...

- typeof:判断基本数据类型

- Object.prototype.toString.call():判断对象属于哪种内置对象类型

- instanceof:判断构造函数原型

 

## 变量提升
- JavaScript是一种弱类型、动态的、解释型的脚本语言

  - 强|弱类型:类型检查 严格|不严格，偏向于 不容忍|容忍 隐式转换

  - 动态类型：运行的时候执行类型检查
  - 静态类型：编译的时候就知道每个变量的类型

  - 解释型：不需要编译，在运行的时候才翻译成机器语言，执行一次翻译一次，故效率低，跨平台性好；
  - 编译型：需编译为机器语言的文件，运行时直接使用编译的结果；
  - 标记语言：被动，不具备与访问者互动的能力；
  - 脚本语言：
  - 编程语言：

- js代码解析原则
  - 第一个步骤是解释，先通篇扫描所有的Js代码，然后把所有变量声明提升到该作用域顶端

  - 第二个步骤是执行

- 函数提升在变量提升之上

## <span id="inline-blue"> 闭包 </span>
- 可以访问其他函数内部作用域的函数 

- 在有函数嵌套的情况下，子函数用到了父函数的参数或者局部变量

- 作用：具有封闭性，保护变量；避免污染全局变量

- 缺点：内存泄漏

## typeof返回哪些数据类型
- Object
- number
- function
- boolean
- undefind

## 3种强制类型转换
- parseInt
- parseFloat
- number

## 2种隐式转换
- == 
- ===
## split(）
- 切割成数组的形式

## join()
- 将数组转换成字符串
## IE和DOM事件流的区别
- 执行顺序不一样、
- 参数不一样
- 事件加不加on
- this指向问题
## call、apply、bind的区别
### call、apply
- 改变函数体内部 this 的指向。
- 作用完全一样，只是接受参数的方式不太一样
- call 需要把参数按顺序传递进去，而 apply 则是把参数放在数组里。　　
### call、apply、bind
- apply 、 call 、bind 三者都是用来改变函数的this对象的指向的；
- apply 、 call 、bind 三者第一个参数都是this要指向的对象，也就是想指定的上下文；
- apply 、 call 、bind 三者都可以利用后续参数传参；
- bind 是返回对应函数，便于稍后调用；apply 、call 则是立即调用 。

[查看更多>](http://www.cnblogs.com/coco1s/p/4833199.html)




## 原型链

- 对象的属性和方法，有可能是定义在自身，也有可能是定义在它的原型对象上。由于原型本身也是对象，又有自己的原型，所以形成了一条原型链（prototype chain）。

- 如果一层层地上溯，所有对象的原型最终都可以上溯到Object.prototype，即Object构造函数的prototype属性指向的那个对象。而Object.prototype对象的原型就是没有任何属性和方法的null对象，而null对象没有自己的原型。

- “原型链”的作用是，读取对象的某个属性时，JavaScript 引擎先寻找对象本身的属性，如果找不到，就到它的原型去找，如果还是找不到，就到原型的原型去找。如果直到最顶层的Object.prototype还是找不到，则返回undefined。

- 如果对象自身和它的原型，都定义了一个同名属性，那么优先读取对象自身的属性，这叫做“覆盖”（overriding）。

- 需要注意的是，一级级向上，在原型链寻找某个属性，对性能是有影响的。所寻找的属性在越上层的原型对象，对性能的影响越大。如果寻找某个不存在的属性，将会遍历整个原型链。  

[查看更多>](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

## 面向对象

- [重新介绍JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/A_re-introduction_to_JavaScript)