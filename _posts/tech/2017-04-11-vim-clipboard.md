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
<table summary="special registers" border="1" cellspacing="0" cellpadding="3">
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


##### **3) 制定寄存器**
在复制或删除文本时，可以使用`"register`命令将文本放入指定的寄存器中。例如一下
命令，将复制的文本放到寄存器`a`中，同时文本也会被放入未命名寄存器中。  

```vim
"ayy
```

如果在使用相应的大写字母来指定寄存器，那么将当前行内容追加到寄存器`a`中，这时
该寄存器中就有了两行文本。    

```vim
"Ayy
```

##### **4) 查看寄存器**
使用`registers name`命令，可以查看特定寄存器中的内容：   
<center>
![vim-register-a](/public/img/tech/vimreg/vim_register_a.jpg)
</center>

如果想要查看所有寄存器中的内容，可以使用如下命令：

```vim
:registers
```

<center>
![vim-registers](/public/img/tech/vimreg/vim_registers.jpg)
</center>


##### **5) 寄存器类别**
寄存器可以分为一下9类：    

<center>
<table summary="special registers" border="1" cellspacing="0" cellpadding="3">
<tbody>
<tr>
<th>类别</th><th>符号</th><th>描述</th>
</tr>
<tr>
<td>未命名寄存器</td><td>"</td><td>上一次复制或删除的文本</td>
</tr>
<tr>
<td>数字寄存器</td><td>0-9</td><td>文本删除历史</td>
</tr>
<tr>
<td>短删除寄存器</td><td>-</td><td>删除少于一行的文本</td>
</tr>
<tr>
<td>命名寄存器</td><td>a-z,A-Z</td><td>存放文本</td>
</tr>
<tr>
<td rowspan="4">只读寄存器</td>
<td>%</td><td>当前文件的名字</td>
</tr><tr>
<td>#</td><td>交替文件的名字</td>
</tr><tr>
<td>.</td><td>上一次插入的文本</td>
</tr><tr>
<td>:</td><td>上一次执行的命令</td></tr>
<tr><td>表达式寄存器</td><td>＝</td><td>返回表达式结果</td></tr>
<tr><td rowspan="3">选择和拖拽寄存器</td>
<td>\*</td><td>系统剪切板</td></tr>
<tr><td>+</td><td>系统剪切板（X11）</td></tr>
<tr><td>~</td><td>拖拽的文本</td></tr>
<tr><td>黑洞寄存器</td><td>\_</td><td>永久删除的文本</td></tr>
<tr><td>搜索模式寄存器</td><td>/</td><td>搜索模式</td></tr>
</tbody>
</table>
</center>


