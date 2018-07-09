---
title: 烂笔头之CSS
date: 2018-05-31 19:12:32
tags:
- notes
- CSS
- 面试
categories: 好记性不如烂笔头
---
## 关于 CSS  <span style="font-size:.5em">[持续更新]</span>  
> 记录了应该熟知的CSS相关知识点~  


<!--more-->

## CSS盒模型
    content、padding、border、margin
- 标准盒模型: 
    
      content.width = content 
- IE盒模型:  

      content.width = content + padding + border 

- 设置盒模型：  
    
      box-sizing:content-box | border-box


## 边距重叠
- 兄弟元素，外边距取绝对值大的

## BFC - 块级格式化上下文
1、原理：
- 页面上的一个独立容器，容器里面的子元素与外面的元素互不影响；
- BFC内部的盒子，会在垂直方向，一个接一个地放置。垂直方向上也会发生边距重叠。

- BFC的区域不会与float box重叠。
- 计算BFC的高度时，浮动元素也被计算在内。

2、如何产生：
    
    - overflow:auto | hidden  
    - position: absolute | fixed  
    - float: left | right  
    - display: inline-block | table-cell |table-caption | flex | inline-flex  
    - clear: both


3、作用：
- 自适应布局：两栏布局，左边固定，右边自适应

- 清除浮动
- 解决垂直边距重叠
- float 坍塌问题
- 文字浮动问题



## 选择器权重

  - 内联样式： 1000

  - ID： 100
  - 类、属性、伪类：10
  - 标签、伪元素： 1



## 引入CSS样式及优先级 
- 内联/行内 样式 > 内部/内嵌 样式 > 外部样式 > 导入样式  



## CSS单位
- 绝对单位： cm mm in pt pc
- 相对单位：
  - px ：不考虑分辨率，当做绝对单位对待
  - % ：
  - em ：相对当前元素（首行缩进用text-indent：2em；） 
  - rem ：相对于根元素(常用于移动端)
- 视窗单位： 
  - vh :视窗高度的百分比
  - vw 
  - vmin ：vw vh中较小的一个
  - vmax ：vw vh中较大的一个

- % 相对于谁：
  - 以父元素容器 **宽** 为基准：padding、margin、width
  - 以父元素容器 **高** 为基准：height 、定位元素
  - 以自身：translate



## 水平居中
- 行级元素:   
          
      父级 {  
        text-align: center ;  
      }   
 
- 块级元素: 

        当前元素 {  
          margin: 0 auto ;  
        }

- 子元素浮动:  

        父级 {
          width:fit-content;  
          margin:0 auto;
        }  

- flex 2012:  

        子元素 {  
          display:flex;  
          justify-content:center; 
        }  

- 绝对定位 + transform:  

        子元素 {  
          position:absolute;  
          left:50%;  
          transform:translate（-50% ,0）;  
        }  

- 定宽 + 绝对定位 + 负值：  

        子元素 {  
          left:50%;  
          margin-left:-0.5*宽度;  
        }   

- 定宽 + 绝对定位 ：  

        子元素 {  
          left:0;  
          right:0;  
          margin:0 auto;  
        }



## 垂直居中
- 单行文本  

      当前元素 {   
        line-height:父级元素高度 ; 
      }

- 行内块级元素  

      父级元素:after 当前元素{  
        display: inline-block;  
        vertical-align: middle;  
      }  

- 元素高度不定  

      父元素: {  
        display:table;  
      }  
      当前元素 {  
        display: table-cell;
        vertical-align:middle;  
      }  
      
    元素内容不会被截断 

- 元素高度固定 

      父级{  
        position:relative;  
      }  
      当前元素{  
        height:固定;  
        position:absolute;  
        top:50%;  
        margin-top:-0.5*高度；  
      }|{  
        height:固定; 
        position:absolute;   
        top:0;  
        bottom:0;  
        margin: auto 0;  
      }

 - Flex 2012 
 
        父级元素{  
          display:flex;  
          algin-items:center;  
        } 

 - transform
      
        父级{  
          position:relative;  
        }   
        当前元素{  
          position:absolute;  
          top:50%;  
          transform:translate(-50% , -50%);  
        }
   

