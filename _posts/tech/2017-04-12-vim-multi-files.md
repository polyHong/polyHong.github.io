---
layout: post
title: VIM打开多个文件
category: 技术
tags: [Vim,Ubuntu]
keywords: Ubuntu, Linux
description: 
---


#### **一、打开多个文件**

1. vim还没有启动的时候：   
在终端里输入`vim file1 file2 ... filen`便可以打开所有想要打开的文件   
2. vim已经启动：   
输入`:open file`可以在打开一个文件，并且此时vim里会显示出file文件的内容。
`:e ../myFile.pl`    

- `vim 文档`：普通方式打开文档   
- `vim +n 文档名`：打开文档后，定位第n行  
- `vim`，进入vim界面之后使用命令`:e 文档名`打开文档，此方式可以在编辑一个
文档的同时打开另外一个文档    

#### **二、同时显示多个文件**




