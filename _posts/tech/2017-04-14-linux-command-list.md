---
layout: post
title: Linux常用命令一之文件处理命令
category: 技术
tags: Linux 
keywords: Ubuntu, Linux
description: 
---


本文对Linux常用命令做一个总结，方便日后查阅。

<h4><strong>(1) ls命令</strong></h4>
<p>
ls命令是linux下最常用的命令。ls命令就是list的缩写，缺省下ls用来打印出当前目录的清单，
如果ls指定其他目录，那么就会显示指定目录里的文件及文件夹清单。通过ls命令不
仅可以查看linux文件夹包含的文件，而且可以查看文件权限(包括目录、文件夹、文件权限)
查看目录信息等等。ls命令在日常的linux操作中用的很多！
</p>

<ol>
<li><strong>命令格式：</strong></li>
ls&nbsp;[选项]&nbsp;[目录名]
<li><strong>命令功能：</strong></li>
列出目标目录中所有的子目录和文件
<li><strong>常用参数：</strong></li>
<ul>
<li>-a, -all 列出目录下的所有文件，包括以.开头的隐含文件</li>
<li>-A&nbsp;同-a，但不列出“.”(表示当前目录)和“..”(表示当前目录的父目录)</li>
<li>-l&nbsp;除了文件名之外，还将文件的权限、所有者、文件大小等信息详细列出来</li>
<li>-t&nbsp;以文件修改时间排序</li>
<li>-x&nbsp;逐行列出项目而不是逐栏列出</li>
<li>-1&nbsp;每行只列出一个文件</li>
</ul>
<li><strong>常用范例：</strong></li>
<strong>例1：</strong>列出/home/peidachang文件夹下的所有文件和目录的详细资料
<p><strong>命令：</strong><code>ls -l -R /home/peidachang</code></p>
<p><strong>命令：</strong><code>ls -lR /home/peidachang</code></p>
<strong>例2：</strong>列出当前目录中所有以“t”开头的目录的详细内容
<p><strong>命令：</strong><code>ls -l t\*</code></p>
<strong>例3：</strong>只列出文件下的子目录
<p><strong>命令：</strong><code>ls -F /opt/soft |grep /$ </code>列出/opt/soft文件下面的子目录</p>
<p><strong>命令：</strong><code>ls -l /opt/soft | grep "^d"</code>列出/opt/soft文件下面的子目录详细情况</p>
<strong>例4：</strong>列出目前工作目录下所有名称是s开头的档案，愈新的排愈后面
<p><strong>命令：</strong><code>ls -ltr s\*</code></p>
<strong>例5：</strong>列出目前工作目录下所有档案及目录;目录于名称后加"/", 可执行档于名称后加"\*"
<p><strong>命令：</strong><code>ls -AF</code></p>
<strong>例6：</strong>计算当前目录下的文件数和目录数
<p><strong>命令：</strong></p>
<p><code>ls -l * |grep "^-"|wc -l</code>文件个数</p>
<p><code>ls -l * |grep "^d"|wc -l </code>目录个数</p>
</ol>


<h4><strong>(2) cd命令</strong></h4>
<p>
Linux cd命令可以说是Linux中最基本的命令语句，其他的命令语句要进行操作，
都是建立在使用cd命令上的。所以，学习Linux常用命令，首先就要学好cd命令的使用方法技巧。
</p>

<ol>
<li><strong>命令格式：</strong></li>
cd&nbsp;[目录名]
<li><strong>命令功能：</strong></li>
切换当前目录至dirName
<li><strong>常用参数：</strong></li>
<ul>
<li>-a, -all 列出目录下的所有文件，包括以.开头的隐含文件</li>
<li>-A&nbsp;同-a，但不列出“.”(表示当前目录)和“..”(表示当前目录的父目录)</li>
<li>-l&nbsp;除了文件名之外，还将文件的权限、所有者、文件大小等信息详细列出来</li>
<li>-t&nbsp;以文件修改时间排序</li>
<li>-x&nbsp;逐行列出项目而不是逐栏列出</li>
<li>-1&nbsp;每行只列出一个文件</li>
</ul>
<li><strong>常用范例：</strong></li>
<p><strong>例1：</strong>进入系统根目录
<strong>命令：</strong><code>cd /</code></p>
<p><strong>例2：</strong>进入上一级目录
<strong>命令：</strong><code>cd ..</code></p>
<p><strong>例3：</strong>进入用户主目录
<strong>命令：</strong><code>cd</code></p>
<p><strong>例4：</strong>返回进入此目录之前所在的目录
<strong>命令：</strong><code>cd -</code></p>
<p><strong>例5：</strong>把上个命令的参数作为cd参数使用
<strong>命令：</strong><code>cd !$</code></p>
</ol>

