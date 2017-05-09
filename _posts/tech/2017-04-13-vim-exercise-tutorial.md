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

<p style="text-align: center;">——————————正文开始——————————</p>

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


<h4>第一级 – 存活</h4>
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
<li><code>:wq</code> → 存盘 + 退出 (<code>:w</code> 存盘, <code>:q</code> 退出) &nbsp; （:w 后可以跟文件名）</li>
<li><code>dd</code> → 删除当前行，并把删除的行存到剪贴板里</li>
<li><code>p</code> → 粘贴剪贴板</li>
</ul>
<p><strong>推荐</strong>:</p>
<ul>
<li><code>hjkl</code> (强例推荐使用其移动光标，但不必需) →你也可以使用光标键 (←↓↑→). 注: <code>j</code> 就像下箭头。</li>
<li><code>:help &lt;command&gt;</code> → 显示相关命令的帮助。你也可以就输入&nbsp;<code>:help</code>&nbsp;而不跟命令。（退出帮助需要输入<code>:q</code>）</li>
</ul>
</blockquote>

你能在vim幸存下来只需要上述的那5个命令，你就可以编辑文本了，你一定要把这些命令练成一种下意识的状态。于是你就可以开始进阶到第二级了。

<p>当是，在你进入第二级时，需要再说一下&nbsp;<em>Normal </em>模式。在一般的编辑器下，当你需要copy一段文字的时候，你需要使用&nbsp;<code>Ctrl</code> 键，
比如：<code>Ctrl-C</code>。也就是说，Ctrl键就好像功能键一样，当你按下了功能键Ctrl后，C就不在是C了，而且就是一个命令或是一个快键键了，<strong>在VIM的Normal模式下，所有的键就是功能键了</strong>。这个你需要知道。</p>

<p>标记:</p>
<ul>
<li>下面的文字中，如果是&nbsp;<code>Ctrl-λ</code>我会写成&nbsp;<code>&lt;C-λ&gt;</code>.</li>
<li>以&nbsp;<code>:</code>&nbsp;开始的命令你需要输入&nbsp;<code>&lt;enter&gt;</code>回车，例如 — 如果我写成&nbsp;<code>:q</code>&nbsp;也就是说你要输入&nbsp;<code>:q&lt;enter&gt;</code>.</li>
</ul>


