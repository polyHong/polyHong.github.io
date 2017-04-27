---
layout: post
title: Linux常用命令二之文件查找命令
category: 技术
tags: Linux
keywords: Ubuntu, Linux
description:
---


本文对Linux常用命令做一个总结，方便日后查阅。

<h4><strong>(1) which命令</strong></h4>
<p>
我们经常在linux要查找某个文件，但不知道放在哪里了，可以使用下
面的一些命令来搜索:
<ul>
<li>&nbsp; &nbsp; &nbsp; &nbsp;which&nbsp;&nbsp;查看可执行文件的位置</li>
<li>&nbsp; &nbsp; &nbsp; &nbsp;whereis&nbsp;查看文件的位置</li>
<li>&nbsp; &nbsp; &nbsp; &nbsp;locate&nbsp;&nbsp;&nbsp;配合数据库查看文件位置</li>
<li>&nbsp; &nbsp; &nbsp; &nbsp;find&nbsp;&nbsp;&nbsp;实际搜寻硬盘查询文件名称</li>
</ul>
which命令的作用是，在PATH变量指定的路径中，搜索某个系统命令的位置，并且返回第一
个搜索结果。也就是说，使用which命令，就可以看到某个系统命令是否存在，以及执行的到底是哪一个位置的命令。
</p>

<ol>
<li><strong>命令格式：</strong></li>
which&nbsp;可执行文件名称
<li><strong>命令功能：</strong></li>
which指令会在PATH变量指定的路径中，搜索某个系统命令的位置，并且返回第一个搜索结果
<li><strong>常用参数：</strong></li>
<ul>
<li>-n&nbsp;指定文件名长度，指定的长度必须大于或等于所有文件中最长的文件名</li>
<li>-p&nbsp;与-n参数相同，但此处的包括了文件的路径</li>
<li>-w&nbsp;指定输出时栏位的宽度</li>
<li>-V&nbsp;显示版本信息</li>
</ul>
</ol>

<h4><strong>(2) whereis命令</strong></h4>
<p>
whereis命令只能用于程序名的搜索，而且只搜索二进制文件（参数-b）、man说明文件（参数-m）和源代码文件（参数-s）。如果省略参数，则返回所有信息。
</p>
<p>
和find相比，whereis查找的速度非常快，这是因为linux系统会将&nbsp;系统内的所有文件都记录在一个数据库文件中，当使用whereis和下面即将介绍的locate时，会从数据库中查找数据，而不是像find命令那样，通&nbsp;过遍历硬盘来查找，效率自然会很高。
</p>
<p>
但是该数据库文件并不是实时更新，默认情况下时一星期更新一次，因此，我们在用whereis和locate&nbsp;查找文件时，有时会找到已经被删除的数据，或者刚刚建立文件，却无法查找到，原因就是因为数据库文件没有被更新。
</p>

<ol>
<li><strong>命令格式：</strong></li>
whereis&nbsp;[-bmsu]&nbsp;[BMS 目录名 -f]文件名
<li><strong>命令功能：</strong></li>
whereis命令是定位可执行文件、源代码文件、帮助文件在文件系统中的位置。这些文件的属性应属于原始代码，二进制文件，或是帮助文件。whereis&nbsp;程序还具有搜索源代码、指定备用搜索路径和搜索不寻常项的能力。
<li><strong>常用参数：</strong></li>
<ul>
<li>-b&nbsp;定位可执行文件</li>
<li>-m&nbsp;定位帮助文件</li>
<li>-s&nbsp;定位源代码文件</li>
<li>-u&nbsp;搜索默认路径下除可执行文件、源代码文件、帮助文件以外的其它文件</li>
<li>-B&nbsp;指定搜索可执行文件的路径</li>
<li>-M&nbsp;指定搜索帮助文件的路径</li>
<li>-S&nbsp;指定搜索源代码文件的路径</li>
</ul>
</ol>

<h4><strong>(3) locate命令</strong></h4>
<p>
locate&nbsp;让使用者可以很快速的搜寻档案系统内是否有指定的档案。其方法是先建立一个包括系统内所有档案名称及路径的数据库，之后当寻找时就只需查询这个数据库，而不必实际深入档案系统之中了。在一般的&nbsp;distribution&nbsp;之中，数据库的建立都被放在&nbsp;contab&nbsp;中自动执行。
</p>