<h4><strong>(3) pwd命令</strong></h4>
<p>
Linux中用pwd命令来查看”当前工作目录“的完整路径。
简单得说，每当你在终端进行操作时，你都会有一个当前工作目录。
在不太确定当前位置时，就会使用pwd来判定当前目录在文件系统内的确切位置。
</p>

<ol>
<li><strong>命令格式：</strong></li>
pwd&nbsp;[选项]
<li><strong>命令功能：</strong></li>
查看”当前工作目录“的完整路径
<li><strong>常用参数：</strong></li>
<ul>
<li>一般情况下不带任何参数</li>
<li>如果目录是链接时：</li>
<li>格式：<code>pwd -P</code>显示出实际路径，而非使用连接（link）路径</li>
</ul>
</ol>


<h4><strong>(4) mkdir命令</strong></h4>
<p>
Linux mkdir命令用来创建指定的名称的目录，要求创建目录的用户在当前目录
中具有写权限，并且指定的目录名不能是当前目录中已有的目录。
</p>

<ol>
<li><strong>命令格式：</strong></li>
mkdir&nbsp;[选项]&nbsp;目录
<li><strong>命令功能：</strong></li>
通过mkdir命令可以实现在指定位置创建以 DirName(指定的文件名)命名的文件夹或
目录。要创建文件夹或目录的用户必须对所创建的文件夹的父文件夹具有写权限。
并且，所创建的文件夹(目录)不能与其父目录(即父文件夹)中的文件名重名，
即同一个目录下不能有同名的(区分大小写)。
<li><strong>常用参数：</strong></li>
<ul>
<li>-m, --mode=模式, 设定权限<模式> (类似 chmod)，而不是 rwxrwxrwx 减 umask</li>
<li>-p&nbsp;--parents，可以是一个路径名称。此时若路径中的某些目录尚不存在,加上此选项后,系统将自动建立好那些尚不存在的目录,即一次可以建立多个目录; </li>
<li>-v&nbsp;--verbose 每次创建新目录都显示信息</li>
<li>--help&nbsp;显示此帮助信息并退出</li>
<li>--version&nbsp;输出版本信息并退出</li>
</ul>
</ol>


<h4><strong>(5) rm命令</strong></h4>
<p>
rm是常用的命令，该命令的功能为删除一个目录中的一个或多个文件或目录，它也可以将某个目录
及其下的所有文件及子目录均删除。对于链接文件，只是删除了链接，原有文件均保持不变。
</p>

<ol>
<li><strong>命令格式：</strong></li>
rm&nbsp;[选项]&nbsp;文件/目录
<li><strong>命令功能：</strong></li>
删除一个目录中的一个或多个文件或目录，如果没有使用- r选项，则rm不会删除目录。如果使用
rm来删除文件，通常仍可以将该文件恢复原状。
<li><strong>常用参数：</strong></li>
<ul>
<li>-f, --force &nbsp;忽略不存在的文件，从不给出提示。</li>
<li>-i, --interactive&nbsp;进行交互式删除</li>
<li>-r,-R,--recursive&nbsp;指示rm将参数中列出的全部目录和子目录均递归地删除。</li>
<li>-v,--verbose&nbsp;详细显示进行的步骤</li>
<li>--help&nbsp;显示此帮助信息并退出</li>
<li>--version&nbsp;输出版本信息并退出</li>
</ul>
<li><strong>常用范例：</strong></li>
<p><strong>例1：</strong>删除文件file，系统会先询问是否删除
<strong>命令：</strong><code>rm 文件名</code></p>
<p><strong>例2：</strong>强行删除file，系统不再提示
<strong>命令：</strong><code>rm -f log1.log</code></p>
<p><strong>例3：</strong>将 test2 子目录及子目录中所有档案删除,并且不用一一确认
<strong>命令：</strong><code>rm -rf test2</code></p>
<p><strong>例4：</strong>删除任何.log文件；删除前逐一询问确认
<strong>命令：</strong><code>rm -i \*.log</code></p>
<p><strong>例5：</strong>删除以-f开头的文件
<strong>命令：</strong><code>rm -- -f</code></p>
</ol>