<h4 id="nd-level----feel-comfortable">第二级 – 感觉良好</h4>
上面的那些命令只能让你存活下来，现在是时候学习一些更多的命令了，下面是我的建议：
<ol>
<li><strong>各种插入模式</strong><br>
<blockquote>
<ul>
<li><code>a</code> → 在光标后插入</li>
<li><code>A</code> → 在本行行末插入</li>
<li><code>i</code> → 在光标前插入</li>
<li><code>I</code> → 在本行行首插入</li>
<li><code>o</code> → 在当前行后插入一个新行</li>
<li><code>O</code> → 在当前行前插入一个新行</li>
<li><code>cw</code> → 替换从光标所在位置后到一个单词结尾的字符</li>
</ul>
</blockquote>
</li>
<li><strong>简单的移动光标</strong><br>
<blockquote>
<ul>
<li><code>0</code> → 数字零，到行头</li>
<li><code>^</code> → 到本行第一个不是blank字符的位置（所谓blank字符就是空格，tab，换行，回车等）</li>
<li><code>$</code> → 到本行行尾</li>
<li><code>g\_</code> → 到本行最后一个不是blank字符的位置。</li>
<li><code>H</code> → 到屏幕上端</li>
<li><code>M</code> → 到屏幕中央</li>
<li><code>L</code> → 到屏幕下端</li>
<li><code>/pattern</code> → 搜索&nbsp;<code>pattern</code> 的字符串（如果搜索出多个匹配，可按n键到下一个）</li>
</ul>
</blockquote>
</li>
<li><strong>删除命令</strong> 
<blockquote>
<ul>
<li><code>x</code> → 删除光标所在处字符</li>
<li><code>nx</code> → 删除光标所在处后n个字符</li>
<li><code>dd</code> → 删除光标所在行，<code>ndd</code>删除n行</li>
<li><code>dG</code> → 删除光标所在行到末尾的内容</li>
<li><code>D</code> → 删除光标所在处到行尾</li>
<li><code>:n1,n2d</code> → 删除指定范围的行</li>
</ul>
</blockquote>
</li>
<li><strong>拷贝、剪切/粘贴</strong> （p/P都可以，p是表示在当前位置之后，P表示在当前位置之前）<br>
<blockquote>
<ul>
<li><code>yy、Y</code> → 复制当前行相当于&nbsp;<code>ddP</code></li>
<li><code>nyy、nY</code> → 复制当前行以下n行</li>
<li><code>dd</code> → 剪切当前行</li>
<li><code>ndd</code> → 剪切当前行以下n行</li>
<li><code>p、P</code> → 粘贴</li>
</ul>
</blockquote>
</li>
<li><strong>替换/取消命令</strong><br>
<blockquote>
<ul>
<li><code>r</code> → 取代光标所在处字符</li>
<li><code>R</code> → 从光标处开始替代字符，按<code>ESC</code></li>
<li><code>c [number] motion</code> → 删除指定字符并插入</li>
<li><code>u</code> → undo</li>
<li><code>&lt;C-r&gt;</code> → redo</li>
</ul>
</blockquote>
</li>
<li><strong>搜索/替换命令</strong><br>
<blockquote>
<ul>
<li><code>/string</code> → 向前搜索指定字符串，搜索时忽略大小写<code>:set ic</code></li>
<li><code>n</code> → 搜索指定字符串的下一个出现位置</li>
<li><code>:%s/old/new/g</code> → 全文替换指定字符串符</li>
<li><code>:n1,n2s/old/new/g</code> → 在一定范围内替换指定字符串</li>
</ul>
</blockquote>
</li>
<li><strong>打开/导入/保存/退出/改变文件/执行命令</strong>(Buffer)<br>
<blockquote>
<ul>
<li><code>:e &lt;path/to/file&gt;</code> → 打开一个文件</li>
<li><code>:r filename</code> → 导入文件内容到当前文件</li>
<li><code>:w</code> → 存盘</li>
<li><code>:saveas &lt;path/to/file&gt;</code> → 另存为&nbsp;<code>&lt;path/to/file&gt;</code></li>
<li><code>:x</code>，&nbsp;<code>ZZ</code> 或&nbsp;<code>:wq</code> → 保存并退出 (<code>:x</code>&nbsp;表示仅在需要时保存，ZZ不需要输入冒号并回车)</li>
<li><code>:q!</code> → 退出不保存&nbsp;<code>:qa!</code>&nbsp;强行退出所有的正在编辑的文件，就算别的文件有更改。</li>
<li><code>:bn</code>&nbsp;和&nbsp;<code>:bp</code>&nbsp;→ 你可以同时打开很多文件，使用这两个命令来切换下一个或上一个文件。（我喜欢使用:n到下一个文件）</li>
<li><code>:! &lt;command&gt;</code> → 在Vim模式下执行系统命令</li>
<blockquote>
<ul>
<li><code>:! ls</code> → 在Vim模式下执行<code>ls</code>，按<code>Enter</code>键返回Vim</li>
<li><code>:!</code>命令还可以和<code>:r</code>结合使用，如</li>
<li><code>:r !date</code> → 在Vim中导入系统当前时间</li>
</ul>
</blockquote>
</ul>
</blockquote>
</li>
<li><strong>几个实例</strong><br>
<p>连续行注释</p>
<blockquote>
<ul>
<li><code>:n1,n2s/^/#/g</code> → 在行首加#号</li>
<li><code>:n1,n2s/^#//g</code> → 在行首去掉#号</li>
<li><code>:n1,n2s/^/\/\//g</code> → 在行首加//</li>
</ul>
</blockquote>
<p>替换</p>
<blockquote>
<ul>
<li><code>:ab sammail samlee@gmail.com</code> → 将a用b替换</li>
</ul>
</blockquote>
</li>
</ol>

花点时间熟悉一下上面的命令，一旦你掌握他们了，你就几乎可以干其它编辑器都能干的事了。但是到现在为止，你还是觉得使用vim还是有点笨拙，不过没关系，你可以进阶到第三级了。


<h4 id="rd-level----better-stronger-faster">第三级&nbsp;– 更好，更强，更快</h4>

先恭喜你！你干的很不错。我们可以开始一些更为有趣的事了。在第三级，我们只谈那些和vi可以兼容的命令。

<h5 id="better">更好</h5>
下面，让我们看一下vim是怎么重复自己的：

<ol>
<li><code>.</code> → (小数点) 可以重复上一次的命令</li>
<li><code>N&lt;command&gt</code>; → 重复某个命令N次</li>
</ol>

