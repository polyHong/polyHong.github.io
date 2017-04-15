---
layout: post
title: Linux常用命令总结 
category: 技术
tags: Linux 
keywords: Ubuntu, Linux
description: 
---


本文对Linux常用命令做一个总结，方便日后查阅。


<h4><strong> 一、文件处理命令</strong></h4>

<h5><strong>(1) ls命令</strong></h5>
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


<h5><strong>(2) cd命令</strong></h5>
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

<h5><strong>(3) pwd命令</strong></h5>
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


<h5><strong>(4) mkdir命令</strong></h5>
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


<h5><strong>(5) rm命令</strong></h5>
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
</ol>








