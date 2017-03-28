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



### 在网页中编写数学公式




#### TeX或LaTeX格式