<h4><strong>(6) rmdir命令</strong></h4>
<p>
mdir是常用的命令，该命令的功能是删除空目录，一个目录被删除之前必须是空的。
（注意，rm - r dir命令可代替rmdir，但是有很大危险性。）删除某目录时也必须具有对父目录的写权限。
</p>

<ol>
<li><strong>命令格式：</strong></li>
rmdir&nbsp;[选项]&nbsp;目录
<li><strong>命令功能：</strong></li>
该命令从一个目录中删除一个或多个子目录项，删除某目录时也必须具有对父目录的写权限。 
<li><strong>常用参数：</strong></li>
<ul>
<li>-p&nbsp;递归删除目录dirname</li>
<li>-v,--verbose&nbsp;详细显示进行的步骤</li>
</ul>
</ol>

<h4><strong>(7) mv命令</strong></h4>
<p>
mv命令是move的缩写，可以用来移动文件或者将文件改名（move (rename) files），
是Linux系统下常用的命令，经常用来备份文件或者目录。
</p>

<ol>
<li><strong>命令格式：</strong></li>
mv&nbsp;[选项]&nbsp;源文件/目录&nbsp;源文件/目录
<li><strong>命令功能：</strong></li>
视mv命令中第二个参数类型的不同（是目标文件还是目标目录），mv命令将文件重命
名或将其移至一个新的目录中。当第二个参数类型是文件时，mv命令完成文件重命名，
此时，源文件只能有一个（也可以是源目录名），它将所给的源文件或目录重命名为给定的
目标文件名。当第二个参数是已存在的目录名称时，源文件或目录参数可以有多个，mv命
令将各参数指定的源文件均移至目标目录中。在跨文件系统移动文件时，mv先拷贝，再将
原有文件删除，而链至该文件的链接也将丢失。
<li><strong>常用参数：</strong></li>
<ul>
<li>-b&nbsp;若需覆盖文件，则覆盖前先行备份</li>
<li>-f&nbsp;force 强制的意思，如果目标文件已经存在，不会询问而直接覆盖</li>
<li>-i&nbsp;若目标文件 (destination) 已经存在时，就会询问是否覆盖</li>
<li>-u&nbsp;若目标文件已经存在，且source比较新，才会更新(update)</li>
<li>-t&nbsp;即指定mv的目标目录，该选项适用于移动多个源文件到一个目录的情况，此时目标目录在前，源文件在后</li>
</ul>
<li><strong>常用范例：</strong></li>
<p><strong>例1：</strong>文件改名
<strong>命令：</strong><code>mv test.log test1.txt</code></p>
<p><strong>例2：</strong>移动文件
<strong>命令：</strong><code>mv test1.txt test3</code></p>
<p><strong>例3：</strong>将文件log1.txt,log2.txt,log3.txt移动到目录test3中
<strong>命令：</strong><code>mv log1.txt log2.txt log3.txt test3</code>
<code>mv -t /opt/soft/test/test4/ log1.txt log2.txt log3.txt </code>
</p>
<p><strong>例4：</strong>目录的移动
<strong>命令：</strong><code>mv dir1 dir2 </code></p>
<p><strong>例5：</strong>移动当前文件夹下的所有文件到上一级目录
<strong>命令：</strong><code>mv \* ../</code></p>
<p><strong>例6：</strong>把当前目录的一个子目录里的文件移动到另一个子目录里
<strong>命令：</strong><code>mv test3/\*.txt test5</code></p>
</ol>


