---
layout: post
title: Markdown中插入LaTex公式的方法
category: 技术
tags: [Markdown,LaTeX]
keywords: Latex, Markdown, Mathematics formula
description: 
---

在Markdown中插入数学公式, 一种方法是把公式保存为图片, 然后在正文使用img标签进行引用, 然而当你有很多公式需要编辑的时候, 这种办法就让人很头疼. 因为你需要在编辑公式, 保存图片, img标签引用之间来回切换.  

一种更为简单方便的方法是, 使用html语法, 调用在线LaTex公式编辑器的公式生成API, 在线生成LaTex数学公式, 这样可以避免将公式保存为图片. 弊端是公式很多的时候, 网页刷新可能会比一般的网页慢一些.  

## 方法一: 使用Google Chart的服务器  

```html
<img src="http://chart.googleapis.com/chart?cht=tx&chl= 在此插入Latex公式" style="border:none;">
```

例子:  

```html
<img src="http://chart.googleapis.com/chart?cht=tx&chl=\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" style="border:none;">  
```  

公式显示结果为:  
![google-chart-formula](/public/img/tech/latex/markdown-insert-formula-example-google-chart.png)  

Google Chart服务器的响应速度还可以, 但据说可能复杂的LaTex公式可能无法解析.  

## 方法二: 使用forkosh服务器  

forkosh上提供了关于LaTex公式的一份简短而很有用的帮助.  

使用forkosh插入公式的方法是  

```html
<img src="http://www.forkosh.com/mathtex.cgi? 在此处插入Latex公式">
```  

例子:  

```html
<img src="http://www.forkosh.com/mathtex.cgi? \Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}">
```  

显示结果是:  
![forkosh-formula](/public/img/tech/latex/markdown-insert-formula-example-forkosh.png)  

因为网页插入公式的原理是调用"某某网站的服务器"动态生成的, 所以保证公式正常显示的前提是该网站公式生成服务一直有效. forkosh在这方面据说表现不错.  

## 方法三: 使用MathJax引擎

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>

[Stakeoverflow](http://stackoverflow.com/)上漂亮的公式是用MathJax引擎生成. 值得一提的是, MathJax引擎生成的公式不是图片. 在Markdown中添加MathJax引擎也很方便:  

```html
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
```  

然后, 直接使用Tex编辑公式即可. `$$公式$$`表示行间公式, 本来Tex中使用`\(公式\)`表示行内公式, 但因为`\`是Markdown的转义字符, 所以在Markdown中输入行内公式应使用`\\(公式\\)`, 下面行间公式代码,

```tex
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}}$$
```  

显示的行间公式结果如下,  
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$  

而行内公式代码,

```tex
\\(x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\\)
```  

给出的则是下面的结果,  
\\(x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\\).  

MathJax引擎生成的公式, 你还可以使用鼠标右键进行操作.
