---
layout: post
title: Vi/Vim的配置
category: 技术
tags: Vim
keywords: Ubuntu, Linux
description: 
---

Vim是我在Linux下用的文本编辑器，它可以让人在编辑文本过程中摆脱鼠标的束缚，书写
的速度可以和思维速度匹配。原生态的Vim使用起来还是有很多不方便的地方。Vim几乎可以完成
我们日常所有的文本编辑任务，但是需要一些配置。我使用Vundle来管理Vim插件，
它可以让我们方便快捷地配置好Vim，省去学多配置过程中的许多繁琐细节。Vim的插件
可以让Vim变得无比强大。     


#### **一、Vim配置和插件安装**    

##### **1) 备份当前Vim配置文件**   

```shell
$ mv ~/.vim ~/.vim.orig
$ mv ~/.vimrc ~/.vimrc.orig  #如果没有.vimrc，这步可省
```

##### **2) 克隆和安装远程仓库**   

```shell
$ git clone git://github.com/humiaozuzu/dot-vimrc.git ~/.vim
$ ln -s ~/.vim/vimrc ~/.vimrc
```

##### **3) 安装`Vundle`**   

```shell
$ git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
```

#### **4) 安装bundles**   
启动Vim(忽略当前错误，在安装完所需插件后，它们会消失)，并且运行   

```vim
:BundleInstall
```

#### **二、如何管理vimrc**   
所有的插件都列在文件`bundles.vim`中，里面还包含非常详细的说明。也可以
往里面添加自己喜欢的其他插件。   

1. `:BundleClean`: 清除不用的插件;
2. `:BundleInstall`: 安装新增插件;
3. `:BundleInstall!`: 更新所有插件.

其他配置也十分详细地写在文件`.vimrc`之中，更详细的内容可以参看里面的内容。


#### **三、安装Vim-Latex Suite插件**
因为需要编写Tex文件，所以我还安装了Vim-Latex套件。这个插件无法用Vundle来管理，
需要独立安装。   

##### **1) 下载和解压文件**
从[SourceForge Files for vim-latex](https://sourceforge.net/projects/vim-latex/files/)
下载插件的压缩包文件。将文件解压到目录`~/.vim`中。    

##### **2) 配置`.vimrc`文件**
在`.vimrc`文件中进行如下配置：   

```vim
" REQUIRED. This makes vim invoke Latex-Suite when you open a tex file.
filetype plugin on

" IMPORTANT: win32 users will need to have 'shellslash' set so that latex
" can be called correctly.
set shellslash

" IMPORTANT: grep will sometimes skip displaying the file name if you
" search in a singe file. This will confuse Latex-Suite. Set your grep
" program to always generate a file-name.
set grepprg=grep\ -nH\ $*

" OPTIONAL: This enables automatic indentation as you type.
filetype indent on

" OPTIONAL: Starting with Vim 7, the filetype of empty .tex files defaults to
" 'plaintex' instead of 'tex', which results in vim-latex not being loaded.
" The following changes the default filetype back to 'tex':
let g:tex_flavor='latex'

```

另外，还要在`~/.vim/ftplugin/tex_latexSuite.vim`中做如下配置：   

```vim
" this is mostly a matter of taste. but LaTeX looks good with just a bit
" of indentation.
set sw=2
" TIP: if you write your \label's as \label{fig:something}, then if you
" type in \ref{fig: and press <C-n> you will automatically cycle through
" all the figure labels. Very useful!
set iskeyword+=:"}
```



