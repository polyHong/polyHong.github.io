---
layout: post
title: 用 Visual Studio Code 高效配置 LaTeX，轻松打造专业排版体验
category: 技术
tags: Visual Studio Code, LaTex
keywords: vscode, LaTex
description: LaTeX 作为一种强大的排版系统，对于理工科，特别是公式比较多的数学专业，其重要性自不必多说，不在本文探讨范围之内。而选择一个比较好的编译器是很重要的，至少对笔者而言是如此。笔者前期使用的...
---


## 前言

**LaTeX** 作为一款功能强大、极具表现力的排版系统，在理工科领域尤为受到推崇。对于数学、物理等专业，公式繁多、排版复杂，LaTeX的重要性不言而喻。本文将引导你逐步在 Visual Studio Code（VSCode）中进行配置，让你轻松掌握高效、优雅的文档创作技巧，使复杂公式的排版变得简单自如，助你在学术写作中游刃有余！

在众多 LaTeX 编译器中，挑选一款既高效又易用的工具，对于提升写作效率和排版质量至关重要。作为一名追求极致创作体验的用户，我深刻体会到，稳定且流畅的编译环境能够带来多么显著的助力。过去，我曾使用过 **TeXstudio**，虽然其功能十分全面，但编译速度较为缓慢，界面设计也略显单调。在处理复杂公式时，层层叠叠的括号缺乏代码高亮支持，使用起来令人颇感挫折。

幸运的是，我发现了一个完美的解决方案——在 Visual Studio Code 中精心配置 LaTeX 插件！VSCode不仅拥有炫目的代码高亮效果，还支持智能提示和丰富的扩展功能，使编辑变得更加高效，排版质量也得到了极大提升。接下来，就让我带你一同揭秘，如何利用 VSCode打造一个高性能、流畅且舒适的LaTeX工作环境，轻松实现专业级别的文档创作体验！

至于**Visual Studio Code**，不多赘述，先上几张图片，让我们一同感受它那强大而迷人的魅力吧！