下面是一个示例，找开一个文件你可以试试下面的命令：
<blockquote>
<ul>
<li><code>2dd</code> → 删除2行</li>
<li><code>3p</code> → 粘贴文本3次</li>
<li><code>100idesu [ESC]</code> → 会写下 “desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu “</li>
<li><code>.</code> → 重复上一个命令—— 100 “desu “.</li>
<li><code>3.</code> → 重复 3 次 “desu” (注意：不是 300，你看，VIM多聪明啊).</li>
</ul>
</blockquote>


<h5 id="stronger">更强</h5>
<p>你要让你的光标移动更有效率，你一定要了解下面的这些命令，<strong>千万别跳过</strong>。</p>
<ol>
<li><code>:set nu</code> →   设置行号</li>
<li><code>:set nonu</code> → 取消行号</li>
<li><code>NG</code> → 到第N行 （注意命令中的G是大写的，另我一般使用 : N 到第N行，如 :137 到第137行）</li>
<li><code>gg</code> → 到第一行。（相当于1G，或 :1）</li>
<li><code>G</code> → 到最后一行。</li>
<li>按单词移动：<br>
<blockquote>
<ol>
<li><code>w</code> → 到下一个单词的开头。</li>
<li><code>e</code> → 到下一个单词的结尾。</li>
</ol>
<p>&gt; 如果你认为单词是由默认方式，那么就用小写的e和w。默认上来说，一个单词由字母，数字和下划线组成（程序变量）</p>
<p>&gt; 如果你认为单词是由blank字符分隔符，那么你需要使用大写的E和W。（程序语句）</p>
<p><img src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/word_moves.jpg" alt="Word moves example"></p></blockquote>
</li>
</ol>

下面，让我来说说最强的光标移动：    
<blockquote>
<ul>
<li><code>%</code>&nbsp;: 匹配括号移动，包括&nbsp;<code>(</code>, <code>{</code>, <code>[</code>. （你需要把光标先移到括号上）</li>
<li><code>\*</code>&nbsp;和&nbsp;<code>#</code>: &nbsp;匹配光标当前所在的单词，移动光标到下一个（或上一个）匹配单词（\*是下一个，#是上一个）</li>
</ul>
</blockquote>

相信我，上面这三个命令对程序员来说是相当强大的。



<h5 id="faster">更快</h5>
你一定要记住光标的移动，因为很多命令都可以和这些移动光标的命令连动。很多命令都可以如下来干：
<p><code>&lt;start position&gt;&lt;command&gt;&lt;end position&gt;</code></p>

<p>例如&nbsp;<code>0y$</code> 命令意味着：</p>

<ul>
<li><code>0</code> → 先到行头</li>
<li><code>y</code> → 从这里开始拷贝</li>
<li><code>$</code> → 拷贝到本行最后一个字符</li>
</ul>

<p>你可可以输入&nbsp;<code>ye</code>，从当前位置拷贝到本单词的最后一个字符。</p>

<p>你也可以输入&nbsp;<code>y2/foo</code>&nbsp;来拷贝2个 “foo” 之间的字符串。</p>


还有很多时间并不一定你就一定要按y才会拷贝，下面的命令也会被拷贝：

<ul>
<li><code>d</code> (删除 )</li>
<li><code>v</code> (可视化的选择)</li>
<li><code>gU</code> (变大写)</li>
<li><code>gu</code> (变小写)</li>
<li>等等</li>
</ul>


<h4 id="th-level----vim-superpowers">第四级 – Vim 超能力</h4>
你只需要掌握前面的命令，你就可以很舒服的使用VIM了。但是，现在，我们向你介绍的是VIM杀手级的功能。
下面这些功能是我只用vim的原因。

<h5 id="move-on-current-line-0---f-f-t-t--">在当前行上移动光标: <code>0</code> <code>^</code> <code>$</code> <code>f</code> <code>F</code> <code>t</code> <code>T</code> <code>,</code> <code>;</code></h5>

<blockquote>
<ul>
<li><code>0</code> → 到行头</li>
<li><code>^</code> → 到本行的第一个非blank字符</li>
<li><code>$</code> → 到行尾</li>
<li><code>g\_</code>&nbsp;→ 到本行最后一个不是blank字符的位置。</li>
<li><code>fa</code> → 到下一个为a的字符处，你也可以fs到下一个为s的字符。</li>
<li><code>t,</code> → 到逗号前的第一个字符。逗号可以变成其它字符。</li>
<li><code>3fa</code> → 在当前行查找第三个出现的a。</li>
<li><code>F</code>&nbsp;和&nbsp;<code>T</code> → 和&nbsp;<code>f</code>&nbsp;和&nbsp;<code>t</code>&nbsp;一样，只不过是相反方向。<br>
<img src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/line_moves.jpg" alt="Line moves"></li>
</ul>
</blockquote>

<p>还有一个很有用的命令是&nbsp;<code>dt"</code> → 删除所有的内容，直到遇到双引号——&nbsp;<code>"。</code></p>

<h5 id="zone-selection-actionaobject-or-actioniobject">区域选择&nbsp;<code>&lt;action&gt;a&lt;object&gt;</code>&nbsp;或&nbsp;<code>&lt;action&gt;i&lt;object&gt;</code></h5>

<p>在visual 模式下，这些命令很强大，其命令格式为</p>

<p><code>&lt;action&gt;a&lt;object&gt;</code> 和 <code>&lt;action&gt;i&lt;object&gt;</code></p>

<ul>
<li>action可以是任何的命令，如&nbsp;<code>d</code> (删除), <code>y</code> (拷贝), <code>v</code> (可以视模式选择)。</li>
<li>object 可能是：&nbsp;<code>w</code> 一个单词，&nbsp;<code>W</code> 一个以空格为分隔的单词，&nbsp;<code>s</code> 一个句字，&nbsp;<code>p</code> 一个段落。也可以是一个特别的字符：<code>"、</code>&nbsp;<code>'、</code>&nbsp;<code>)、</code>&nbsp;<code>}、</code>&nbsp;<code>]。</code></li>
</ul>

<p>假设你有一个字符串&nbsp;<code>(map (+) ("foo"))</code>.而光标键在第一个&nbsp;<code>o&nbsp;</code>的位置。</p>

<blockquote>
<ul>
<li><code>vi"</code> → 会选择&nbsp;<code>foo</code>.</li>
<li><code>va"</code> → 会选择&nbsp;<code>"foo"</code>.</li>
<li><code>vi)</code> → 会选择&nbsp;<code>"foo"</code>.</li>
<li><code>va)</code> → 会选择<code>("foo")</code>.</li>
<li><code>v2i)</code> → 会选择&nbsp;<code>map (+) ("foo")</code></li>
<li><code>v2a)</code> → 会选择&nbsp;<code>(map (+) ("foo"))</code></li>
</ul>
</blockquote>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/textobjects.png" alt="Text objects selection"></p>

