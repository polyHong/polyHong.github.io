---
layout: post
title: 如何优雅地书写 LaTeX 论文
category: 技术
tags: LaTeX, VSCode
keywords: LaTeX, VSCode
description: how tow write LaTex paper elegantly.
---

## TeX Live+VS Code+Sumatra PDF书写你的LaTeX论文

LaTeX是一款功能强大的文本排版软件，尤其在科研论文写作中应用广泛。数模美赛也强烈推荐使用LaTeX进行编辑，有些出版社甚至只接受用LaTeX撰写的论文。起初我使用的是CTEX套装，后来换成了TeX Live。然而，LaTeX自带的各种编辑器界面实在太丑，作为一个“颜控”，无法更改背景颜色，也没有各种便捷的提示功能，实在难以接受。后来我在网上发现，VSCode竟然也可以作为LaTeX的编辑器，于是我很心动。经过一番折腾（包括但不限于外部阅读器失效、找不到开关、每次打开文件都要修改工作区设置等问题），我终于搭建出了一个基本可用的LaTeX编辑环境。接下来，我将把这个过程分享给大家。

## Step 1：安装 TeX Live\\TeX\\ \\text{Live}

**书写 LaTeX，我们当然需要一个编译环境，这里推荐 TeX Live。这也是 lshort 里面推荐的TeX排版引擎。**

> 选择那种TeX开发版？
>
> - 为什么不推荐CTEX套装呢？原因是CTEX已经过时了，他使用的是MikiTeX，但CTEX已经已经断更很久了，没能兼容一些新的特性。
> - 至于TeX Live的下载当然是版本越新越好咯，这里我们以TeX Live 2020为例来演示其安装过程。

至于TeX Live的下载我们可以在 **CTAN** 上下载，为了获取更快的下载速度，我们可以选择在 [清华的开源镜像](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/) 上下载。我们这里下载iso镜像文件。清华的镜像还是很快的，我在家差不多能跑到5 M/s的样子。

