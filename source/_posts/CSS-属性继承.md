---
title: CSS_属性继承
date: 2018-06-21 18:29:02
tags: 
- CSS
- 属性继承
categories: 好记性不如烂笔头
---
## CSS_属性继承 <span style="font-size:.5em">[待完善]</span>
>哪些属性可继承？？呃。。。往下看。

<!--more-->

## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接。
>- [参考链接](https://www.cnblogs.com/thislbq/p/5882105.html)
>- [CSS 参考手册](http://www.runoob.com/cssref/css-reference.html)
>- [CSS Properties](https://www.w3schools.com/cssref/css3_pr_align-content.asp)
----

## 一、**无继承性**的属性
### 1. display
定义元素生成的框的类型,下面是常用的属性值: 

display值      |    描述 
:--:    |   :--  
inherit	| 继承父元素 display 属性的值 
**none**	| 不会被显示
**block**	| 块级元素，前后会带有换行符
**inline**	| 默认。内联元素，前后没有换行符
**inline-block** | 行内块元素
|


### 2. 文本属性[部分属性无继承性]

文本属性|描述
:--:    |   :--  
vertical-align|垂直文本对齐
text-decoration|规定添加到文本的装饰
text-shadow|文本阴影效果
white-space|空白符的处理
unicode-bidi|设置文本的方向
|
### 3.Border/Outline属性
属性|描述
:--    |   :--  


### 3.盒子模型
盒子模型属性|描述
:--    |   :--  
width/height |宽/高
margin: top right bottom left|[上右下左]外边距
padding: top right bottom left|[上右下左]内边距
border: top right bottom left|[上右下左]边框
border-[top`|`right`|`bottom`|`left]-style |边框[上右下左]样式
border-[top`|`right`|`bottom`|`left]-width| 边框[上右下左]宽度
border-[top`|`right`|`bottom`|`left]-color| 边框[上右下左]颜色
|
    
### 4.背景属性[均无继承性]
背景属性|描述
:--    |   :--  
background|[颜色`|`图片`|`位置`|`大小`|`重复`|`原点`|`素材`|`附件]
background-color|颜色
background-image|图片
background-position|位置
background-size|大小
background-repeat|重复
background-origin|指定原点位置
background-clip|背景(颜色或图像)应在元素内延伸的距离
background-attachment|背景图像是否与页面的其余部分一起滚动,或者是否已修复。
|
### 5.定位属性
定位属性|描述
:--    |   :--  
float|指定元素应该如何浮动
clear|指定元素浮动元素的哪些边不允许浮动
position|指定用于元素的定位方法的类型(static/relative/absolute/fixed/sticky)
top`|`bottom|影响定位元素的垂直位置
left`|`right|影响定位元素的水平位置
min-[width`|`height]|定义了元素的最小宽度/高度
max-[width`|`height]|定义了元素的最大宽度/高度
overflow|溢出
clip|指定一个矩形来剪切绝对定位的元素
z-index|指定元素的堆栈顺序。
|

### 6.生成内容属性  
内容属性|描述
:--    |   :--  
content|::before和::after伪元素一起使用,以插入生成的内容
counter-reset|创建或重置一个或多个CSS计数器
counter-increment|增加或减少一个或多个CSS计数器的值
|

### 7.轮廓属性  
内容属性|描述
:--    |   :-- 
outline|轮廓[宽度/*样式/颜色]
outline-style|样式
outline-width|宽度
outline-color|颜色
|

### 8.打印属性  
内容属性|描述
:--    |   :-- 
size|
page-break-before|元素之前添加分页符
page-break-after|元素后添加分页符
page-break-inside|指定元素内避免分页符
|

### 9.声音样式属性  
内容属性|描述
:--    |   :-- 
pause-before|
pause-after|
pause|
cue-before|
cue-after|
cue|
play-during|
|

## 二、**有继承性**的属性

### 1.字体系列属性[均继承]
字体属性 | 描述
:---    |   :---  
font|[*size`|`*family`|`weight`|`style]
font-style|样式
font-variant|变形
font-weight|粗细
font-size/line-height|尺寸
font-family|字体系列
font-stretch|对字体进行伸缩变形
font-size-adjust|更好地控制字体大小。
|
### 2. 文本属性[部分继承]
文本属性|描述
:---: | :---
text-indent | 文本缩进
text-align | 文本水平对齐
line-height|行高
word-spacing|增加或减少**单词间**的空白（即字间隔）
letter-spacing|增加或减少**字符间**的空白（字符间距）
text-transform|控制文本大小写
direction|规定文本的书写方向
color|文本颜色
 |

### 3.visibility


### 4.表格布局属性 
表格布局属性|描述
:--    |   :--   
aption-side|
border-collapse|表格边框是应折叠为单个边框还是按标准HTML分隔
border-spacing|相邻单元格边界之间的距离
empty-cells|是否在表格中的空单元格上显示边框
table-layout|布置表格单元格，行和列的算法
|

### 5.列表布局属性[均继承]
盒子模型属性|描述
:--    |   :--  
list-style|[type`|`image`|`position]
list-style-type|类型
list-style-image|图像
list-style-position|位置inside`|`outside`|`initial`|`inherit;
|


### 6.引用属性:quotes
引用的引号类型:none|string|initial|inherit;

### 7.鼠标光标:cursor
        

### 8.打印属性
盒子模型属性|描述
:--    |   :--  
page|
windows|发生分页时必须在页面**顶部**保留的最少行数
orphans|生分页时必须在页面**底部**保留的最少行数
|

### 9.声音样式属性
盒子模型属性|描述
:--    |   :--  
speak|
speak-punctuation|
speak-numeral|
speak-header|
speech-rate|  
    
volume|
voice-family|
pitch|
pitch-range|
stress|
richness|
azimuth|
elevation

 

