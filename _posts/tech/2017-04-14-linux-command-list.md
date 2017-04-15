---
layout: post
title: Linux常用命令总结 
category: 技术
tags: Linux 
keywords: Ubuntu, Linux
description: 
---


本文对Linux常用命令做一个总结，方便日后查阅。


#### **一、文件处理命令**

##### **(1) ls命令**
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
<p>
<code>ls -l * |grep "^-"|wc -l</code>文件个数
<code>ls -l * |grep "^d"|wc -l </code>目录个数
</p>
</ol>