<h4><strong>(8) cp命令</strong></h4>
<p>
cp命令用来复制文件或者目录，是Linux系统中最常用的命令之一。一般情况下，shell会
设置一个别名，在命令行下复制文件时，如果目标文件已经存在，就会询问是否覆盖，不管
你是否使用-i参数。但是如果是在shell脚本中执行cp时，没有-i参数时不会询问是否覆盖。
这说明命令行和shell脚本的执行方式有些不同。
</p>

<ol>
<li><strong>命令格式：</strong></li>
cp&nbsp;[选项]...&nbsp;源&nbsp;目录
<li><strong>命令功能：</strong></li>
将源文件复制至目标文件，或将多个源文件复制至目标目录。
<li><strong>常用参数：</strong></li>
<ul>
<li>-b&nbsp;类似--backup 但不接受参数</li>
<li>-f&nbsp;如果目标文件无法打开则将其移除并重试(当-n选项存在时则不需再选此项)</li>
<li>-i&nbsp;覆盖前询问(使前面的 -n 选项失效)</li>
<li>-r&nbsp;复制目录及目录内的所有项目</li>
<li>-l&nbsp;链接文件而不复制</li>
</ul>
</ol>


<h4><strong>(9) touch命令</strong></h4>
<p>
Linux的touch命令不常用，一般在使用make的时候可能会用到，用来修改文件时间戳，
或者新建一个不存在的文件。
</p>

<ol>
<li><strong>命令格式：</strong></li>
touch&nbsp;[选项]&nbsp;文件
<li><strong>命令功能：</strong></li>
touch命令参数可更改文档或目录的日期时间，包括存取时间和更改时间。 
<li><strong>常用参数：</strong></li>
<ul>
<li>-a&nbsp;只更改存取时间</li>
<li>-c&nbsp;不建立任何文档</li>
<li>-d&nbsp;使用指定的日期时间，而非现在的时间。</li>
<li>-f&nbsp;此参数将忽略不予处理，仅负责解决BSD版本touch指令的兼容性问题。</li>
<li>-m&nbsp;只更改变动时间。</li>
<li>-r&nbsp;把指定文档或目录的日期时间，统统设成和参考文档或目录的日期时间相同。</li>
<li>-t&nbsp;使用指定的日期时间，而非现在的时间。</li>
</ul>
<li><strong>常用范例：</strong></li>
<p><strong>例1：</strong>创建不存在的文件
<strong>命令：</strong><code>touch log2012.log log2013.log</code></p>
<p><strong>例2：</strong>更新log.log的时间和log2012.log时间戳相同
<strong>命令：</strong><code>touch -r log.log log2012.log</code></p>
<p><strong>例3：</strong>设定文件的时间戳
<strong>命令：</strong><code>touch -t 201211142234.50 log.log</code>
</p>
</ol>


<h4><strong>(10) cat命令</strong></h4>
<p>
cat命令的用途是连接文件或标准输入并打印。这个命令常用来显示文件内容，或者将几个文件连接起来显示，或者从标准输入读取内容并显示，它常与重定向符号配合使用。 
</p>

<ol>
<li><strong>命令格式：</strong></li>
cat&nbsp;[选项]&nbsp;[文件]
<li><strong>命令功能：</strong></li>
cat主要有三大功能：
<ol>
<li>一次显示整个文件:cat filename</li>
<li>从键盘创建一个文件:cat > filename 只能创建新文件,不能编辑已有文件.</li>
<li>将几个文件合并为一个文件:cat file1 file2 > file</li>
</ol>
<li><strong>常用参数：</strong></li>
<ul>
<li>-A&nbsp;等价于 -vET</li>
<li>-b&nbsp;对非空输出行编号</li>
<li>-e&nbsp;等价于 -vE</li>
<li>-E&nbsp;在每行结束处显示$</li>
</ul>


<h4><strong>(11) nl命令</strong></h4>
<p>
nl命令在Linux系统中用来计算文件中行号。nl可以将输出的文件内容自动的加上行号！其默认的结果与 cat -n 有点不太一样， nl 可以将行号做比较多的显示设计，包括位数与是否自动补齐0等等的功能。
</p>