![清华镜像](https://levitate-qian.github.io/2020/07/21/latex-vscode/%E6%B8%85%E5%8D%8E%E9%95%9C%E5%83%8F.png)

下面开始正式安装TeX Live。

1. 双击加载iso光盘文件，进入虚拟光盘。
2. 右击 `install-tl-windows` ，并以管理员身份运行安装程序
 ![texlive安装1](https://levitate-qian.github.io/2020/07/21/latex-vscode/texlive%E5%AE%89%E8%A3%851.png)
3. 进入TeX Live安装界面，我们可以选择安装的位置，我选择在D盘。该软件体积比较大，大约要6个GB左右。
 ![texlive安装2-1](https://levitate-qian.github.io/2020/07/21/latex-vscode/texlive%E5%AE%89%E8%A3%852-1.png)
 *（可选）* 我们可以点击下方的 `Advanced` 按钮，进入高级设置，选择我们需要的应用。我们可以 `Customize` 选项下来取消勾选不需要的宏包。 **在电脑空间充足的前提下，推荐安装所有的宏包。**
 ![texlive安装2-2](https://levitate-qian.github.io/2020/07/21/latex-vscode/texlive%E5%AE%89%E8%A3%852-2.png)
4. 多等一会，静候佳音。这个安装过程是很漫长的，大致需要一小时左右。

## Step 2：安装Sumatra PDF

在等待的过程中，我们不妨下载Sumatra PDF，这是一个很轻量的的PDF阅读器，但是它支持通过命令行代码 **实现反向搜索** 。

我们可以在 [官网](https://www.sumatrapdfreader.org/prerelease.html) 下载这个软件，不推荐在微软商店下载。（这个下载可能需要科学上网）这个软件更新版本很多，这里提供一个在2020年7月21日最新的版本（v3.3.13082版本）的 [下载地址](https://levitate.lanzous.com/iGnjQetdvvi) ，大家可以有选择性地选择是否更新。安装时记得记住 **安装路径** 哦！

> 突然发现我一直用的是预览版，难怪更新这么勤快，这里再给一个普通版的 [网址](https://www.sumatrapdfreader.org/download-free-pdf-viewer.html) 。

Sumatra软件的界面大致如下。

![sumatra界面](https://levitate-qian.github.io/2020/07/21/latex-vscode/sumatra%E7%95%8C%E9%9D%A2.png)

下面我们来配置反向搜索的命令行。

1. 看到左上方三横的菜单栏了吗，依次选择里面的 `设置` -> `选项` 。也许我们能够看到下面的页面，当然设置反向搜索命令行的内容肯定是空的，但是如果出现了 **设置反向搜索命令行** ，那恭喜你，很方便的就能设置反向搜索。
 ![sumatra选项1](https://levitate-qian.github.io/2020/07/21/latex-vscode/sumatra%E9%80%89%E9%A1%B91.png)
 你只需要在文本框中输入以下内容

 ```bash
 "C:\Users\qcl\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\qcl\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" -r -g "%f:%l"
 ```

 当然这两句代码要根据你VSCode的安装路径决定，如果你没有动过的话大致就是这样的路径。
2. 如果你的软件没有出现 **设置反向搜索命令行** ，甚至没有出现 `选项` ，甚至没有出现 `高级选项` ，更甚至没有出现 `设置` 。别担心，不是软件出了问题，我们可以通过修改文本内容来解决。

- 我们在Sumatra PDF的安装路径下，应该能够找到名为”SumatraPDF-settings“的文本文档。（如果能找到高级选项，在高级选项中打开也就是这个文本文档。）
  ![sumatra选项2-1](https://levitate-qian.github.io/2020/07/21/latex-vscode/sumatra%E9%80%89%E9%A1%B92-1.png)
- 进入这个文档，在里面加入以下文字：

  ```bash
  InverseSearchCmdLine = "C:\Users\qcl\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\qcl\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" -r -g "%f:%l"
  EnableTeXEnhancements = true
  ```

这样反向搜索就配置完了。

## Step 3：VSCode的加持

前面的都是小case啦，真正的重头戏来了，那就是 **VSCode** 。

VSCode是一款优质的轻量的编辑器，它的界面美观，插件丰富，可以应用于编写各种代码。我还配置过C语言环境、Python环境等等。我比较建议的是将每种语言放在一个工作区内，互不干扰，也能在不同时候编译不同的语言。

### 3.1 安装LaTeX Workshop插件

我们在VSCode的扩展商店中安装 **LaTeX Workshop插件** ，这差不多算是一个All-in-one插件了，它的功能非常丰富。

![VSC-2](https://levitate-qian.github.io/2020/07/21/latex-vscode/VSC-2.png)

安装完成后，随便打开一个 tex 源文件，代码已经可以高亮了。

### 3.2 创建LaTeX工作区

首先，我们先创建一个空文件夹。名称可以自己命名， **要求最好不含中文、空格** ，分词可以使用下划线 `_` 来分词。（这点很重要，也是一个比较好的习惯吧）

在VSCode中打开创建的文件夹，接着选择 `文件` -> `将工作区另存为` 。

![VSC](https://levitate-qian.github.io/2020/07/21/latex-vscode/VSC.png)

我们把工作区保存在该文件夹目录下即可。

### 3.3 配置工作区

创建完工作区，我们就需要配置工作区，记住既然我们创建了工作区，那么所有的操作都在工作区内进行就可以了，切记不要去别的地方操作，那是没用的。

我们将下述代码直接贴入`.code-workspace` 文件中，下面我们再来谈谈这些代码的具体作用。（ **记得修改路径哦！** ）

![VSC-3](https://levitate-qian.github.io/2020/07/21/latex-vscode/VSC-3.png)

```json
{
    "folders": [
        {
            "path": "."
        }
    ],
    "settings": {
        "latex-workshop.latex.tools": [
            {
                "name": "xelatex",
                "command": "xelatex",
                "args": [
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "-pdf",
                    "%DOCFILE%"
                ]
            },
            {
                "name": "pdflatex",
                "command": "pdflatex",
                "args": [
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "%DOCFILE%"
                ]
            },
            {
                "name": "makeindex",
                "command": "makeindex",
                "args": [
                    "%DOCFILE%.nlo",
                    "-s",
                    "nomencl.ist",
                    "-o",
                    "%DOCFILE%.nls"
                ]
            },
            {
                "name": "biber",
                "command": "biber",
                "args": [
                    "%DOCFILE%"
                ]
            },
            {
                "name": "bibtex",
                "command": "bibtex",
                "args": [
                  "%DOCFILE%"
                ]
            }
        ],
        "latex-workshop.latex.recipes": [
            {
                "name": "xelatex🔃",
                "tools": [
                    "xelatex"
                ]
            },
            {
                "name": "xe->mkind->bib->xe*2🔃",
                "tools": [
                    "xelatex",
                    "makeindex",
                    "biber",
                    "xelatex",
                    "xelatex"
                ]
            },
            {
                "name": "pdf->mkind->bib->pdf*2🔃",
                "tools": [
                    "pdflatex",
                    "makeindex",
                    "biber",
                    "pdflatex",
                    "pdflatex"
                ]
            },
            {
                "name": "xe->bib->xe->xe🔃",
                "tools": [
                    "xelatex",
                    "bibtex",
                    "xelatex",
                    "xelatex"
                ]
            },
            {
                "name": "biber🔃",
                "tools": [
                    "biber"
                ]
            },
            {
                "name": "pdflatex🔃",
                "tools": [
                    "pdflatex"
                ]
            },
            {
                "name": "pdf->bib->pdf->pdf🔃",
                "tools": [
                    "pdflatex",
                    "bibtex",
                    "pdflatex",
                    "pdflatex"
                ]
            },
            {
                "name": "BibTeX🔃",
                "tools": [
                    "bibtex"
                ]
            }
        ],
        "latex-workshop.view.pdf.viewer": "external",
        "latex-workshop.view.pdf.ref.viewer":"external", 
        "latex-workshop.showContextMenu":true,
        "latex-workshop.view.pdf.external.command":{
            "command": "C:/Users/qcl/AppData/Local/SumatraPDF/SumatraPDF.exe",
            "args": [
                "%PDF%"
            ]
        },
        "latex-workshop.view.pdf.external.viewer.command": "C:/Users/qcl/AppData/Local/SumatraPDF/SumatraPDF.exe", 
        "latex-workshop.view.pdf.external.viewer.args": [
            "%PDF%"
        ],
        "latex-workshop.view.pdf.external.synctex.command": "C:/Users/qcl/AppData/Local/SumatraPDF/SumatraPDF.exe", // 注意修改路径
        "latex-workshop.view.pdf.external.synctex.args": [
            "-forward-search",
            "%TEX%",
            "%LINE%",
            "%PDF%"
        ],
        "latex-workshop.latex.recipe.default": "lastUsed",
        "editor.wordWrap": "on",
        "latex-workshop.synctex.synctexjs.enabled": false,
        "latex-workshop.synctex.afterBuild.enabled": true,
        "latex-snippets.autoSuggestionOn": true,
    }
}
```

上述部分的代码呢，其实也来源于网络，但是用谁的都会出错，所以就被我改了一部分，下面讲讲具体的。

1. `latex-workshop.latex.tools` 这里面主要配置的就是各种编译方式，我们最常用到的就两种 `xelatex` 和 `bibtex` （注意不是 `biber` ），有时候也会用到 `pdflatex` 。一开始，我一直都无法编译`.bib` 的参考文献，原因就出在编译链使用的是 `biber` ，而非 `bibtex` ，所以我就改了。
2. `latex-workshop.latex.recipes` 这里面就是所谓的编译链了。我们知道LaTeX生成PDF的原理就是使用编译器进行编译。一般的文件我们只需要使用一次或两次 `xelatex` 即可编译成功；而当我们有含`.bib` 的参考文献时，一般的编译链就变成，编译一次 `xelatex` ，一次 `bibtex` ，两次 `xelatex` ，也就是上述编译链中的 `"xe->bib->xe->xe🔃"` 。其他还给了一些编译链，大家可以按需取舍。值得注意的是，默认的编译链时最上面一条，所以我一般放的是单次执行 `xelatex` 编译。
3. 下面主要的代码处理的就是利用外部PDF阅读器Sumatra所需要的代码了。 **需要注意修改部分的路径** 。  
 ❗值得注意的是：这个代码 **可能会报错** ，显示未使用最新的语法，但是使用最新语法后，每次重开一个文件都需要修改该工作区配置文件，不知道bug在哪里，所以我就保留了一条老的语法。具体的错误说明如下：
 ![错误](https://levitate-qian.github.io/2020/07/21/latex-vscode/%E9%94%99%E8%AF%AF.png)
4. 还有一些别的我也不记得是什么了，就不解释了。(¬‿¬)略略略
5. 还有一些其他设置，来自 [参考文献1](https://zhuanlan.zhihu.com/p/38178015)

- LaTeX Workshop 默认保存的时候自动编译，如果不喜欢这个设置，可以添加以下代码进入设置区：

 ```bash
 "latex-workshop.latex.autoBuild.run": "never",
 ```

- 如果编译出错，插件会弹出两个很烦人的气泡，不喜欢的话可以在设置中添加以下代码：

 ```bash
 "latex-workshop.message.error.show": false,
 "latex-workshop.message.warning.show": false,
 ```

## Step 4：使用上述工具来书写你的文章吧

首先，介绍一下LaTeX Workshop提供的常用工具吧！

![VSC-4](https://levitate-qian.github.io/2020/07/21/latex-vscode/VSC-4.png)

我常用的也就上面这几个

- 编译常用的两个编译链，我们可以直接单击 `Bulid LaTeX Project` 也是生成LaTeX文件啊！生成后会自动打开Sumatra PDF，我一般就让VSCode和Sumatra分布在屏幕的左右，方便工作。当然，我一般是ctrl+S保存就编译的，这个就看个人习惯了。
- 正向搜索使用synctex命令。我们选中LaTeX代码中的位置，再选择 `SyncTeX from cursor` 即可实现文章的正向搜索
- 在Sumatra PDF中双击文字，即可定位到tex代码中的相应段落。

下图就是我一般的写LaTeX文章的桌面环境。

![样例](https://levitate-qian.github.io/2020/07/21/latex-vscode/%E6%A0%B7%E4%BE%8B.png)
