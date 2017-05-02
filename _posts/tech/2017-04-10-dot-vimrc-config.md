---
layout: post
title: Ubuntu下Vi/Vim的配置
category: 技术
tags: [Vim,Ubuntu]
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

##### **3) 安装帮助文件**
安装`latex-suite.txt`和`latexhelp.txt`文件作为帮助文件，启动vim，并且键入
如下命令：   

```vim
helptags ~/.vim/doc
```

##### **4) 修复`Alt+i`功能键**
因为在编写文档的时候需要频繁地用到列表环境, 所以`Alt+i`自动补全`item`真的是太方便了.
但是在我的ThinkPad T440s上(Xubuntu 16.04平台)这个功能却无法实现, 琢磨了很久, 终于
在网上找到了一个解决办法. 有了这个功能之后, 感觉身心舒畅极了.   

原因是不同的终端对于`Alt`组合键有不同的解释. 一些终端将`Alt`组合键解释成`8-bit`码,
而另一些终端将其解释为7位码. 实现Latex-Suite中`Alt+i`宏补全组合键, 只需要在`.vimrc`
中作如下配置即可:   

```tex
let c='a'
while c <= 'z'
    exec "set <A-".c.">=\e".c
    exec "imap \e".c." <A-".c.">"
    let c = nr2char(1+char2nr(c))
endw
set timeout ttimeoutlen=50
```

##### **5) 完成**
至此，我们就算完成了插件的安装。现在我们可以在vim中编辑Tex文件，并且Latex-Suite
应该会自动启动。我们还可以通过如下命令：   

```vim
:help latex-suite.txt
```
来获得在线的Latex-Suite帮助文档。



相关链接：     

- [dot-vimrc in GitHub](https://github.com/humiaozuzu/dot-vimrc)   
- [use-vim-as-IDE in GitHub](https://github.com/yangyangwithgnu/use_vim_as_ide)   
- [list-of-vim](http://mirnazim.org/writings/vim-plugins-i-use/)    
- [Manual,LaTex Reference,Tutorial](http://vim-latex.sourceforge.net/index.php?subject=manual&title=Tutorial#tutorial)    
- [LatTex-Suite Reference](http://vim-latex.sourceforge.net/documentation/latex-suite.html#recommended-settings)    
- [Vim latex suite “alt” macro not working](https://tex.stackexchange.com/questions/130389/vim-latex-suite-alt-macro-not-working)
