---
layout: default
title: 技术科普 JavaScript
---

# <center><font size="7" font face="楷体" font color="#006666">技术科普 JavaScript</font></center>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font size="4"  font face="楷体">小伙伴们，在这里我要 introduce 的是一门编程语言：<font size="4">JavaScript</font>。对于编程语言，广为人知的便是 C、C++、Python、Java 和 JavaScript 了。那么 JavaScript 到底是一门怎样的语言呢？我就在这简单地介绍一下吧 (毕竟我也是一枚小白呀~~~~~~ )。</font>
# JavaScript 简介
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**JavaScript** 是一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言，内置支持类型。它的解释器被称为 JavaScript 引擎，为浏览器的一部分，广泛用于客户端的脚本语言，最早是在 **HTML**（标准通用标记语言下的一个应用）网页上使用，用来给 HTML 网页增加动态功能。<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在1995年时，由 **Netscape** 公司的 Brendan Eich，在网景领航者浏览器上首次设计实现而成。因为 Netscape 与 Sun 合作，Netscape 管理层希望它外观看起来像 Java，因此取名为 JavaScript。但实际上它的语法风格与 Self 及 Scheme 较为接近。<br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;为了取得技术优势，微软推出了JScript，CEnvi 推出 ScriptEase，与 JavaScript 同样可在浏览器上运行。为了统一规格，因为 JavaScript 兼容于 ECMA 标准，因此也称为 **ECMAScript** (简称 **ES** )。<br>
![](https://image.baidu.com/search/detail?ct=503316480&z=&tn=baiduimagedetail&ipn=d&word=Netscape&step_word=&ie=utf-8&in=&cl=2&lm=-1&st=-1&cs=1912092249,3074237694&os=1574825493,104625872&simid=3252705511,225275602&pn=1&rn=1&di=194395414400&ln=1903&fr=&fmq=1539430514784_R&ic=0&s=undefined&se=&sme=&tab=0&width=&height=&face=undefined&is=0,0&istype=2&ist=&jit=&bdtype=0&spn=0&pi=0&gsm=0&objurl=http%3A%2F%2Fphotocdn.sohu.com%2F20131219%2FImg392023668.jpg&rpstart=0&rpnum=0&adpicid=0 "Netscape")
# JavaScript基础语法
## 1、三条基本指令
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;JavaScript 是一门与浏览器密切相关的语言，适用于前端处理。以下便是 JavaScript最常用的三条基本的指令：
### （一）alert 警告框指令
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;语法： &nbsp;&nbsp;***alert("你需要弹出的内容")***<br>
![](图片/alert.jpg "alert")<br>
![](图片/alert2.jpg "执行效果")<br><br>
### （二）document.write 文本指令
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;语法：&nbsp;&nbsp;***document.write("你要写入的内容")***<br>
![](图片/document.jpg "document.write")<br>
![](图片/document2.jpg "执行效果")<br><br>
### （三）console.log 控制台指令
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;语法：&nbsp;&nbsp; ***console.log("你要写入的内容")*** <br>
![](图片/console.jpg "console.log")<br>
![](图片/console2.jpg "执行效果")<br><br>
## 2、JavaScript 基本语法
### （1）注释
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;分为了 **多行注释** 和 **单行注释**<br>
![](图片/注释符.jpg "注释")<br><br>
### （2）JS中严格区分大小写
### （3）JS中每条语句以（ ; ）结尾
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1、如果不以（ ; ）结尾,浏览器会自动添加，但是会消耗一些资源；<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2、有些时候，浏览器会加错分号,导致程序语义出现错误。
### （4）JS中会忽略多个空格与换行，所以我们可以利用空格与换行对代码进行格式化
## 3、JavaScript 基本概念
### （1）字面量和变量
![](图片/字面量.jpg "字面量与变量")<br><br>
在JS中，使用 var 来声明一个变量<br>
![](图片/变量声明.jpg "变量声明")<br><br>
使用 = 进行变量赋值，并且声明与赋值可同时进行<br>
![](图片/变量赋值.jpg "变量赋值")<br><br>
### （2）字符串
![](图片/字符串.jpg "字符串")<br>
![](图片/转义字符.jpg "转义字符")<br><br>
### （3）标识符
![](图片/标识符.jpg "标识符")<br><br>
## 4、JavaScript 数据类型
### （1）六种数据类型一览
![](图片/六种数据类型.jpg "六种数据类型")<br><br>
其中有 **五种** 数据类型被称为 **基本数据类型**<br><br>
### （2）基本数据类型介绍
#### 1、String
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;即 **字符串**，介绍如上
#### 2、Number
![](图片/Number.jpg "Number")<br><br>
**Typeof** 运算符的使用<br>
![](图片/Typeof.jpg "Typeof")<br><br>
#### 3、布尔值
![](图片/Boolean.jpg "Boolean")<br><br>
#### 4、null 和 undefined
![](图片/null.jpg "null 和 undefined")<br><br>
### （3）强制数据类型转换
#### 1、强制转换为 Number
![](图片/转Number.jpg "强制转换为Number")<br>
![](图片/转Number2.jpg "强制转换为Number")<br><br>
#### 2、强制转换为 String
![](图片/转String.jpg "强制转换为String")<br><br>
#### 3、强制转换为 Boolean
![](图片/转Boolean.jpg  "转Boolean")<br><br>
<font size="4"  font face="楷体">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;小伙伴们，初识JavaScript有什么感受吗？有没感到 dokidoki 心脏乱跳呢？这里我们接触的都是 基础中的基础。 如果小伙伴真的感到了小鹿乱撞，那就自己接着去更深入地了解它吧！</font>