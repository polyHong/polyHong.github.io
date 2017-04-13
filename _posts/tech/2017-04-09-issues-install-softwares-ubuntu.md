---
layout: post
title: Xubuntu下TexLive和Matlab的安装
category: 技术
tags: Ubuntu
keywords: Ubuntu, Linux
description: 
---

为方便将来查阅，记录下Ubuntu里TexLive和Matlab等几个软件的安装过程。

#### **1. TexLive的在线安装**
最新的安装包已经在Ubuntu 16.10的官方仓库中。    
1) 打开终端(`Ctrl+Alt+T`)，运行如下命令添加PPA：    

```shell
$ sudo add-apt-repository ppa:jonathonf/texlive
```

2) 升级软件源并安装：    

```shell
$ sudo apt-get update
$ sudo apt-get install texlive-full
```

你可能也想安装一个文本编辑器，比如Kile, Texmaker, JLatexEditor等。

```shell
$ sudo apt-get update
$ sudo apt-get install texworks
```


#### **2. Matlab 2016a的光盘安装**





