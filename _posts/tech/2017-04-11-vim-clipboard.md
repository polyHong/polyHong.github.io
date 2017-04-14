---
layout: post
title: VIM剪贴板和寄存器的使用
category: 技术
tags: [Vim,Ubuntu]
keywords: Ubuntu, Linux
description: 
---


将寄存器与各种删除、复制、粘贴命令组合使用，能够大大提高编辑文本的效率。

##### **1) 复制粘贴基本命令**

<center>
<table>
<tbody><tr>
<td>
yy
</td>
<td>
复制游标所在行整行。或大写一个Y
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
</center>


##### **2) 系统剪贴板的使用**

- 从系统剪贴板粘贴: `Shift+Insert`;
- 选择全文: `gg shift+V shift+g`;
- 复制到系统剪贴板    

```vim
"+y  把选中内容复制到系统剪贴板
"+p  把系统剪贴板里的内容粘贴到vim
```

- 将Vim默认剪贴板设为系统剪贴板: `set clipboard=unnameplus`



