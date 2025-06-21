---
layout: post
title: 在 Mac OS 上用 VS Code 轻松打造 MATLAB 的工作环境
category: 技术
tags: vscode
keywords: MATLAB Environment
description: 
---


[Visual Studio Code](https://zhida.zhihu.com/search?content_id=145381473&content_type=Article&match_order=1&q=Visual+Studio+Code&zhida_source=entity) 是一款开源且功能强大的代码编辑器。我已经使用它半年了，深深喜欢上了这款出色的IDE。遇到这样一款得心应手的工具，作为一名理科科研工作者，再也不用为选择合适的编辑器而烦恼。

在日常工作中，我主要使用 Matlab，偶尔会用到 Python 和 C/C++。每一种编程语言都有许多优秀的IDE，基本都具备自动补全（Auto-completion）、语法高亮（syntax highlight）、语法检查（syntax checking）以及代码片段（snippets）等功能。

作为理工科背景的人，绕不开的一座大山就是 $LaTeX$。几乎所有 SCI 期刊投稿时，都需要提交符合期刊模板的 $LaTeX$ 初稿。除了撰写论文初稿，还要制作演示幻灯片（Slides）、报告（Report），甚至整理研究日记（Research diary）等。在一个项目中，我常常同时打开 Matlab、RStudio、Spyder 和 Sublime Text（主要用来写 $LaTeX$）。这就带来了一个问题：频繁在不同编辑器之间切换，效率不高。如果能有一款集成上述多种开发环境的编辑器，无需频繁切换，那工作效率必然大幅提升。而我相信，Visual Studio Code 完全可以胜任这个任务。

“工欲善其事，必先利其器。” 本文将介绍如何在 Mac OS 系统下，在 Visual Studio Code 中配置 Matlab。

## 环境介绍

- 操作系统：Mac OS Catalina
- MATLAB: 2020a
- Visual Studio Code：1.49.0
- Python：3.7.6
- [Xcode](https://zhida.zhihu.com/search?content_id=145381473&content_type=Article&match_order=1&q=Xcode&zhida_source=entity): 12.0

**注意：** MATLAB 2020a 不支持 Python3.8，想要通过 [Anaconda](https://zhida.zhihu.com/search?content_id=145381473&content_type=Article&match_order=1&q=Anaconda&zhida_source=entity) 来安装 Python 的小伙伴， 注意不要下载最新的 Anaconda 包，Anaconda 历史版本可通过 [这里](https://link.zhihu.com/?target=https%3A//repo.anaconda.com/archive/) 下载 Anaconda3-2020.02之前的版本，包含 Mac、Linux 和 Windows 版本，请自行选择。

同时需注意，Mac OS Catalina 不再自带 C/C++ 编译器，因此在安装 Matlab 之前，请务必将 Xcode 更新到最新版本，因为 MATLAB 的某些 APP 需要特殊的编译器，详情见 [这里](https://link.zhihu.com/?target=https%3A//uk.mathworks.com/support/requirements/supported-compilers.html%3Fsec%3Dmaci64%26s_cid%3Dpi_scl_2_R2020b_maci64%23mac_n1)。

## VS Code 插件

- [Matlab](https://link.zhihu.com/?target=https%3A//github.com/Gimly/vscode-matlab): 提供 MATLAB 的 VS Code 支持
- [Matlab Interactive Terminal](https://link.zhihu.com/?target=https%3A//github.com/apommel/vscode-matlab-interactive-terminal): Matlab 交互式终端
- [matlab-formatter](https://link.zhihu.com/?target=https%3A//github.com/affenwiesel/matlab-formatter-vscode): 格式化 MATLAB 代码
- [Matlab Snippets](https://link.zhihu.com/?target=https%3A//github.com/skyran1278/matlab-snippets): MATLAB 代码片段
- [Matlab Code Run](https://link.zhihu.com/?target=https%3A//github.com/bramvbilsen/Matlab-Code-Run-for-VS-Code): 运行 MATLAB m 文件
- [Matlab Extension Pack](https://link.zhihu.com/?target=https%3A//github.com/bat67/matlab-extension-pack): 以上五个插件的合集

## 安装方法

可以逐个安装插件，也可以直接安装 Matlab Extension Pack 插件。Matlab Code Run 插件可以选择安装，因为 [Matlab Interactive Terminal](https://zhida.zhihu.com/search?content_id=145381473&content_type=Article&match_order=1&q=Matlab+Interactive+Terminal&zhida_source=entity) 可以替代它。下面我们介绍安装步骤：打开 Visual Studio Code，按快捷键 ⇧ + ⌘ + X 打开扩展面板，输入 matlab 搜索，会出现如下界面：

![](https://picx.zhimg.com/v2-ec61684a803ef7e080e5bd513ce33deb_1440w.jpg)

在右边界面点击 install 即可。其他插件亦可通过此方法安装。插件安装完成后，需进一步配置环境变量才能使用。

### Matlab

1\. Visual Studio Code 默认将 .m 文件识别为 Objective-C 文件，需要修改。打开 [setting.json](https://zhida.zhihu.com/search?content_id=145381473&content_type=Article&match_order=1&q=setting.json&zhida_source=entity) 文件，或使用快捷键 ⌘ + , 直接打开 setting.json，添加如下内容：

```json
"files.associations": {"*.m": "matlab"},
```

2\. 配置 linter。什么是 Linter？根据 [Wikipedia](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/w/index.php%3Ftitle%3DLint_%28software%29%26oldid%3D907589761)的解释：

*lint, or a linter, is a tool that analyzes source code to flag programming errors, bugs, stylistic errors, and suspicious constructs. The term originates from a Unix utility that examined C language source code.*

即 linter 是用于检测 MATLAB 代码错误的工具，默认安装在 MATLAB 文件夹下，故只需告知插件该工具路径。继续编辑 setting.json，添加：

 ```json
 "matlab.mlintpath": "/Applications/MATLAB_R2020a.app/bin/maci64/mlint",
 "matlab.matlabpath": "/Applications/MATLAB_R2020a.app/bin/matlab",
 ```

3\. 中文环境下，MATLAB linter 使用的是 GB2312 编码而非 UTF-8，故操作系统为中文的用户需在 setting.json 中增加：

 ```json
 "matlab.linterEncoding" : "gb2312",
 ```

基础配置完成，更多设置可参考：[github.com/Gimly/vscode](https://link.zhihu.com/?target=https%3A//github.com/Gimly/vscode-matlab)。

截至此阶段，Visual Studio Code 已支持 MATLAB 语言（见下图），但尚无法运行 MATLAB 程序，需继续配置 Matlab Interactive Terminal。

![](https://pic2.zhimg.com/v2-c8304a189bbbe64eb41d82c0fde93511_1440w.jpg)

### Matlab Interactive Terminal

该插件需要满足以下条件：

- **Python X64 3.6/3.7**
- **MATLAB R2014b 及以上版本**
- **MATLAB Engine API for Python**

以下为配置步骤：

1. 我通过 Anaconda 安装 Python 3.7，当然也能手动安装。需注意：  
	1. 使用 Anaconda 前，务必确认 MATLAB 支持的 Python 版本，详见[此处](https://link.zhihu.com/?target=https%3A//www.mathworks.com/content/dam/mathworks/mathworks-dot-com/support/sysreq/files/python-support.pdf)。我的 MATLAB 2020a 支持 Python 3.6 和 3.7，因此需下载较旧的 Anaconda 版本，可通过 [这里](https://link.zhihu.com/?target=https%3A//repo.anaconda.com/archive/) 获取。
	2. 下载安装时，建议 macOS 用户将 Anaconda 安装在 Applications 目录下，亦可安装至自定义路径。安装后一般会自动配置环境变量，如未成功，可自行搜索解决方法。
	3. 通过 Terminal 可检测安装是否成功：
		```bash
		which python
		```
		若返回路径指向 Anaconda，说明配置正确。再执行：
		```bash
		python --version
		```
		如显示 3.7 或 3.6，则 Python 安装成功。
2. 需在 Mac App Store 安装 Xcode，因 MATLAB 依赖特定编译器，详见[这里](https://link.zhihu.com/?target=https%3A//uk.mathworks.com/support/requirements/supported-compilers.html%3Fsec%3Dmaci64%26s_cid%3Dpi_scl_2_R2020b_maci64%23mac_n1)。完成安装后，按照 MATLAB 官方教程操作。安装完成后需将 bin 目录加入 PATH 环境变量，若使用 macOS 自带 Terminal，则添加至 .bash_profile；若使用 [oh-my-zsh](https://link.zhihu.com/?target=https%3A//github.com/ohmyzsh/ohmyzsh)，则在 .zshrc 添加：
	```bash
	export MATLAB_ROOT=/Applications/MATLAB_R2020a.app
	export PATH=$MATLAB_ROOT/bin:$PATH
	```
3. MATLAB Engine API for Python 详见[此链接](https://link.zhihu.com/?target=https%3A//uk.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html)。Mac 用户确认环境变量正确后，打开 terminal，执行：
	```bash
	cd $MATLAB_ROOT/extern/engines/python
	python setup.py install
	```
	完成安装。接着在 Visual Studio Code 的 setting.json 中加入：
	```json
	"matlab-interactive-terminal.pythonPath": "/Path/to/your/anaconda3/bin/python",
	"matlab-interactive-terminal.unicodeSwitch": true,
	```
	注意需将 pythonPath 替换成实际 Anaconda Python 路径，避免出现多版本 Python 冲突。
4. 快捷键配置。Matlab Interactive Terminal 提供 3 个命令，可通过快捷键 ⇧ + ⌘ + P 调出命令面板，输入 matlab 即可看到，如下：
![](https://pica.zhimg.com/v2-9101f176e6c8912a3511d5702c1b524c_1440w.jpg)

为避免频繁操作，我为这三条命令设置了快捷键，编辑 keybindings.json，添加：

```json
{
     "key": "Cmd+Enter",
     "command": "extension.runMatlabSelection",
     "when": "editorTextFocus && editorLangId == 'matlab'"
 },
 {
     "key": "shift+Cmd+Enter",
     "command": "extension.runMatlabScript",
     "when": "editorTextFocus && editorLangId == 'matlab'"
 },
 {
     "key": "Cmd+t",
     "command": "extension.openMatlabTerminal",
     "when": "editorTextFocus && editorLangId == 'matlab'"
 },
```

分别映射为：⌘ + T 打开新终端窗口；⌘ + Enter 运行当前行或选中代码块；⇧ + ⌘ + Enter 运行整个 m 文件。用户也可自定义快捷键，详细教程见[这里](https://link.zhihu.com/?target=https%3A//code.visualstudio.com/docs/getstarted/keybindings)。

### matlab-formatter

我始终认为，无论是程序员、科研工作者还是偶尔写代码的人，都应遵守代码规范，如缩进、注释、变量命名、空格等，每种语言都有行业内的标准。良好的代码风格不仅助力快速回忆几周、几月甚至几年前的逻辑，还方便团队协作。遇到无缩进、无注释，变量命名混乱的代码，往往令我不愿多花一秒。

Matlab-formatter 让格式化 MATLAB 代码变得轻而易举。它依赖 Python 3，之前已安装，无需额外配置。如插件未工作，可在 setting.json 添加：

```json
"matlab-formatter.pythonPath": "/Path/to/your/anaconda3/bin/python",
```

选中需格式化的代码，按 ⌘ + K 再 ⌘ + F，即可格式化当前行或选中代码块，非常便捷。

### Matlab Snippets

安装 Matlab Snippets 后，请在 setting.json 中添加：

```json
"editor.snippetSuggestions": "top",
```

即可优先显示代码片段建议，提升编写效率。

### Matlab Code Run

安装该插件后可直接运行 MATLAB 脚本，详情见[github.com/bramvbilsen/](https://link.zhihu.com/?target=https%3A//github.com/bramvbilsen/Matlab-Code-Run-for-VS-Code)。

## 效果：

**Formatter**

![动图封面](https://pic3.zhimg.com/v2-8acdf3008572d9e030af0c403db0d26e_b.jpg)

**Run Code**

![动图封面](https://pic2.zhimg.com/v2-e649a902d1c73b7fb2f9dd9dbca3d849_b.jpg)

## 注意事项

安装过程依赖包和插件较多，若某插件或软件升级后运行异常，建议重新安装。核心思路如前所述，但需注意各软件和插件间的依赖关系。
