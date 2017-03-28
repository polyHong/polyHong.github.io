---
layout: post
title: Jekyll博客中使用Mathjax写数学公式
category: 技术
tags: [Markdown,LaTeX,Mathjax]
keywords: Latex, Markdown, Mathematics formula
description: 
---

### 简介
MathJax 是一个能将 LaTeX，MathML 和 AsciiMath 表示的数学式在现代浏览器网页上正确呈现现出来的开源JavaScript显示引擎。
使用时，只需在网页上包含进 MathJax，之后按 LaTeX, MathML 或 AsciiMath 的规则编写的数学式将被JavaScript转换成
HTML、SVG 或 MathML 格式的同等式正确显示，它不要求客户端进行插件等的下载。


### 加载Mathjax
在页面的`<head>`中加载如下脚本：

```javascript
<script type="text/javascript" async src="//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
```
这里的`TeX-MML-AM_CHTML`是最常用的配置，能用来快速上手 Mathjax，更多的配置信息可参考
[Loading and Configuring MathJax](http://docs.mathjax.org/en/latest/configuration.html#loading).


### 在网页中编写数学公式

根据目前的配置，现在可以在网页中使用TeX,LaTeX,MathML,AsciiMath表示法的数学式，也可以混合使用。

#### TeX或LaTeX格式

这种格式通过用 *数学分隔符*将数学式包围起来，使Mathjax能区分哪些是数学式，
哪些是普通文本。有两种形式：一种是在段落内的，叫 *in-line mathematics*；
另一种是独立成段的，叫 *displayed mathematics*。


*displayed mathematics*的默认分隔符是`$$...$$` 和`\[...\]`，而*in-line mathematics*的默认分隔符是`(\...\)`,
如果要想使用`$...$`作为分隔符，需要加上如下的配置：

```html
<!DOCCTYPE html>
<html>
<head>
<title>MathJax TeX Test Page</title>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});
</script>
<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
</script>
</head>
<body>
When <span>$a \ne 0$</span>, there are two solutions to <span>$ax^2 + bx + c = 0$</span> and they are
<div>$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$</div>
</body>
</html>
```

显示效果如下：

<script type="text/x-mathjax-config">
MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});
</script>

<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
</script>
When <span>$a \ne 0$</span>, there are two solutions to <span>$ax^2 + bx + c = 0$</span> and they are
<div>$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$</div>


由于TeX表达式是网页的一部分，因此要注意输入数学式时不要与HTML的符号冲突，
特别如_小于_号，因为这是HTML用于开启一个标签的符号。注意在数学式的小于
号两边加空格。

如果使用Markdown编写，要注意：TeX使用下划线来表示下标，而Markdown用下划线
表示斜体，因此TeX表示下标的下划线要用\_转义。


TeX中的几个特殊符号：  
* `^`表示上标  
* `\_`表示下标  
* `{}`用于分组  


更多的基本使用教程见[tuicoll上的一篇文章](www.tuicool.com/articles/7zqYFb3).


Markdown LaTeX的参数文章：  
* [Mathjax](https://cdn.mathjax.org/mathjax/latest/test/examples.html)  
* [Markdown LaTeX在线编辑器](https://kerzol.github.io/markdown-mathjax/editor.html)  
* [LaTeX完整教程](http://www.forkosh.com/mathtextutorial.html)   
* [LaTeX数学符号表，PDF文件](http://mirror.lzu.edu.cn/CTAN/info/symbols/math/maths-symbols.pdf)   