![](https://pic3.zhimg.com/v2-47f995b53b3ffb7d9bd13243ca9e9ccc_1440w.jpg)

你会惊喜地发现，Visual Studio Code不仅支持丰富的代码高亮效果，更在不同层级的括号上巧妙地采用了多彩标识，使界面既美观又直观。令人称道的是其强大的插件生态系统——无论你的需求多么独特，总能找到合适的插件轻松扩展功能。如此一来，每个人都能将VSCode打造成专属于自己的高效编辑利器，实现真正的个性化定制！尤其是在LaTeX编辑方面，这份强大的工具将带来焕然一新的体验，让专业排版变得轻松而愉快。

经过反复探索和大量实践，笔者总结出了一套高效实用的Visual Studio Code LaTeX配置方案。在市面上，不少博主多只是简单贴出配置代码，缺乏深入讲解与实际操作指导。为帮助大家真正理解每一步配置背后的原理、灵活调整与优化环境的技巧，笔者倾心打造了这篇详尽而通俗易懂的指南。无论你是LaTeX新手，还是已有一定基础的用户，都能从中获得宝贵启发与提升，让排版工作变得轻松顺畅、专业出众！希望这篇文章成为你学习和创作道路上的坚实助力，激发无限潜力！

## 1 TeX Live 下载与安装

我心仪的 TeX 系统是功能强大、稳定可靠的 TeX Live。若你渴望迅速入门，这里为你奉上最详尽、最实用的 **TeX Live 下载与安装指南**，一步步引导你轻松搞定，让你的 LaTeX 之旅畅通无阻、事半功倍！

① 通过网址 ：

进入 ISO 下载页面后，点击图中红框标示的位置，即可跳转至随机分配的镜像网站。

![](https://pic1.zhimg.com/v2-8a250fb74061547b79689d0206b1e588_1440w.jpg)

② 可以看到，笔者已访问清华大学镜像站点，并点击红框标识的链接，进行 TeX Live 的下载安装。

![](https://pic4.zhimg.com/v2-9d56e7f966e487e22395179c8261199d_1440w.jpg)

③ 如果下载速度过于缓慢，可以返回上一页面，重新点击链接，随机选择其他镜像站点进行下载尝试，直到速度达到您的满意为止。或者，在上一页面点击“mirror list”进入镜像列表，选择合适的镜像站点进行下载。

![](https://pic2.zhimg.com/v2-1f6a48df96b0c18cbc6a0e3db67e5ed3_1440w.jpg)

然后手动选择某一镜像网站进行下载：

![](https://pic1.zhimg.com/v2-5a87555591c462962b55e6fc6fdf00ea_1440w.jpg)

④ 找到下载好的压缩包，右键，在打开方式中选择 **“Windows 资源管理器"** 打开

![](https://pic2.zhimg.com/v2-4ec3eda449f70e5c676b58a922343645_1440w.jpg)

⑤ 找到 **"install-tl-windows"** 文件，为了后面不必要的麻烦，右键 **以管理员身份运行**

![](https://pic2.zhimg.com/v2-2f29568230f2b17c4f72dde10d7f6007_1440w.jpg)

⑥ 会先出现下图，无需理会，等会儿会消失

![](https://pic3.zhimg.com/v2-4250c2abb56eff32c38834396e88ede4_1440w.jpg)

⑦ **基本更改：** 出现下图后，需要进行路径的更改；由于 TeX Live 自带的 TeXworks 不怎么好用，并且此文主要将 vscode 作为 LaTeX 的编辑器，故而取消 **安装 TeXworks 前端** 的选项，再点击安装

![](https://pic3.zhimg.com/v2-c52fd778b93f735d04d71a5df602d2a8_1440w.jpg)

⑧ **个性化安装：** 如果您需要个性化程度高的话，那么可以点击上图左下角的 **Advanced** ，根据您的需要进行相应的更改，但 **建议** 在不明白各个选项的作用时，不要对其进行修改，以免后期使用产生奇怪的问题。要注意的是， **Adjust searchpath** 这个选项一定要选中，将之添加到环境变量，否则后期手动添加比较麻烦；

而对于我们大部分人来说，只需要更改下图框选出的部分即可，也就是上图所完成的功能，再点击 **安装** 即可

![](https://pic1.zhimg.com/v2-62ab1fa73c53f8421df62828c498d036_1440w.jpg)

⑨ **进行安装：** 接着就会出现下图，具体的安装指标已在下图标明，可根据其数字来判断安装所需时间。

![](https://pic1.zhimg.com/v2-24be6bfb89fa079cb1436aa62222eaa0_1440w.jpg)

当上面标示的时间安装完之后，会出现一些配置文件的安装运行写入，进行等待即可，几分钟左右：

![](https://pic2.zhimg.com/v2-94d8416c76ff3c139063a4b8b71cba3d_1440w.jpg)

当出现下图所示弹窗时，说明安装完毕，点击关闭即可。

![](https://pic3.zhimg.com/v2-908faffd78dca6bd35a0445aea0d521e_1440w.jpg)

⑩ 检查安装是否正常： 按 **win + R** 打开运行，输入 **cmd** ，打开命令行窗口；然后输入命令 **xelatex -v** ，如下图

![](https://picx.zhimg.com/v2-c19eeb1b3a7558c834a4bea2a85b9a7d_1440w.jpg)

如上图所示，若输出了一些版本信息，则安装正常。

## 2 vscode下载

官网下载：

点进去之后就可以进行下载了。具体安装过程与常见的软件安装过程一致，这里就不作赘述。笔者只对几个 **要点** 进行提及：

① 记得 **修改安装路径**

② 根据个人想法可以选择是否在开始菜单文件夹创建 vscode 的快捷方式

![](https://pic3.zhimg.com/v2-e2039abadd095a9647fa50fdd639726e_1440w.jpg)

③ 一定要选上 **"添加到PATH”** 这个选项，能省很多麻烦。其余如图所示，自行选择。

![](https://pic4.zhimg.com/v2-024c709b63c2682dade44540642737e5_1440w.jpg)

安装好之后，打开 vscode，应如下图页面所示：

![](https://pic1.zhimg.com/v2-b7f200c44ede6c2a452d2615d09c08ee_1440w.jpg)

## 3 中文语言环境配置

vscode的中文环境需要下载插件来进行支持。如下图所示：

① 点击拓展图标，打开拓展；

② 输入 **"Chinese"** ，选择第一个Chinese (Simplified) Language Pack for Visual Studio Code插件；

③ 点击 **"install"** 进行安装，等待安装完成；

![](https://pic3.zhimg.com/v2-11ec6ecc7dacfbfdf6a0d3ab1fe0f9a4_1440w.jpg)

④ 点击页面右下角跳出窗口中的 **"Restart now"** ，进行 vscode 重启。

![](https://pica.zhimg.com/v2-57860a05da184fa4226a2104513d8f1c_1440w.jpg)

⑤ 完成中文环境配置，显示如下：

![](https://picx.zhimg.com/v2-563a1bd8d874db37e2a3130ab6c570e3_1440w.jpg)

## 4 LaTeX的支持插件 LaTeX Workshop安装

① 点击拓展图标，打开拓展；

② 输入 **"latex workshop"** ，选择第一个LaTeX Workshop插件；

③ 点击 **"install"** 进行安装，等待安装完成；

![](https://pic3.zhimg.com/v2-37df048ea711ccd6191a06763899d952_1440w.jpg)

④ 若在安装完该插件之后在 vscode 页面右下角跳出如下弹窗，无需在意，只是提醒该插件已经更新到了8.11.1版本。若您想要了解新版本增加的功能，可以点击 **"Change log"** 进行查看；若不想了解，点击 **"Disable this message"** 即可。

![](https://pic1.zhimg.com/v2-4a9aec61bb403f89fa84b9f2f0ae46fc_1440w.jpg)

## 5 打开LaTeX环境设置页面

① 点击设置图标

② 点击设置

③ 转到 UI 设置页面

![](https://pica.zhimg.com/v2-9f7cd81aeac1a5565d3f0e39c902ab02_1440w.jpg)

④ 点击下图 **1** 处打开 json 文件，进入代码设置页面

![](https://pic3.zhimg.com/v2-8a214dc687d81cf4ecb25c5e5e9ea69e_1440w.jpg)

**注 1 ：** UI 设置页面和JSON设置页面均为设置页面，其功能是一样的。不同的是，UI 设置页面交互能力较强，但一些设置需要去寻找，比较麻烦；而JSON设置页面虽然相对 UI 而言不那么直观，但却可以对自己想要的功能直接进行代码编写，且代码设置可以直接克隆别人的代码到自己的编辑器中，从而直接完成相应设置，比较便捷。

**注 2 ：** 可以直接按 **Ctrl + ，** 进入设置页面。

## 6 LaTeX环境的代码配置

## 6.1 LaTeX配置代码展示

先给出效果图：

![](https://pic2.zhimg.com/v2-175b476a0cf425370065156bf807e205_1440w.jpg)

LaTeX 配置代码如下（不包含外部 pdf 查看器设置）：

```json
{
    "latex-workshop.latex.autoBuild.run": "never",
    "latex-workshop.showContextMenu": true,
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
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
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
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
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        },
    ],
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    "latex-workshop.latex.autoClean.run": "onFailed",
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click"
}
```

**注 3 ：** 若您不想要配置外部查看器以及了解内部查看和外部查看之间切换操作，可以直接复制上述代码至 json 文件中，即可完成 LaTeX 的配置，从而可以对 LaTeX 代码进行编译。

**注 4 ：** 根据 json 文件编写规则，每个代码语句（除了代码块儿最后一句）都需要加上英文状态下的`,`，否则就会报错；而每个代码块儿的最后一句是不需要加上`,`的。从上文整个代码块儿可以看出此规则。

如果您日后需要在上述代码之后再添加其他代码，请记得在最后一句

```json
"latex-workshop.view.pdf.internal.synctex.keybinding": "double-click"
```

后添加上`,`，即变为

```json
"latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
......
```

其中的`......`为您添加的其余代码。

## 6.2 LaTeX配置代码解读

如果您对此不感兴趣，可以跳过该小节。下面进行代码 **注释解读** ：

```json
"latex-workshop.latex.autoBuild.run": "never"
```

设置何时使用默认的(第一个)编译链自动构建 LaTeX 项目，即什么时候自动进行代码的编译。有三个选项：

1\. **onFileChange** ：在检测任何依赖项中的文件更改(甚至被其他应用程序修改)时构建项目，即当检测到代码被更改时就自动编译tex文件；

2\. **onSave**: 当代码被保存时自动编译文件；

3\. **never**: 从不自动编译，即需编写者手动编译文档

此项笔者设置为 **never** 。

```json
"latex-workshop.showContextMenu": true
```

启用上下文LaTeX菜单。此菜单默认状态下停用，即变量设置为 **false** ，因为它可以通过新的 LaTeX 标记使用（新的 LaTeX 标记能够编译文档，将在下文提及）。只需将此变量设置为 **true** 即可恢复菜单。即此命令设置是否将编译文档的选项出现在鼠标右键的菜单中。

下两图展示两者区别，第一幅图为设置 **false** 情况，第二幅图为设置 **true** 情况。可以看到的是，设置为 **true** 时，菜单中多了两个选项，其中多出来的第一个选项为进行tex文件的编译，而第二个选项为进行正向同步，即从代码定位到编译出来的 pdf 文件相应位置，下文会进行提及。

![](https://pic2.zhimg.com/v2-d614a4ecc4b7da18624926b5a49f144d_1440w.jpg)

![](https://pic1.zhimg.com/v2-c66892ca1a278e961fe9fdb124896126_1440w.jpg)

笔者觉得菜单多了此选项较方便，故此项笔者设置为 **true**

```json
"latex-workshop.intellisense.package.enabled": true
```

设置为 **true** ，则该拓展能够从使用的宏包中自动提取命令和环境，从而补全正在编写的代码。

```json
"latex-workshop.message.error.show"  : false,
"latex-workshop.message.warning.show": false
```

这两个命令是设置当文档编译错误时是否弹出显示出错和警告的弹窗。因为这些错误和警告信息能够从终端中获取，且弹窗弹出比较烦人，故而笔者设置均设置为 **false** 。

```json
"latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
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
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
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
    ]
```

这些代码是定义在下文 recipes 编译链中被使用的编译命令，此处为默认配置，不需要进行更改。其中的 `name` 为这些命令的标签，用作下文 recipes 的引用；而 `command` 为在该拓展中的编译方式。

可以更改的代码为，将编译方式: pdflatex 、 xelatex 和 latexmk 中的 `%DOCFILE` 更改为 `%DOC` 。 `%DOCFILE` 表明编译器访问没有扩展名的根文件名，而 `%DOC` 表明编译器访问的是没有扩展名的根文件完整路径。这就意味着，使用 `%DOCFILE` 可以将文件所在路径设置为中文，但笔者不建议这么做，因为毕竟涉及到代码，当其余编译器引用时该 tex 文件仍需要根文件完整路径，且需要为英文路径。笔者此处设置为 `%DOCFILE` 仅是因为之前使用 TeXstudio，导致路径已经是中文了。

更多详情可以访问 github 中 LaTeX-Workshop 的 Wiki:

```json
"latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ]
```

此串代码是对编译链进行定义，其中 `name` 是标签，也就是出现在工具栏中的链名称； `tool` 是 `name` 标签所对应的编译顺序，其内部编译命令来自上文 `latex-workshop.latex.recipes` 中内容。

定义完成后，能够在 vscode 编译器中能够看到的编译顺序，具体看下图：

![](https://pic2.zhimg.com/v2-42b419223d07a18fd406ecd54f674fd1_1440w.jpg)

可以看到的是，在编译链中定义的命令出现在了vscode右侧的工具栏中。

**注 5 ：PDFLaTeX** 编译模式与 **XeLaTeX** 区别如下：

> 1\. PDFLaTeX 使用的是TeX的标准字体，所以生成PDF时，会将所有的非 TeX 标准字体进行替换，其生成的 PDF 文件默认嵌入所有字体；而使用 XeLaTeX 编译，如果说论文中有很多图片或者其他元素没有嵌入字体的话，生成的 PDF 文件也会有些字体没有嵌入。  
>   
> 2\. XeLaTeX 对应的 XeTeX 对字体的支持更好，允许用户使用操作系统字体来代替 TeX 的标准字体，而且对非拉丁字体的支持更好。  
>   
> 3\. PDFLaTeX 进行编译的速度比 XeLaTeX 速度快。

**注 6 ：** 编译链的存在是为了更方便编译，因为如果涉及到**.bib** 文件，就需要进行多次不同命令的转换编译，比较麻烦，而编译链就解决了这个问题。

```json
"latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ]
```

这串命令则是设置编译完成后要清除掉的辅助文件类型，若无特殊需求，无需进行更改。

```json
"latex-workshop.latex.autoClean.run": "onFailed"
```

这条命令是设置什么时候对上文设置的辅助文件进行清除。其变量有：

1\. **onBuilt**: 无论是否编译成功，都选择清除辅助文件；

2\. **onFailed**: 当编译失败时，清除辅助文件；

3\. **never**: 无论何时，都不清除辅助文件。

由于 tex 文档编译有时需要用到辅助文件，比如编译目录和编译参考文献时，如果使用 `onBuilt` 命令，则会导致编译不出完整结果甚至编译失败；

而有时候将 tex 文件修改后进行编译时，可能会导致 pdf 文件没有正常更新的情况，这个时候可能就是由于辅助文件没有进行及时更新的缘故，需要清除辅助文件了，而 `never` 命令做不到这一点；

故而笔者使用了 `onFailed` ，同时解决了上述两个问题。

```json
"latex-workshop.latex.recipe.default": "lastUsed"
```

该命令的作用为设置 vscode 编译 tex 文档时的默认编译链。有两个变量： 1. **first**: 使用 `latex-workshop.latex.recipes` 中的第一条编译链，故而您可以根据自己的需要更改编译链顺序； 2. **lastUsed**: 使用最近一次编译所用的编译链。

笔者选择使用 **lastUsed** 。

```json
"latex-workshop.view.pdf.internal.synctex.keybinding": "double-click"
```

用于反向同步（即从编译出的 pdf 文件指定位置跳转到 tex 文件中相应代码所在位置）的内部查看器的快捷键绑定。变量有两种：

1\. **ctrl-click** ： 为默认选项，使用Ctrl/cmd+鼠标左键单击

2\. **double-click**: 使用鼠标左键双击

此处笔者使用的为 **double-click** 。

## 7 tex文件编译

## 7.1 tex测试文件下载

为了测试 vscode 功能是否比较完整，笔者编写了一份简单的 tex 文件，以此测试其是否支持中英文，能否编译目录，能否插入图片，能否进行引用，能否编译参考文献（编译bixtex文件）等功能。

测试所用的 tex 文件可以从 github 下载：

**下载步骤** 如图：

![](https://pic1.zhimg.com/v2-f2d5103563e0bb9db364c4f946de22d2_1440w.jpg)

  

**注 7 ：** 若因网络原因无法连接到github导致无法下载，可以使用自己的tex文件进行测试，或者复制以下代码进行文档的简单编译测试，但其只能测试一部分功能：

```tex
\documentclass[a4paper]{article}
\usepackage[margin=1in]{geometry} % 设置边距，符合Word设定
\usepackage{ctex}
\usepackage{lipsum}
\title{\heiti\zihao{2} This is a test for vscode}
\author{\songti Ali-loner}
\date{2020.08.02}
\begin{document}
    \maketitle
\begin{abstract}
    \lipsum[2]
\end{abstract}
\tableofcontents
\section{This is a section}
Hello world! 你好，世界 ！
\end{document}
```

## 7.2 tex 测试文件编译

**① 打开测试文件所在文件夹**

![](https://pic1.zhimg.com/v2-cc8b54b9dd5e44f7ff79b988c5d214d4_1440w.jpg)

**② 点击选中 tex 文件** ，进行文件内容查看

![](https://pic2.zhimg.com/v2-2938ac1763f64723cc7f2812923ccf07_1440w.jpg)

**③ 开始编译文件。** 由于进行测试的文件中涉及参考文献的引用（**.bib** 的编译），故而选择 `xelatex -> bibtex -> xelatex*2` 编译链。

![](https://pic3.zhimg.com/v2-c42deeda6c6dd52e46ca85f780d77a6e_1440w.jpg)

**注 8 ：** 为了更方便进行编译，可对其设置快捷键，设置快捷键步骤如下：

![](https://pic4.zhimg.com/v2-f9c5c82990dbeac2895ec2593bbff1c5_1440w.jpg)

笔者将快捷键设置为 **Ctrl+Alt+R** 。

**选中tex文件的代码页面** （若未选中，则无法进行编译），然后按下该快捷键，在编辑器页面上端进行编译链选择，如下图：

![](https://pic3.zhimg.com/v2-c9fb99fa3eab73827ecfe822ea24f316_1440w.jpg)

**④ 编译成功**

当发现页面下方出现 **√** 符号时，说明编译成功，相反，如果出现 **×** 符号，说明编译失败，就要找失败原因了。

**a.** 左侧工具栏

当编译成功后，选中 tex 文件中任意的代码，以此来选中 tex 文件，然后进行图示操作。其中侧边栏所展现的就是上文提及的新的 LaTeX 标记。

![](https://pic1.zhimg.com/v2-7581b1033a9c201fc13c9c1ebb05d01e_1440w.jpg)

**b.** 快捷键

选中 tex 文件中任意的代码，然后按 **Ctrl+Alt+V** ，出现编译好的 pdf 页面。该快捷键为默认设置。若您想要更改，可以根据上文进行配置。

![](https://pic4.zhimg.com/v2-880a90f3a4feb0e1628d21b7765acaa3_1440w.jpg)

注意到，现在编译的结果为内部查看器查看。

**⑤ 正向同步测试** ，即从代码定位到 pdf 页面相应位置。有以下三种方法：

**a.** 使用侧边工具栏

![](https://picx.zhimg.com/v2-26481bfc0f4bccff10394e3746ad61e1_1440w.jpg)

**b.** 使用右键菜单

![](https://pic2.zhimg.com/v2-5f13291f73b7182ec16cfb5585d729f7_1440w.jpg)

**c.** 使用快捷键

选中需要跳转的代码所在行，按Ctrl+Alt+J，右侧就会跳转到相应行。这里的快捷键为默认设置，可自行通过上文方式设置为您想要的快捷键。

**⑥ 反向同步测试**,即从 pdf 页面定位到代码相应位置

在编译生成的 pdf 上，选中想要跳转行，鼠标 **左键双击** 或 **ctrl+鼠标左键单击** ，跳转到对应代码。此处快捷键的选择为上文设置，若使用笔者的代码，则为 **鼠标左键双击** 。

![](https://pic1.zhimg.com/v2-2297f86ee5e2ed18067fbbb82c6c539a_1440w.jpg)

## 8 SumatraPDF 安装设置（可选）

您可自行选择是否需要设置此部分内容。

有的时候，由于想要看到 pdf 文件的完整展现效果，使用内置查看器已无法满足需求，这时可以使用外部查看器进行查看。

外部查看器的优势是能够看到 pdf 文件在查看器中的目录，可以实时进行跳转；且根据笔者使用来看，外部查看器展示出来的 pdf 默认会放大一些，使得字体变大，要更加让人舒服一些。

笔者选择 **SumatraPDF** 作为外部查看器，该软件的优点在于在具有 pdf 阅读功能的同时很轻量，安装包不到 10MB 大小，且支持双向同步功能。通过调整其与 vscode 的窗口位置，能够在拥有这些优势的同时，达到与内置 pdf 查看具有相同的效果。

## 8.1 SumatraPDF下载与安装

官网下载：

![](https://picx.zhimg.com/v2-3173f5fb7cc1a8dcc5f2c349565e5997_1440w.jpg)

其安装很简单，与通用软件安装过程一致，记得更改安装路径并记住，下文配置需要使用其路径。

## 8.2 使用SumatraPDF查看的代码配置

### 8.2.1 代码展示

```json
{
    "latex-workshop.view.pdf.viewer": "external",
    "latex-workshop.view.pdf.ref.viewer":"auto",
    "latex-workshop.view.pdf.external.viewer.command": "F:/SumatraPDF/SumatraPDF.exe", // 注意修改路径
    "latex-workshop.view.pdf.external.viewer.args": [
        "%PDF%"
    ],
    "latex-workshop.view.pdf.external.synctex.command": "F:/SumatraPDF/SumatraPDF.exe", // 注意修改路径
    "latex-workshop.view.pdf.external.synctex.args": [
        "-forward-search",
        "%TEX%",
        "%LINE%",
        "-reuse-instance",
        "-inverse-search",
        "\"F:/Microsoft VS Code/Code.exe\" \"F:/Microsoft VS Code/resources/app/out/cli.js\" -r -g \"%f:%l\"", // 注意修改路径
        "%PDF%"
    ]
}
```

此代码仅为展示所用，让您进行查看，为下文解读之用。如需写入到 json 文件内，可直接完整复制文末笔者的个人配置到自己的编译器内。

### 8.2.2 代码解读

```json
"latex-workshop.view.pdf.viewer": "external"
```

设置默认的pdf查看器，有三种变量参数：

1\. **tab**: 使用 vscode 内置 pdf 查看器；

2\. **browser**: 使用电脑默认浏览器进行 pdf 查看；

3\. **external**: 使用外部 pdf 查看器查看。

此处选择 **external** 参数，使用外部查看器。

**注 8 ：** 此参数为下文进行pdf内部查看和外部查看进行切换的关键参数。

```json
"latex-workshop.view.pdf.ref.viewer":"auto"
```

设置PDF查看器用于在 **\\ref** 命令上的\[View on PDF\]链接，此命令作用于 **\\ref** 引用查看。有三个参数变量：

1\. **auto**: 由编辑器根据情况自动设置；

2\. **tabOrBrowser**: 使用vscode内置pdf查看器或使用电脑默认浏览器进行pdf查看；

3\. **external**: 使用外部pdf查看器查看。

此处设置为 **auto** 。

```json
"latex-workshop.view.pdf.external.viewer.command": "F:/SumatraPDF/SumatraPDF.exe"// 注意修改路径
```

使用外部查看器时要执行的命令，设置外部查看器启动文件 **SumatraPDF.exe** 文件所在位置，此处需要您根据自身情况进行路径更改，正常情况下只需更改磁盘盘符即可。

**请注意** 中间为 **" / "** 而不是 **" \\ "** ，不然会报错。

```json
"latex-workshop.view.pdf.external.viewer.args": [
        "%PDF%"
    ]
```

此代码是设置使用外部查看器时， `latex-workshop.view.pdf.external.view .command` 的参数。 `%PDF%` 是用于生成PDF文件的绝对路径的占位符。

```json
"latex-workshop.view.pdf.external.synctex.command": "F:/SumatraPDF/SumatraPDF.exe" // 注意修改路径
```

此命令是将生成的辅助文件 **.synctex.gz** 转发到外部查看器时要执行的命令,设置其位置参数，您注意更改路径，此路径为 **SumatraPDF.exe** 文件路径。与上文相同。

```json
"latex-workshop.view.pdf.external.synctex.args": [
        "-forward-search",
        "%TEX%",
        "%LINE%",
        "-reuse-instance",
        "-inverse-search",
        "\"F:/Microsoft VS Code/Code.exe\" \"F:/Microsoft VS Code/resources/app/out/cli.js\" -r -g \"%f:%l\"", // 注意修改路径
        "%PDF%"
    ]
```

当 **.synctex.gz** 文件同步到外部查看器时 `latex-workshop.view.pdf.external.synctex` 的参数设置。 `%LINE%` 是行号， `%PDF%` 是生成PDF文件的绝对路径的占位符， `%TEX%` 是当触发syncTeX被触发时，扩展名为 **.tex** 的 LaTeX 文件路径。

上面代码串中记得进行 **Microsoft VS Code** 路径修改，修改如下图:

![](https://pic4.zhimg.com/v2-a477f108729117b53b2f0fd611357f81_1440w.jpg)

此处感谢 [@可爱又迷人的反派](https://www.zhihu.com/people/Dota-Data) 对于笔者的代码提出的修改，让一部分读者存在的 SumatraPDF 无法进行正常反向同步操作的问题得到了解决。

## 9 SumatraPDF 的使用

将完整代码复制到自己的 json 文件内后，即可使用 SumatraPDF作为自己的 pdf 外部查看器了。以下为具体操作：

① 点击编辑页面任意位置来选中 tex 文件；

② 按Ctrl+Alt+V，打开编译出的 pdf 文件；

③ 出现如下图页面。可以看到的是，原本内嵌输出的 pdf 变为了在 SumatraPDF 上查看，且侧面带有书签：

![](https://pic4.zhimg.com/v2-9b6ca459e3d476f0212ea73054a42513_1440w.jpg)

④ 为了出现和内嵌输出具有相同的效果，可以将 vscode 和 SumatraPDF 进行分屏，且根据需要关闭标签，如下图：

![](https://pic3.zhimg.com/v2-a2220a77580118d76a4d8e2cc787316c_1440w.jpg)

⑤ 且同样支持双向同步（正向同步和反向同步），其操作步骤与内嵌输出 pdf 时操作步骤相同，此处就不再赘述。查看效果图：

![](https://pica.zhimg.com/v2-44c5bc95722bbc6c6440baf3a0eee47a_1440w.jpg)

## 10 pdf 内部查看与外部查看的切换

以下展示由外部查看转为内部查看的操作，由内转外操作相同。

共有两种操作方式： **UI界面设置** 或 **Json界面设置** 。具体见下图：

![](https://picx.zhimg.com/v2-f8721aaa72da52d9050f11d97b8177e3_1440w.jpg)

您可根据个人适应选择相应的方法。

## 11 Skim 安装设置（可选）

### 11.1 下载并安装Skim

下载链接： [https://sourceforge.net/projects/skim-app/](https://sourceforge.net/projects/skim-app/)

### 11.2 配置Skim

```bash
touch displayfile.txt
open displayfile.txt
```

在文本中写入：

```bash
#!/bin/bash

# displayfile (Skim)
#
# Usage: displayfile [-r] [-g] PDFFILE
#
# Modified from "displayline" to only revert the file, not jump to a given line
#

if [ $# == 0 -o "$1" == "-h" -o "$1" == "-help" ]; then
  echo "Usage: displayfile [-r] [-g] PDFFILE
Options:
-r, -revert      Revert the file from disk if it was open
-g, -background  Do not bring Skim to the foreground"
  exit 0
fi

# get arguments
revert=false
activate=true
while [ "${1:0:1}" == "-" ]; do
  if [ "$1" == "-r" -o "$1" == "-revert" ]; then
    revert=true
  elif [ "$1" == "-g" -o "$1" == "-background" ]; then
    activate=false
  fi
  shift
done
file="$1"
#shopt -s extglob
#[ $# -gt 2 ] && source="$3" || source="${file%.@(pdf|dvi|xdv)}.tex"

# expand relative paths
[ "${file:0:1}" == "/" ] || file="${PWD}/${file}"

# pass file arguments as NULL-separated string to osascript
# pass through cat to get them as raw bytes to preserve non-ASCII characters
/usr/bin/osascript \
  -e "set theFile to POSIX file \"$file\"" \
  -e "set thePath to POSIX path of (theFile as alias)" \
  -e "tell application \"Skim\"" \
  -e "  if $activate then activate" \
  -e "  if $revert then" \
  -e "    try" \
  -e "      set theDocs to get documents whose path is thePath" \
  -e "      if (count of theDocs) > 0 then revert theDocs" \
  -e "    end try" \
  -e "  end if" \
  -e "  open theFile" \
  -e "end tell"
```

然后保存，继续在命令行输入：

```bash
chmod u+x displayfile.txt
mv displayfile.txt displayfile
mv displayfile /usr/local/bin/
```

### 11.3 配置VScode setting

添加配置：

```json
"latex-workshop.view.pdf.viewer": "external",
"latex-workshop.view.pdf.external.synctex.command": "/Applications/Skim.app/Contents/SharedSupport/displayline",
"latex-workshop.view.pdf.external.synctex.args": [
    "-r",
    "%LINE%",
    "%PDF%",
    "%TEX%"
],

"latex-workshop.view.pdf.external.viewer.command": "displayfile",
"latex-workshop.view.pdf.external.viewer.args": [
    "-r",    // "0",
    "%PDF%"
],
```

## 11.4 配置Skim

点击skim，是不会有界面的：

1. 在顶部导航栏Skim -> Preferences
2. 点开第4个标签Sync，配置如下：  
	![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/71be9fda9fdb9543a3d9483553fcaf80.png#pic_center)

## 跳转

写完 latex 文档并且编译完成后从插件这里打开pdf文件：  
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/cf59a85f17bae72146aba71c88fd44ad.png#pic_center)  

然后从PDF -> TeX文件：cmd+shift+鼠标左击

## 12 个人完整配置

```json
{
 //------------------------------LaTeX 配置----------------------------------
    // 设置是否自动编译
    "latex-workshop.latex.autoBuild.run":"never",
    //右键菜单
    "latex-workshop.showContextMenu":true,
    //从使用的包中自动补全命令和环境
    "latex-workshop.intellisense.package.enabled": true,
    //编译出错时设置是否弹出气泡设置
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    // 编译工具和命令
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
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
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
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
    // 用于配置编译链
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    //文件清理。此属性必须是字符串数组
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    //设置为onFaild 在构建失败后清除辅助文件
    "latex-workshop.latex.autoClean.run": "onFailed",
    // 使用上次的recipe编译组合
    "latex-workshop.latex.recipe.default": "lastUsed",
    // 用于反向同步的内部查看器的键绑定。ctrl/cmd +点击(默认)或双击
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",

    //使用 SumatraPDF 预览编译好的PDF文件
    // 设置VScode内部查看生成的pdf文件
    "latex-workshop.view.pdf.viewer": "external",
    // PDF查看器用于在\ref上的[View on PDF]链接
    "latex-workshop.view.pdf.ref.viewer":"auto",
    // 使用外部查看器时要执行的命令。此功能不受官方支持。
    "latex-workshop.view.pdf.external.viewer.command": "F:/SumatraPDF/SumatraPDF.exe", // 注意修改路径
    // 使用外部查看器时，latex-workshop.view.pdf.external.view .command的参数。此功能不受官方支持。%PDF%是用于生成PDF文件的绝对路径的占位符。
    "latex-workshop.view.pdf.external.viewer.args": [
        "%PDF%"
    ],
    // 将synctex转发到外部查看器时要执行的命令。此功能不受官方支持。
    "latex-workshop.view.pdf.external.synctex.command": "F:/SumatraPDF/SumatraPDF.exe", // 注意修改路径
    // latex-workshop.view.pdf.external.synctex的参数。当同步到外部查看器时。%LINE%是行号，%PDF%是生成PDF文件的绝对路径的占位符，%TEX%是触发syncTeX的扩展名为.tex的LaTeX文件路径。
    "latex-workshop.view.pdf.external.synctex.args": [
        "-forward-search",
        "%TEX%",
        "%LINE%",
        "-reuse-instance",
        "-inverse-search",
        "\"F:/Microsoft VS Code/Code.exe\" \"F:/Microsoft VS Code/resources/app/out/cli.js\" -r -g \"%f:%l\"", // 注意修改路径
        "%PDF%"
    ]
}
```
