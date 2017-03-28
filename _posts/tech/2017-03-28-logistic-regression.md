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



逻辑回归属于概率型非线性回归，分为二分类和多分类的回归模型。对于二分类的逻辑回归，
因变量$ y $只有“是、否”两个取值，记为1和0。假设在自变量$ x\_1,x\_2,\ldots,x\_p$ 作用下，
$ y$取“是”的概率是$ p$，则取否的概率是$ 1-p$，研究的是当$ y$取"是"发生的概率$ p$与
自变量$ x\_1,x\_2,\ldots, x\_p$的关系。


### 1. 逻辑回归分析介绍  

#### (1) Logistic函数  

Logistic回归模型中的因变量的值只有1-0(如是和否、发生和不发生)两种取值。假设在$ p$
个独立自变量$ x\_1, x\_2,\ldots,x\_p$作用下，记$y$取1的概率是$ p=P(y=1|X)$，取0的概率是
$1-p$，取1和0的概率之比为$\frac{p}{1-p}$，称为事件的优势比(odds)，对odds取自然对数
即得Logistic变换${\mathrm{Logit}(p)=\ln\left( \frac{p}{1-p}\right)}$.  


令$\mathrm{Logit}(p)=\ln\left(\frac{p}{1-p}\right)$，则$p={1 \over 1 + e^{-z}}$即为
Logistic函数，如下图所示。
<center>
![logistic-fun](/public/img/tech/ml/logistic_regression.jpg)
</center>


当$p$在$(0,1)$之间变化时，odds的取值范围是$0,+\infty$，则$\ln\left( {p \over 1-p} \right)$
的取值范围是$(-\infty,+\infty)$. 


#### (2) 逻辑回归模型
逻辑回归模型是建立$\ln\left( {p\over 1-p} \right)$与自变量的线性回归模型。

逻辑回归模型为：
$$\ln\left( {p\over 1-p} \right)=\beta\_0 + \beta\_1x\_1 + \cdots + \beta\_p x\_p + \varepsilon$$
因为$\ln\left( {p\over 1-p} \right)$的取值范围是$(-\infty,+\infty)$，这样，自变量$x\_1,x\_2,\cdots,x\_p$
可在任意范围内取值。记$g(x)=\beta\_0 + \beta\_1 x\_1 + \cdots + \beta\_p x\_p$，得到：
$$p = P(y=1|X)={1 \over 1 + e^{-g(x)}}$$
$$1-p = P(y=0|X)=1 - {1\over 1 + e^{-g(x)}}= {1\over 1 + e^{g(x)}}$$


#### (3) 逻辑回归模型解释
$${p\over 1-p}= e^{\beta\_0 + \beta\_1 x\_1 + \cdots + \beta\_p x\_p + \varepsilon}$$
$\beta\_0$: 在没有自变量，即$x\_1,x\_2,\cdots,x\_p$全部取0, $y=1$与$y=0$发生概率之比的自然
对数; $\beta\_i$: 某自变量$x\_i$变化时，即$x\_i=1$与$x\_i=0$相比，$y=1$优势比的对数值。



### 2. 逻辑回归建模步骤

逻辑回归模型的建模步骤如下。  


1. 根据分析目的设置指标变量(因变量和自变量)，然后收集数据，根据收集到的数据，对特征再次进行筛选;
2. $y$取1的概率是$p=P(y=1|X)$, 取0的概率是$1-p$。用$\ln\left( {p\over 1-p} \right)$和自变量列出
   线性回归方程，估计出模型中的回归系数;
3. 进行模型检验。模型有效性的检验指标有很多，最基本的有正确率，其次有混淆矩阵、ROC曲线、KS值等。
4. 模型应用：输入自变量的取值，就可以得到预测变量的值，或者根据预测变量的值去控制自变量的取值。
