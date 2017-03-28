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

这种格式通过用* 数学分隔符*将数学式包围起来，使Mathjax能区分哪些是数学式，
哪些是普通文本。有两种形式：一种是在段落内的，叫*in-line mathematics*；
另一种是独立成段的，叫*displayed mathematics*。


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



#### TeX或LaTeX格式






