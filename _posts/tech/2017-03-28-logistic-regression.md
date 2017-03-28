---
layout: post
title: 逻辑回归(Logistic Regression)原理
category: 技术
tags: [Machine Learning,Statistics]
keywords: 
description: 
---



逻辑回归是因变量一般是1和0两种取值的一类回归模型。它是广义线性回归模型的特例，
利用Logistic函数将函数因变量的取值范围控制在0和1之间，表示取值为1的概率。在
信号处理，机器学习等领域有着非常广泛的应用。  

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['$','$']]}});
</script>
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default">
</script>



逻辑回归属于概率型非线性回归，非为二分类和多分类的回归模型。对于二分类的逻辑回归，
因变量$ y $只有“是、否”两个取值，记为1和0。假设在自变量$ x\_1,x\_2,\ldots,x\_p$ 作用下，
$ y$取“是”的概率是$ p$，则取否的概率是$ 1-p$，研究的是当$ y$取"是"发生的概率$ p$与
自变量$ x\_1,x\_2,\ldots, x\_p$的关系。


### 1. 逻辑回归分析介绍  

#### (1) Logistic函数  

Logistic回归模型中的因变量的值只有1-0(如是和否、发生和不发生)两种取值。假设在$ p$
个独立自变量$ x\_1, x\_2,\ldots,x\_p$作用下，记$y$取1的概率是$ p=P(y=1|X)$，取0的概率是
$1-p$，取1和0的概率之比为$\frac{p}{1-p}$，称为事件的优势比(odds)，对odds去自然对数
即得Logistic变换${\mathrm{Logit}(p)=\ln\left( \frac{p}{1-p}\right)}$.  







#### (2) 逻辑回归模型




#### (3) 逻辑回归模型解释




### 2. 逻辑回归建模步骤