<ol>
<li><strong>命令格式：</strong></li>
locate&nbsp;[选择参数]&nbsp;[样式]
<li><strong>命令功能：</strong></li>
<p>
locate命令可以在搜寻数据库时快速找到档案，数据库由updatedb程序来更新，updatedb是由cron&nbsp;daemon周期性建立的，locate命令在搜寻数据库时比由整个由硬盘资料来搜寻资料来得快，但较差劲的是locate所找到的档案若是最近才建立或&nbsp;刚更名的，可能会找不到，在内定值中，updatedb每天会跑一次，可以由修改crontab来更新设定值。(etc/crontab)
</p>
<p>
locate指定用在搜寻符合条件的档案，它会去储存档案与目录名称的数据库内，寻找合乎范本样式条件的档案或目录录，可以使用特殊字元（如”*”&nbsp;或”?”等）来指定范本样式，如指定范本为kcpa*ner,&nbsp;locate会找出所有起始字串为kcpa且结尾为ner的档案或目录，如名称为kcpartner若目录录名称为kcpa_ner则会列出该目录下包括&nbsp;子目录在内的所有档案。
</p>
<p>
locate指令和find找寻档案的功能类似，但locate是透过update程序将硬盘中的所有档案和目录资料先建立一个索引数据库，在&nbsp;执行loacte时直接找该索引，查询速度会较快，索引数据库一般是由操作系统管理，但也可以直接下达update强迫系统立即修改索引数据库。
</p>
<li><strong>常用参数：</strong></li>
<ul>
<li>-e&nbsp;将排除在寻找的范围之外。</li>
<li>-l&nbsp;如果 是 1．则启动安全模式。在安全模式下，使用者不会看到权限无法看到	的档案。这会始速度减慢，因为 locate 必须至实际的档案系统中取得档案的权限资料。</li>
<li>-f&nbsp;将特定的档案系统排除在外，例如我们没有到理要把 proc 档案系统中的档案放在资料库中。</li>
<li>-q&nbsp;安静模式，不会显示任何错误讯息。</li>
<li>-n&nbsp;至多显示n个输出。</li>
<li>-r&nbsp;使用正规运算式做寻找的条件。</li>
<li>-o&nbsp;指定资料库存的名称。</li>
<li>-d&nbsp;指定资料库的路径</li>
<li>-h&nbsp;显示辅助讯息</li>
<li>-V&nbsp;显示程式的版本讯息</li>
</ul>
</ol>


<h4><strong>(4) find命令概览</strong></h4>
<p>
Linux下find命令在目录结构中搜索文件，并执行指定的操作。Linux下find命令提供了相当多的查找条件，功能很强大。由于find具有强大的功能，所以它的选项也很多，其中大部分选项都值得我们花时间来了解一下。即使系统中含有网络文件系统( NFS)，find命令在该文件系统中同样有效，只你具有相应的权限。 在运行一个非常消耗资源的find命令时，很多人都倾向于把它放在后台执行，因为遍历一个大的文件系统可能会花费很长的时间(这里是指30G字节以上的文件系统)。
</p>

<ol>
<li><strong>命令格式：</strong></li>
find&nbsp;pathname&nbsp;-options &nbsp;[-print -exec -ok ...]
<li><strong>命令功能：</strong></li>
用于在文件树种查找文件，并作出相应的处理 
<li><strong>命令参数：</strong></li>
<ul>
<li>pathname: find命令所查找的目录路径。例如用.来表示当前目录，用/来表示系统根目录。 </li>
<li>-print&nbsp;find命令将匹配的文件输出到标准输出。 </li>
<li>-exec&nbsp;find命令对匹配的文件执行该参数所给出的shell命令。相应命令的形式为'command' { } \;，注意{ }和\；之间的空格。 </li>
<li>-ok&nbsp;和-exec的作用相同，只不过以一种更为安全的模式来执行该参数所给出的shell命令，在执行每一个命令之前，都会给出提示，让用户来确定是否执行。</li>
</ul>
</ol>

