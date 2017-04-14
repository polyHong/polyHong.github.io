---
layout: post
title: 简明VIM练级攻略
category: 技术
tags: [Vim,Ubuntu]
keywords: Ubuntu, Linux
description: 
---


VIM的学习曲线相当的大(参看[各种文本编辑器的学习曲线](http://coolshell.cn/articles/3125.html))，
所以，如果你一开始看到的是一大堆VIM的命令分类，你一定会对这个编辑器失去兴趣的。下面的文章翻译自
《[Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)》，

<center>
<p>
---------------------正文开始---------------------
</p>
</center>

你想以最快的速度学习人类史上最好的文本编辑器VIM吗？你先得懂得如何在VIM幸存下来，然后一点一点地学习各种戏法。

Vim the Six Billion Dollar editor

> Better, Stronger, Faster.

学习 vim 并且其会成为你最后一个使用的文本编辑器。没有比这个更好的文本编辑器了，非常地难学，但是却不可思议地好用。

我建议下面这四个步骤：    

1. 存活   
2. 感觉良好   
3. 感觉更好，更强，更快   
4. 使用VIM的超能力  

当你走完这篇文章，你会成为一个vim的 superstar。

在开始学习以前，我需要给你一些警告：    
<ul>
<li>学习vim在开始时是痛苦的。</li>
<li>需要时间</li>
<li>需要不断地练习，就像你学习一个乐器一样。</li>
<li>不要期望你能在3天内把vim练得比别的编辑器更有效率。</li>
<li>事实上，你需要2周时间的苦练，而不是3天。</li>
</ul>


#### **第一级--存活**
<ol>
<li>安装&nbsp;<a href="http://www.vim.org">vim</a></li>
<li>启动 vim</li>
<li><strong>什么也别干！</strong>请先阅读</li>
</ol>

当你安装好一个编辑器后，你一定会想在其中输入点什么东西，
然后看看这个编辑器是什么样子。但vim不是这样的，请按照下面的命令操作：

<ul>
<li>启动Vim后，vim在&nbsp;<em>Normal</em>&nbsp;模式下。</li>
<li>让我们进入&nbsp;<em>Insert</em> 模式，请按下键 i 。</li>
<li>此时，你可以输入文本了，就像你用“记事本”一样。</li>
<li>如果你想返回&nbsp;<em>Normal</em>&nbsp;模式，请按&nbsp;<code>ESC</code> 键。</li>
</ul>)

<p>现在，你知道如何在&nbsp;<em>Insert</em>&nbsp;和&nbsp;<em>Normal</em> 模式下切换了。
下面是一些命令，可以让你在&nbsp;<em>Normal</em> 模式下幸存下来：</p>

<blockquote>
<ul>
<li><code>i</code> → <em>Insert</em> 模式，按&nbsp;<code>ESC</code>&nbsp;回到 <em>Normal</em> 模式.</li>
<li><code>x</code> → 删当前光标所在的一个字符。</li>
<li><code>:wq</code> → 存盘 + 退出 (<code>:w</code> 存盘, <code>:q</code> 退出) &nbsp; （`:w` 后可以跟文件名）</li>
<li><code>dd</code> → 删除当前行，并把删除的行存到剪贴板里</li>
<li><code>p</code> → 粘贴剪贴板</li>
</ul>
<p><strong>推荐</strong>:</p>
<ul>
<li><code>hjkl</code> (强例推荐使用其移动光标，但不必需) →你也可以使用光标键 (←↓↑→). 注: <code>j</code> 就像下箭头。</li>
<li><code>:help &lt;command&gt;</code> → 显示相关命令的帮助。你也可以就输入&nbsp;<code>:help</code>&nbsp;而不跟命令。（陈皓注：退出帮助需要输入:q）</li>
</ul>
</blockquote>