<h5 id="select-rectangular-blocks-c-v">块操作: <code>&lt;C-v&gt;</code></h5>

<p>块操作，典型的操作：&nbsp;<code>0 &lt;C-v&gt; &lt;C-d&gt; I-- [ESC]</code></p>

<ul>
<li><code>^</code> → 到行头</li>
<li><code>&lt;C-v&gt;</code> → 开始块操作</li>
<li><code>&lt;C-d&gt;</code> → 向下移动 (你也可以使用hjkl来移动光标，或是使用%，或是别的)</li>
<li><code>I-- [ESC]</code> → I是插入，插入“<code>--</code>”，按ESC键来为每一行生效。</li>
</ul>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/rectangular-blocks.gif" alt="Rectangular blocks"></p>

<p>在Windows下的vim，你需要使用&nbsp;<code>&lt;C-q&gt;</code> 而不是&nbsp;<code>&lt;C-v&gt;</code>&nbsp;，<code>&lt;C-v&gt;</code>&nbsp;是拷贝剪贴板。</p>

<h5 id="completion-c-n-and-c-p">自动提示：&nbsp;<code>&lt;C-n&gt;</code>&nbsp;和&nbsp;<code>&lt;C-p&gt;</code></h5>

<p>在 Insert 模式下，你可以输入一个词的开头，然后按&nbsp;<code>&lt;C-p&gt;或是&lt;C-n&gt;，自动补齐功能就出现了……</code></p>

<p><code></code><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/completion.gif" alt="Completion"></p>

<h5 id="macros--qa-do-something-q-a-">宏录制：&nbsp;<code>qa</code> 操作序列&nbsp;<code>q</code>, <code>@a</code>, <code>@@</code></h5>

<ul>
<li><code>qa</code>&nbsp;把你的操作记录在寄存器&nbsp;<code>a。</code></li>
<li>于是&nbsp;<code>@a</code>&nbsp;会replay被录制的宏。</li>
<li><code>@@</code>&nbsp;是一个快捷键用来replay最新录制的宏。</li>
</ul>

