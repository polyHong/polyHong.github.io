---
layout: post
title: VIM剪贴板和寄存器的使用
category: 技术
tags: [Vim,Ubuntu]
keywords: Ubuntu, Linux
description: 
---


将寄存器与各种删除、复制、粘贴命令组合使用，能够大大提高编辑文本的效率。

##### **1) 系统剪贴板**
如果想从系统剪贴板粘贴内容到Vim，那么只需要在输入模式下使用`Shift+Insert`组合键
即可。从Vim复制内容到系统剪贴板，在normal模式下使用`"+y`命令。

##### **2) 复制粘贴基本命令**


<table>
<tbody><tr>
<td>
yy
</td>
<td>
复制游标所在行整行。或大写一个Y。
</td>
</tr>
<tr>
<td>
2yy或y2y
</td>
<td>
复制两行
</td>
</tr>
<tr>
<td>
y^
</td>
<td>
复制至行首，或y0
</td>
</tr>
<tr>
<td>
y$
</td>
<td>
复制至行尾。含游标所在处字元
</td>
</tr>
<tr>
<td>
yw
</td>
<td>
复制一个word
</td>
</tr>
<tr>
<td>
y2w
</td>
<td>
复制两个字（单词）
</td>
</tr>
<tr>
<td>
yG
</td>
<td>
复制至档尾
</td>
</tr>
<tr>
<td>
y1G
</td>
<td>
复制至档首
</td>
</tr>
<tr>
<td>
p
</td>
<td>
小写p代表贴至游标后（下）
</td>
</tr>
<tr>
<td>
P
</td>
<td>
大写P代表贴至游标前（上）
</td>
</tr>
</tbody>
</table>