<ol>
<li><strong>命令格式：</strong></li>
nl&nbsp;[选项]&nbsp;文件
<li><strong>命令功能：</strong></li>
 nl 命令读取 File 参数（缺省情况下标准输入），计算输入中的行号，将计算过的行号写入标准输出。 在输出中，nl 命令根据您在命令行中指定的标志来计算左边的行。 输入文本必须写在逻辑页中。每个逻辑页有头、主体和页脚节（可以有空节）。 除非使用 -p 标志，nl 命令在每个逻辑页开始的地方重新设置行号。 可以单独为头、主体和页脚节设置行计算标志（例如，头和页脚行可以被计算然而文本行不能）。
</ol>


<h4><strong>(12) more命令</strong></h4>
<p>
more命令，功能类似 cat ，cat命令是整个文件的内容从上到下显示在屏幕上。 more会以一页一页的显示方便使用者逐页阅读，而最基本的指令就是按空白键（space）就往下一页显示，按 b 键就会往回（back）一页显示，而且还有搜寻字串的功能 。more命令从前向后读取文件，因此在启动时就加载整个文件。
</p>

<ol>
<li><strong>命令格式：</strong></li>
more&nbsp;[-dlfpcsu ]&nbsp;[-num ]&nbsp;[+/pattern]&nbsp;[+linenum]&nbsp;[file]
<li><strong>命令功能：</strong></li>
more命令和cat的功能一样都是查看文件里的内容，但有所不同的是more可以按页来查看文件的内容，还支持直接跳转行等功能。
<li><strong>常用参数：</strong></li>
<ul>
<li>+n&nbsp;从笫n行开始显示</li>
<li>-n&nbsp;定义屏幕大小为n行</li>
<li>+/pattern&nbsp;在每个档案显示前搜寻该字串（pattern），然后从该字串前两行之后开始显示</li>
<li>-c&nbsp;从顶部清屏，然后显示</li>
</ul>
</ol>


<h4><strong>(13) less命令</strong></h4>
<p>
less工具也是对文件或其它输出进行分页显示的工具，应该说是linux正统查
看文件内容的工具，功能极其强大。less 的用法比起 more 更加的有弹性。
在more的时候，我们并没有办法向前面翻，只能往后面看，但若使用了less时，
就可以使用[pageup][pagedown]等按键的功能来往前往后翻看文件，更容易用来
查看一个文件的内容！除此之外，在 less 里头可以拥有更多的搜索功能，不止可
以向下搜，也可以向上搜。
</p>

<ol>
<li><strong>命令格式：</strong></li>
less&nbsp;[选项]&nbsp;文件
<li><strong>命令功能：</strong></li>
less与more类似，但使用less可以随意浏览文件，而more仅能向前移动，却不能向后移动，而且less在查看之前不会加载整个文件。
</ol>


<h4><strong>(14) head命令</strong></h4>
<p>
head与tail就像它的名字一样的浅显易懂，它是用来显示开头或结尾某个数量的文字区块，head 用来显示档案的开头至标准输出中，而tail想当然尔就是看档案的结尾。
</p>

<ol>
<li><strong>命令格式：</strong></li>
head&nbsp;[选项]&nbsp;文件
<li><strong>命令功能：</strong></li>
head用来显示档案的开头至标准输出中，默认head命令打印其相应文件的开头10行。 
<li><strong>常用参数：</strong></li>
<ul>
<li>-q&nbsp;隐藏文件名</li>
<li>-v&nbsp;显示文件名</li>
<li>-c&nbsp;显示字节数</li>
<li>-n&nbsp;显示的行数</li>
</ul>
</ol>


<h4><strong>(15) tail命令</strong></h4>
<p>
tail 命令从指定点开始将文件写到标准输出.使用tail命令的-f选项可以方便的查阅正在改变的日志文件,tail -f filename会把filename里最尾部的内容显示在屏幕上,并且不但刷新,使你看到最新的文件内容. 
</p>

<ol>
<li><strong>命令格式：</strong></li>
tail&nbsp;[必要参数]&nbsp;[选择参数]&nbsp;文件
<li><strong>命令功能：</strong></li>
用于显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。
</ol>