<blockquote><p><strong><em>示例</em></strong></p>
<p>在一个只有一行且这一行只有“1”的文本中，键入如下命令：</p>
<ul>
<li><code>qaYp&lt;C-a&gt;q</code>→
<ul>
<li><code>qa</code>&nbsp;开始录制</li>
<li><code>Yp</code> 复制行.</li>
<li><code>&lt;C-a&gt;</code> 增加1.</li>
<li><code>q</code> 停止录制.</li>
</ul>
</li>
<li><code>@a</code> → 在1下面写下 2</li>
<li><code>@@</code> → 在2 正面写下3</li>
<li>现在做&nbsp;<code>100@@</code> 会创建新的100行，并把数据增加到 103.</li>
</ul>
</blockquote>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/macros.gif" alt="Macros"></p>

<h5 id="visual-selection-vvc-v">可视化选择：&nbsp;<code>v</code>,<code>V</code>,<code>&lt;C-v&gt;</code></h5>

<p>前面，我们看到了&nbsp;<code>&lt;C-v&gt;</code>的示例 （在Windows下应该是&lt;C-q&gt;），我们可以使用&nbsp;<code>v</code> 和 <code>V</code>。一但被选好了，你可以做下面的事：</p>

<ul>
<li><code>J</code> → 把所有的行连接起来（变成一行）</li>
<li><code>&lt;</code> 或 <code>&gt;</code>&nbsp;→ 左右缩进</li>
<li><code>=</code> → 自动给缩进 （这个功能相当强大，我太喜欢了）</li>
</ul>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/autoindent.gif" alt="Autoindent"></p>

在所有被选择的行后加上点东西：

<ul>
<li><code>&lt;C-v&gt;</code></li>
<li>选中相关的行 (可使用&nbsp;<code>j</code>&nbsp;或&nbsp;<code>&lt;C-d&gt;</code>&nbsp;或是&nbsp;<code>/pattern</code>&nbsp;或是&nbsp;<code>%</code>&nbsp;等……)</li>
<li><code>$</code> 到行最后</li>
<li><code>A</code>, 输入字符串，按&nbsp;<code>ESC。</code></li>
</ul>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/append-to-many-lines.gif" alt="Append to many lines"></p>

<h5 id="splits-split-and-vsplit">分屏: <code>:split</code>&nbsp;和&nbsp;<code>vsplit</code>.</h5>

<p>下面是主要的命令，你可以使用VIM的帮助&nbsp;<code>:help split</code>. 你可以参考本站以前的一篇文章<a title="Vim的分屏功能" href="http://coolshell.cn/articles/1679.html" target="_blank">VIM分屏</a>。</p>

<blockquote>
<ul>
<li><code>:split</code> → 创建分屏 (<code>:vsplit</code>创建垂直分屏)</li>
<li><code>&lt;C-w&gt;&lt;dir&gt;</code>&nbsp;: dir就是方向，可以是&nbsp;<code>hjkl</code> 或是 ←↓↑→ 中的一个，其用来切换分屏。</li>
<li><code>&lt;C-w&gt;\_</code> (或&nbsp;<code>&lt;C-w&gt;|</code>)&nbsp;: 最大化尺寸 (&lt;C-w&gt;|&nbsp;垂直分屏)</li>
<li><code>&lt;C-w&gt;+</code> (或 <code>&lt;C-w&gt;-</code>)&nbsp;: 增加尺寸</li>
</ul>
</blockquote>

<p><img class="aligncenter" src="http://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/split.gif" alt="Split"></p>


<h4 id="conclusion">结束语</h4>


<ul>
<li>上面是作者最常用的90%的命令。</li>
<li>我建议你每天都学1到2个新的命令。</li>
<li>在两到三周后，你会感到vim的强大的。</li>
</ul>

<ul>
<li>有时候，学习VIM就像是在死背一些东西。</li>
<li>幸运的是，vim有很多很不错的工具和优秀的文档。</li>
<li>运行vimtutor直到你熟悉了那些基本命令。</li>
<li>其在线帮助文档中你应该要仔细阅读的是&nbsp;<code>:help usr_02.txt</code>.</li>
<li>你会学习到诸如&nbsp;&nbsp;<code>!，</code>&nbsp;目录，寄存器，插件等很多其它的功能。</li>
</ul>

学习vim就像学弹钢琴一样，一旦学会，受益无穷。

<p style="text-align: center;">——————————正文结束——————————</p>

<p>对于vi/vim只是点评一点：这是一个你不需要使用鼠标，不需使用小键盘，只需要
使用大键盘就可以完成很多复杂功能文本编辑的编辑器。不然，
<a title="Visual Studio的Vim插件" href="http://coolshell.cn/articles/1901.html" target="_blank">Visual Studio也不就会有vim的插件了</a>。</p>

