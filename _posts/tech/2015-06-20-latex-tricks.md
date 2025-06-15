---
layout: post
title: 使用LaTeX的技巧
category: 技术
tags: LaTeX
keywords: LateX
description: 
---


## LaTex正确输入双(单)引号  

好几次使用Latex都碰到需要用到双引号, 然而连续两次键入键盘上的双引号并不能得到正确的双引号输出.

Latex中双引号的正确输入方式如下：  

1. 找到Tab键上方的*~*和*`*键，如下图

<center>
![pix1](/public/img/tech/latex/double-quote-mark.jpg)
</center>>
2. 使用该键(即*~*和*`*键)连续键入两个*`*(即*``*)然后键入两个单引号(即*''*). 单引号的输入类似.  
3. 下面是一个例子. 下图是最终效果图,  
<center>  
![pix2](/public/img/tech/latex/double-quote-mark-example.png)
</center>

下面是实现上图效果的代码:

```tex
\documentclass{article}
\setlength
\textwidth{150pt}
\begin{document}
\large
 Pumas are ``large, cat-like animals'' which are `found in America'. 
 When reports came into London Zoo that a wild puma had been spotted 
 forty-five miles south of London, they were not taken seriously. 
 However, as the evidence began to accumulate, experts from the Zoo 
 felt obliged to investigate, for the descriptions given by people 
 who claimed to have seen the puma were extraordinarily similar. 
\end{document}
```

## LaTex表格线颜色设置  

导言区添加如下宏包: 边框颜色要用到`booktabs`和`colortbl`宏包,
下面的代码里有一个自定义的颜色`tabcolor`.

```tex  
\usepackage{ctexcap}  
\usepackage{graphicx}   
\usepackage{amsmath}  
\usepackage{amssymb}  
\usepackage{array}  
\usepackage{times,psfig,amsmath,subfigure}  
\usepackage{color}  
\usepackage{algorithm}  
\usepackage{booktabs}  
\usepackage{multirow}  
\usepackage{colortbl}  
\definecolor{tabcolor}{rgb}{.105,.410,.113}   
```  

如下表格:  
<center>
![tabular-rule-color](/public/img/tech/latex/tabular-rule-color.jpg)
</center>  

对应的代码如下:  

```tex
\begin{table}[h]
\centering
\begin{tabular}{cccc}
\arrayrulecolor{tabcolor} \toprule[1.4pt] 
&文科 & 理科 & 总计 \\
\hline
男& 77 & 98 & 175 \\
女& 101 & 72 & 173 \\
总计& 178 & 170 & 348 \\
\bottomrule[1.4pt]
\end{tabular}
\caption {问卷调查对象基本情况汇总表.}
\label{tab:number}
\end{table
```

## `\vspace`和`\vskip`命令的区别  
  
编辑LaTex文档是, `\vspace`和`\vskip`命令都能产生一个垂直距离. 然而它们有什么区别呢?  

1. `\vspace`是LaTex命令, `\vskip`是Tex命令;  
2. 使用方法不同: `\vspace{1cm}`, `\vskip 1cm`;  
3. 产生的效果有区别:

> - `\vspace`命令是在命令出现的当前行输出完后, 才生成垂直间距;生成间距后, 继续之前段落的内容(逻辑上还是相同的一段);
> - `\vskip`命令是在命令出现时立马生成垂直间距; 生成间距后, 开始一个新的段落(逻辑上分段).

## `\rule`, `hrule`, `\hfill`和`\hrulefill`命令  
  
