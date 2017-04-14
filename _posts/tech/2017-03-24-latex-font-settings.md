---
layout: post
title: LaTex字体设置
category: 技术
tags: LaTeX
keywords: Latex
description: 
---


## 字体设置  

使用`times new roman`字体应使用`usepackage{txfonts}`宏包. 使用粗体应使用
`usepackage{bm}`宏包. 下面对常用字体命令做一个归纳:  

```tex
\bf             % 罗马族，直立形状，黑体系列
\it             % 罗马族，斜体形状，中等粗细系列
\rm             % 罗马族，直立形状，中等粗细系列，默认的字体
\sc             % 罗马族，小型大写形状，中等粗细
\sf             % 无衬线族，直立形状，中等粗细
\sl             % 罗马族，slanted的斜体形状，中等粗细系列
\tt             % 打字机族，直立形状，中等粗细
\em             % 强调字体，它与当前字体同族、同系列，但形状不同
\emph           % 用强调字体打印文本，它与当前字体同族、同系列，但形状不同
```

```tex
\normalfont     % 把字体转换为默认的族、形状和系列
\bfseries       % 不改变当前字体的族与形状，但转变成bold序列
\mdseries       % 不改变当前字体的族与形状，但转变成中等粗细medium序列
\itshape        % 把字体的形状属性改为斜体，但保留族与系列不变
\scshape        % 把字体的形状属性改为小型大写，但保留族与系列不变
\slshape        % 把字体的形状属性改为slanted的斜体，但保留族与系列不变
\upshape        % 把字体的形状属性改为直立，但保留族与系列不变
\rmfamily       % 使字体保持当前的系列与形状属性，但转变为罗马族
\sffamily       % 使字体保持当前的系列与形状属性，但转变为无衬线族
\ttfamily       % 使字体保持当前的系列与形状属性，但转变为打字机族
```

```tex
\mathbf         % 数学模式里用粗体打印文本，空格被忽略
\mathcal        % 数学模式里用书写体打印文本
\mathit         % 数学模式里用斜体打印文本
\mathnormal     % 数学模式里用数学字体打印文本
\mathrm         % 数学模式里用罗马体（\rmfamily）打印文本，其中的空格被忽略
\mathsf         % 数学模式里用无衬线字体（\sffamily）打印文本，其中的空格被忽略
\mathtt         % 数学模式里用打印机字体（\ttfamily）打印文本，其中的空格被忽略
```

```tex
\textbf         % 等价于{\bfseries 文本}
\textit         % 等价于{\itshape 文本}
\textmd         % 等价于{\mdseries 文本}
\textnormal     % 等价于{\normalfont 文本}
\textrm         % 等价于{\rmfamily 文本}
\textsc         % 等价于{\scshape 文本}
\textsf         % 等价于{\sffamily 文本}
\textsl         % 等价于{\slshape 文本}
\texttt         % 等价于{\ttfamily 文本}
\textup         % 等价于{\upshape 文本}
```


##  字号设置
### 方法一: LaTex默认命令  

字体大小设置命令由小到大依次为:

```tex
\tiny
\scriptsize
\footnotesize
\small 
\normalsize
\large
\Large
\LARGE
\huge
\Huge  
```  
一般来说, 这些命令足够应付日常工作需要.
    

### 方法二: `\fontsize{字号}{行距}`命令  

通过`\fontsize{字号}{行距}`命令来定义字体的大小. 
使用这个命令, 需要在导言去加入下面的语句

```tex
\usepackage{type1cm}  % cm为Computer Modern的缩写
```  
需要注意的是, 这个命令对其后所有文本都起作用, 在使用此命令后需要用
`\selectfont`才能使字体大小设置起作用.   

在中文环境下, 通常会遇到"正文使用小四, 宋体"这样的规定, 但是LaTex并没
有小四, 只有pt. 下面是字号对应的转换表:  
<center>
<table summary="special registers" border="1" cellspacing="0" cellpadding="3"><tbody><tr><th>类别</th><th>符号</th><th>描述</th></tr><tr><td>未命名寄存器</td><td>"</td><td>上一次复制或删除的文本</td></tr><tr><td>数字寄存器</td><td>0-9</td><td>文本删除历史</td></tr><tr><td>短删除寄存器</td><td>-</td><td>删除少于一行的文本</td></tr><tr><td>命名寄存器</td><td>a-z,A-Z</td><td>存放文本</td></tr><tr><td rowspan="4">只读寄存器</td><td>%</td><td>当前文件的名字</td></tr><tr><td>#</td><td>交替文件的名字</td></tr><tr><td>.</td><td>上一次插入的文本</td></tr><tr><td>:</td><td>上一次执行的命令</td></tr><tr><td>表达式寄存器</td><td>＝</td><td>返回表达式结果</td></tr><tr><td rowspan="3">选择和拖拽寄存器</td><td>*</td><td>系统剪切板</td></tr><tr><td>+</td><td>系统剪切板（X11）</td></tr><tr><td>~</td><td>拖拽的文本</td></tr><tr><td>黑洞寄存器</td><td>_</td><td>永久删除的文本</td></tr><tr><td>搜索模式寄存器</td><td>/</td><td>搜索模式</td></tr></tbody></table>
<tr>
   <td> 字号 </td> <td> 大小 (pt)</td> <td>1.5倍行距\baselineskip值 </td>
