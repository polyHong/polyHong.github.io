---
layout: post
title: 关于 VSCode 中工作区的讲解与使用工作区
category: 技术
tags: vscode workspace
keywords: workspace
description: VSCode的使用率在逐渐提高，但安装太多的插件会使得VSCode变得臃肿，甚至运行变慢，占用太多内存，此文章介绍了工作区，并如何来使用工作区更好地体验VSCode。 初次使用VSCode，肯定有很多人好奇，这里面的工作区有什么用，与文件夹的区别在哪。
---


初次使用VSCode，肯定有很多人好奇，这里面的工作区有什么用，与文件夹的区别在哪。其实VSCode中的工作区是为了让你配置一个工作环境,让你更好地针对不同地环境（如JAVA环境，C++环境）设定不同地配置体验更好的VSCode。

这里举个栗子：

我们在JAVA环境，无需使用Python的插件，但是Python的插件默认开启，占有很多系统不必要的内存，我们就可以在不同的工作区进行不同的配置。这里仅是用Java和Python举个栗子，可能有人会说不会用VSCode写个Java，作者本人也不经常用VSCode写Java项目，用它写前端更多些。

## VSCode层次关系

层次关系如下

![](https://picx.zhimg.com/v2-91da9ea2ecd7f2e5ddd42dba07f4281b_1440w.jpg)

层次很清晰，即

系统默认设置（不可修改）- [用户设置](https://zhida.zhihu.com/search?content_id=100299601&content_type=Article&match_order=1&q=%E7%94%A8%E6%88%B7%E8%AE%BE%E7%BD%AE&zhida_source=entity) -工作区设置- [文件夹设置](https://zhida.zhihu.com/search?content_id=100299601&content_type=Article&match_order=1&q=%E6%96%87%E4%BB%B6%E5%A4%B9%E8%AE%BE%E7%BD%AE&zhida_source=entity)

后者的设置会覆盖前者的设置，若没有设置某一项，将继续使用前者的设置。

  
我们可以这样理解此层次：

- 用户设置即全局设置，用户自行设定好后，每次打开VSCode即使用的此设定，若某项无设定即使用默认设置。   
- 工作区设置即工作环境设置，可对不同的工作环境是用不同的工作环境，若某项无设定，即使用上一层设置。   
- 文件夹设置即为项目设置，将一个文件夹当成一个项目，对同一个工作环境下的不同项目，使用不同的设置，若某项无设定，即使用上一层设置。

即 全局-工作环境-项目。仅是一种理解方式，如有更好的理解，可以评论。

注：工作区可以不打开，即无“工作区设置”，“用户设置”下面直接到“文件夹设置”。层次为 用户设置-文件夹设置

## 如何新建一个工作区

大家应该都发现了，文件中没有“新建工作区”的选项。

打开文件会看到“将工作区另存为…”选项，这就代替了“新建工作区”，在不打开任何工作区、文件夹及文件的清空下，这个选项都可以使用。

![](https://pic2.zhimg.com/v2-cbfde91bb1c9fd3aa1d5a88f5ed2ddf3_1440w.jpg)

如果在打开的文件夹的情况下保存工作区，会自动将此文件夹放入工作区，也建议这样使用。

工作区文件建议直接放置在你的工作文件夹（如Java文件夹）下，若打开文件夹的情况下，建议不要更改路径，直接放置此文件夹下。

打开某一文件夹后，若文件夹中含有工作区文件，会自动弹出以下提示

![](https://picx.zhimg.com/v2-facfecbeb1e9dd391acc2d87c2e3d12d_1440w.jpg)

也可以将所有的工作区文件放置在同一个文件夹下，方便管理。

## 工作区的文件夹配置详解

你可以添加任意的文件夹至此工作区，来使用当前工作区的设置。

工作区中的文件夹配置如下，为json格式。

```json
{  
> "folders": \[  
> {  
> "path": "."  
> },  
> {  
> "path": "D:\\\\Workspaces\\\\VSCode\\\\Python"  
> }  
> \],  
> "settings": {  
> "python.pythonPath": "C:\\\\Program Files\\\\Python37\\\\python.exe"  
> }  
> }
```

"path": "." 为当前工作区文件所在的文件夹。

"path": "D:\\\\Workspaces\\\\VSCode\\\\Python" 为你自行添加的文件夹路径。

"python.pythonPath": "C:\\\\Program Files\\\\Python37\\\\python.exe"此为python路径

通过此方式我们亦可以为不同的工作区设置不同python版本，如python2，python3。

## 如何在不同的工作区启用/禁用不同的插件

这里就是工作区的关键部分。找到当前插件，若是Java或Python等插件集合建议打开其扩展包。有两个选项  

- 第一个选项“禁用”为你的用户设置
- 第二个选项“禁用（工作区）”为工作区设置

选择“禁用（工作区）”。

![](https://pic1.zhimg.com/v2-d42414dbeef61d577c0d6fd176bf04ec_1440w.jpg)

这里我是在Python的工作区下禁用Java扩展包。禁用后会发现此扩展包下的所有Java插件集合都被禁用。

![](https://pic2.zhimg.com/v2-3348baa06e1cc54df8400bf627285249_1440w.jpg)

此设置会只应用到当前工作区下，不会影响用户设置和其他工作区的设置，文件夹无此设置。VSCode关闭后会继续打开上次打开的工作区，如想关闭，请使用文件-关闭工作区。

**建议：** 在用户设置（即非打开工作区的情况下）关闭大多数插件，留下常用的，在不同的工作区下再开启，比如我是默认关闭了Java插件，在Java工作区下开启了它。

**总结：** 通过这种方式，将使得安装太多插件下VSCode也不会显得很臃肿，占用内存也会相应地减小，还给我们一个轻量的VSCode。