<h4><strong>(16) ln命令</strong></h4>
<p>
ln是Linux中又一个非常重要命令，它的功能是为某一个文件在另外一个位置建立一个同步的链接.当我们需要在不同的目录，用到相同的文件时，我们不需要在每一个需要的目录下都放一个必须相同的文件，我们只要在某个固定的目录，放上该文件，然后在 其它的目录下用ln命令链接（link）它就可以，不必重复的占用磁盘空间。
</p>

<ol>
<li><strong>命令格式：</strong></li>
ln&nbsp;[参数]&nbsp;[源文件或目录名]&nbsp;[目标文件或目录名]
<li><strong>命令功能：</strong></li>
Linux文件系统中，有所谓的链接(link)，我们可以将其视为档案的别名，而链接又可分为两种 : 硬链接(hard link)与软链接(symbolic link)，硬链接的意思是一个档案可以有多个名称，而软链接的方式则是产生一个特殊的档案，该档案的内容是指向另一个档案的位置。硬链接是存在同一个文件系统中，而软链接却可以跨越不同的文件系统。
<ul>
<li><strong>软链接:</strong></li>
<ol>
<li>软链接，以路径的形式存在。类似于Windows操作系统中的快捷方式</li>
<li>软链接可以跨文件系统，硬链接不可以</li>
<li>软链接可以对一个不存在的文件名进行链接</li>
<li>软链接可以对目录进行链接</li>
</ol>
<li><strong>硬链接：</strong></li>
<ol>
<li>硬链接，以文件副本的形式存在。但不占用实际空间。</li>
<li>不允许给目录创建硬链接</li>
<li>硬链接只有在同一个文件系统中才能创建</li>
</ol>
<li><strong>有两点要注意：</strong></li>
<li>ln命令会保持每一处链接文件的同步性，也就是说，不论你改动了哪一处，其它的文件都会发生相同的变化；</li>
<li>ln的链接又分软链接和硬链接两种，软链接就是ln –s 源文件 目标文件，它只会在你选定的位置上生成一个文件的镜像，不会占用磁盘空间，硬链接 ln 源文件 目标文件，没有参数-s， 它会在你选定的位置上生成一个和源文件大小相同的文件，无论是软链接还是硬链接，文件都保持同步变化。</li>
ln指令用在链接文件或目录，如同时指定两个以上的文件或目录，且最后的目的地是一个已经存在的目录，则会把前面指定的所有文件或目录复制到该目录中。若同时指定多个文件或目录，且最后的目的地并非是一个已存在的目录，则会出现错误信息。
</ul>
<li><strong>命令参数：</strong></li>
<ul>
<li><strong>必要参数：</strong></li>
<ul>
<li>-b&nbsp;删除，覆盖以前建立的链接</li>
<li>-d&nbsp;允许超级用户制作目录的硬链接</li>
<li>-f&nbsp;强制执行</li>
<li>-i&nbsp;交互模式，文件存在则提示用户是否覆盖</li>
<li>-n&nbsp;把符号链接视为一般目录</li>
<li>-s&nbsp;软链接(符号链接)</li>
<li>-v&nbsp;显示详细的处理过程</li>
</ul>
<li>选择参数：</li>
<ul>
<li>-S&nbsp;“-S<字尾备份字符串> ”或 “--suffix=<字尾备份字符串>”</li>
<li>-V&nbsp;“-V<备份方式>”或“--version-control=<备份方式>”</li>
<li>--help&nbsp;显示帮助信息</li>
<li>--version&nbsp;显示版本信息</li>
</ul>
</ul>
<li><strong>常用范例：</strong></li>
<strong>例1：</strong>给文件创建软链接
<p><strong>命令：</strong><code>ln -s log2013.log link2013</code></p>
<p><strong>命令：</strong><code>ls -lR /home/peidachang</code></p>
<strong>例2：</strong>给文件创建硬链接
<p><strong>命令：</strong><code>ln log2013.log ln2013</code></p>
<strong>例3：</strong>将文件链接为另一个目录中的相同名字
<p><strong>命令：</strong><code>ln log2013.log test3</code></p>
<strong>例4：</strong>给目录创建软链接
<p><strong>命令：</strong><code>ln -sv /opt/soft/test/test3 /opt/soft/test/test5</code></p>
</ol>