</tr>
<tr>
<td><center>初号</center> </td> <td><center>42pt</center></td> <td><center>63pt</center> </td>
</tr>  
<tr>
<td><center>小初 </center></td> <td><center>36pt </center></td> <td><center>54pt </center></td>
</tr>
<tr>
<td><center>一号 </center></td> <td><center> 26pt</center></td> <td><center> 39pt</center></td>
</tr>
<tr>
<td><center>小一 </center></td> <td><center>24pt </center></td> <td><center> 36pt</center></td>
</tr>

<tr>
<td><center>二号 </center></td> <td><center> 22pt</center></td> <td><center>33pt </center></td>
</tr>
<tr>
<td><center>小二 </center></td> <td><center>18pt </center></td> <td><center>27pt </center></td>
</tr> 
<tr>
<td><center>三号 </center></td> <td><center>16pt </center></td> <td><center>24pt </center></td>
</tr>
<tr>
<td><center>小三 </center></td> <td><center>15pt </center></td> <td><center>22.5pt </center></td>
</tr>

<tr>
<td><center> 四号</center></td> <td><center> 14pt</center></td> <td><center> 21pt</center></td>
</tr>
<tr>
<td><center>小四 </center></td> <td><center>12pt </center></td> <td><center>18pt </center></td>
</tr>
<tr>
<td><center>五号 </center></td> <td><center>10.5pt</center></td> <td><center>15.75pt </center></td>
</tr>
<tr>
<td><center> 小五</center></td> <td><center>9pt </center></td> <td><center> 13.5pt</center></td>
</tr>

<tr>
<td><center>六号 </center></td> <td><center>7.5pt</center></td> <td><center>11.25pt</center></td>
</tr>
<tr>
<td><center>小六 </center></td> <td><center>6.5pt</center></td> <td><center>9.75pt</center></td>
</tr>
<tr>
<td><center>七号 </center></td> <td><center>5.5pt</center></td> <td><center>8.25pt</center></td>
</tr>
<tr>
<td><center>小七</center></td> <td><center>5pt</center></td> <td><center>7.5pt</center></td>
</tr> 
</table>
</center>  
比如,`\fontsize{12pt}{18pt}\selectfont`就设置了*小四, 且1.5倍*行距. 

>错误：  
>Latex font warning: font shape `OT1/cmr/m/n' in size <15> not available  
>  
> LaTeX font warning: size s stitutions with differencesup to 0.6 pt have occurred

>解决方案：\usepackage{type1cm}  


通常我们会根据具体要求在源文件的导言区加入下面的语句，以方便设置字号：

```tex
\newcommand{\yihao}{\fontsize{26pt}{36pt}\selectfont}        % 一号, 1.4 倍行距
\newcommand{\erhao}{\fontsize{22pt}{28pt}\selectfont}        % 二号, 1.25倍行距
\newcommand{\xiaoer}{\fontsize{18pt}{18pt}\selectfont}       % 小二, 单倍行距
\newcommand{\sanhao}{\fontsize{16pt}{24pt}\selectfont}       % 三号, 1.5倍行距
\newcommand{\xiaosan}{\fontsize{15pt}{22pt}\selectfont}      % 小三, 1.5倍行距
\newcommand{\sihao}{\fontsize{14pt}{21pt}\selectfont}        % 四号, 1.5 倍行距
\newcommand{\banxiaosi}{\fontsize{13pt}{19.5pt}\selectfont}  % 半小四, 1.5倍行距
\newcommand{\xiaosi}{\fontsize{12pt}{18pt}\selectfont}       % 小四, 1.5倍行距
\newcommand{\dawuhao}{\fontsize{11pt}{11pt}\selectfont}      % 大五号, 单倍行距
\newcommand{\wuhao}{\fontsize{10.5pt}{15.75pt}\selectfont}   % 五号, 单倍行距
```  

`\song\xiaosi`可以快速设置为 *宋体，小四，1.5 倍* 行距.