- `\rule`: 绘制水平线. 其用法是`\rule{depth}{width}{height}`, 详见[http://en.wikibooks.org/wiki/LaTeX/Rules_and_Struts](http://en.wikibooks.org/wiki/LaTeX/Rules_and_Struts). `\rule`一个很常见的用途是在一个`box`命令中加`\rule{0pt}{height}`, 绘制一个最小高度为`height`的柱子;  
- `\hrule`: 绘制一条水平的`rule`(尺子), `rule`包含三个参数(width, length, depth).  例如,  

```tex
\hrule                                  %可以得到一条水平直线(默认宽度为  
                                        %0.4pt, length适应周围环境);    
\hrule width2pt length 2cm depth2pt     %可以得到一条定制的直线.
```
  
同样, 也有`\vrule`命令，绘制一条竖直的`rule`. 如果`\hrule`和`\vrule`参数一致, 得到的结果也相同.

- `\hfill`: 水平空白, 弹性长度填充. 例如,  

```tex
This \hfill is a text.   %This将会左对齐, is a text将会右对齐,    
                         %中间就是\hfill填充. 之所以是弹性长度, 
       %是根据内容来填充空白.
```

- `\hrulefill`: 一行剩余的空白用rule填充.  

> 该命令与`\hrule`的不同在于: 两者生成的直线上下空白不同, 且`\hrulefill`是填充剩下的空白，而`\hrule`在该行下重新绘制一条直线.  

## 拆分源文件并分别编译  
  
当处理很大的文档时，经常将文件分成若干个部分分别进行编译，这时我们可以使用LATEX所提供的命令:  
  
> - `\input`  
> - `\include`  
> - `includeonly`  

### `\input{textfile}`  
  
文件名只需指定基本名, 不需加扩展名`.tex`, 它等价于直接将文件`文件名.tex`中的内容输入到命令`\input`所处的位置. 此命令可以放在文档的任何地方(导言区或正文区), 而且可以相互嵌套. 你可以将经常使用的导言放在单独的一个文件中, 使用时置于源文件之首.  
  
在`\begin{document}....\end{document}`之间加入多个`\input`命令. 导言区加入`\listfiles`可以得到读入文件的清单.

### `\include{textfile}`  
  
使用`\input`命令的缺点是,通过`\input`命令合并起来的文章(不管那部分)每经过一次修改, 所有的文件都要被重新读入和处理.
若用`\input`命令仅加载那个特定的文件, 那么所有的页码、章节、插图和公式等的自动编号都从1开始, 这会使交叉引用产生混乱.

更好的办法是采用`\include`命令. 它只能放在文档的正文区, 不能嵌套, 且与命令`\includeonly{文件清单}`结合使用.文件清单
列出当前正在处理的文件(其中的文件名不需要加后缀`.tex`, 各文件名用逗号隔开). 若`\input`命令后的文件名在文件清单中，
则此命令等价于`\clearpage\input{文件名}\clearpage`, 否则相当于换页. 因此文档应该在新页开始(如章与章之间)分割.  

`\include`命令可以帮助我们省去很多宝贵的编译时间. 它的主要好处是页面、章节和公式编号的附加信息可以由`\includeonly`命令提供,
因此交叉引这类命令, 如`\ref`和`pageref`命令等能生成正确的结果. 此命令可多次使用, 所需的导言区仅有一个.  

## LaTex的长度单位  

LaTex支持的长度单位有:  
>`in` - 英寸(inch);  
>`mm` - 毫米(millimeters);
>`cm` - 厘米(centimeters);
>`pt` - points(大约1/72inch);
>`em` - 接近当前字体的字符"M"的宽度(approximately the       >       width of a "M" in current font);
>`ex` - 接近当前字体的字符"x"的高度(approximately the height of an "x" in the current font).
  
长度也可以是负值. 例如`-1.5em`. 注意到数字`0`本身不是一个长度, 必须表明是`0in`或`0pt`等.

## LaTex输入矩阵

一般来讲, LaTex中矩阵的输入有两种方法可以实现, 即amsmath宏包提供的矩阵环境和LaTex提供的阵列环境array. 第一种方法使用简单方便, 但是缺乏灵活性, 矩阵元素align只能是默认的矩阵排列; 第二种方法, 输入相对繁琐, 但是相应地可以灵活定制一些特殊结构.

### 1. amsmath宏包提供的矩阵环境

- `matrix`环境: 没有括号的矩阵
- `pmatrix`环境: 用小括号括起来的矩阵
- `bmatrix`环境: 用中括号括起来的矩阵
- `Bmatrix`环境: 用大括号括起来的矩阵
- `vmatrix`环境: 用单竖线括起来的矩阵
- `Vmatrix`环境: 用双竖线括起来的矩阵

举例:  
  
```tex
\begin{bmatrix}
1 & t_1 & t_1^2 & \cdots & t_1^{n-1}\\ 
1 & t_2 & t_2^2 & \cdots & t_2^{n-1}\\ 
\vdots & \vdots  & \vdots & \ddots & \vdots\\ 
1 & t_n & t_n^2 & \cdots & t_n^{n-1}
\end{bmatrix}
```  

结果如下:  

$$
\begin{bmatrix}
1 & t_1 & t_1^2 & \cdots & t_1^{n-1}\\
1 & t_2 & t_2^2 & \cdots & t_2^{n-1}\\
\vdots & \vdots  & \vdots & \ddots & \vdots\\
1 & t_n & t_n^2 & \cdots & t_n^{n-1}
\end{bmatrix}
$$

### 2. LaTex提供的array环境

举例:

```tex
\left[ \begin{array}{lcr}
1 & 2 & 3 \\ 2 & 3 & 4 
\end{array}  \right]
```

结果如下:

$$ 
\left [\begin{array}{lcr}
1 & 2 & 3 \\ 2 & 3 & 4
\end{array}  \right]
$$