## 垂直水平居中
[待完善]
 

## 伪类与伪元素
- 伪类：效果可以通过添加实际类实现，只要不是互斥可以叠加使用，优先级与类相同

- 伪元素：效果可以通过添加实际元素来实现，在一个选择器中只能出现一次，且只能出现在末尾，优先级与标签相同  

- 本质区别：是否抽象创造了新元素
---------
[参考链接》](http://www.bslxx.com/m/view.php?aid=1217)
## html5为什么只需要写<!doctype html>
- html5不是基于sgml（标准通用标记语言），不需要对dtd文件进行引用，但是需要doctype来规范浏览器的行为，否则浏览器将开启怪异模式。
- 而html4.01基于sgml，需要引入dtd，才能告知浏览器文档使用的文档类型

## 页面导入样式时，使用link和@import有什么区别？
### 同
- 都是外部引用CSS的方式
### 异

---
| link | @import |
| :--: | :--   | 
XHTML标签,除加载CSS,还可以定义RSS等其他事务 | 属于CSS范畴，只能加载CSS
引用CSS时，在页面载入时同时加载 | 需要页面网页完全载入以后加载
XHTML标签，无兼容问题 | CSS2.1提出,低版本的浏览器不支持
支持使用Javascript控制DOM去改变样式 | 不支持Javascript控制DOM去改变样式

-----

## 常见的浏览器内核有哪些？

| 内核 | 浏览器 |
| :--: | :--   | 
Trident| **IE**、Maxthon、TT、The World等
Gecko | Netcape6及以上版本、**FireFox**、MozillaSuite/SeaMonkey
Presto  | **Opera7及以上版本**
Webkit | Safari、**Chrome**

----
## null和undefined的区别？

>NULL 

- null是一个表示”无”的对象，转为数值时为0;
- null表示”没有对象”，即该处不应该有值;
  - 作为函数的参数，表示该函数的参数不是对象。
  - 作为对象原型链的终点。

>undefined
- undefined是一个表示”无”的原始值，转为数值时为NaN。
- undefined表示”缺少值”，就是此处应该有一个值，但是还没有定义
    - 变量被声明了，但没有赋值时，就等于undefined。
    - 调用函数时，应该提供的参数没有提供，该参数等于undefined。
    - 对象没有赋值的属性，该属性的值为undefined。
    - 函数没有返回值时，默认返回undefined。
## 严格模式
- 进入”严格模式”的标志，老版本的浏览器会把它当作一行普通字符串，加以忽略
- 引用
  -  将”use strict”放在**脚本文件的第一行**，则整个脚本都将以”严格模式”运行。
  - 将”use strict”放在**函数体的第一行**，则整个函数以”严格模式”运行
  >因为第一种调用方法不利于文件合并，所以更好的做法是，借用第二种方法，将**整个脚本文件放在一个立即执行的匿名函数之中**
- 作用
  - 消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为;
  - 消除代码运行的一些不安全之处，保证代码运行的安全；
  - 提高编译器效率，增加运行速度；
  - 为未来新版本的Javascript做好铺垫。
## hasOwnProperty()
- 执行对象查找时，永远不会去查找原型
- 用于指示一个对象自身(不包括原型链)是否具有指定名称的属性。如果有，返回true，否则返回false。
- 该方法属于Object对象，由于所有的对象都”继承”了Object的对象实例，因此几乎所有的实例对象都可以使用该方法。
 
## 时间格式化YYY-MM-DD
  
    now: function () {
      var time = new Date(),
          Y = time.getFullYear(),
          M = time.getMonth()+1,   
          D = time.getDate();

          M = M < 10? '0'+M : M;
          D = D < 10? '0'+D :D;
      return Y +'-'+ M +'-'+ D;
    }
## 任意时间

    date: function (Day) {
        var time = new Date();
            time.setDate(time.getDate() + Day);

        var Y = time.getFullYear(),
            M = (time.getMonth()+1) < 10 ? "0"+ (time.getMonth() + 1) : (time.getMonth() + 1),    
            D = time.getDate() < 10 ? "0" + time.getDate() : time.getDate();

        return Y + "-" + M + "-" + D;
    }
