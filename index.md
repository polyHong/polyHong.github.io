---
layout: post
title: Welcome to Hong's Blog
---


<div class="row">
  <div class="col-md-12">
    <div class="panel panel-primary">
      <div class="panel-heading">{{ site.locals.newest }}</div>
      {% for post in paginator.posts %}
        <a  href='{{ post.url }}' class="list-group-item pjaxlink clearfix">
          {{post.title}}
          <span class="badge">{{ post.date | date:"%Y年%m月%d日" }}</span>
        </a>
      {% endfor %}
    </div>
  </div>
  {% for cate in site.cates %}
    <div class="col-md-12">
      <div class="panel panel-primary">
        <div class="panel-heading">{{ cate }}</div>
        {% for tag in site.tags %} 
          {% if tag[0] == cate %}
            {% for post in tag[1] %}
              <a  href='{{ post.url }}' class="list-group-item pjaxlink clearfix">
                {{post.title}}
                <span class="badge">{{ post.date | date:"%Y年%m月%d日" }}</span>
              </a>
            {% endfor %}
          {% endif %}
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>


## Why Blog

2012年的时候，就想着应该有个自己的博客，来记录学习和生活的足迹. 
记得当时一时兴起, 注册了个新浪博客，暗下决心, 一定要把它坚持下去，
当岁月流逝, 还有个地方可以凭吊过往. 然而，新浪博客一方面只能写文字, 
另一方面到处是烦人的广告. 以至于心里当时那把火烧着烧着就灭了.

经营博客的计划随之搁浅。直到几天前 (2015年5月份)，看到很多网友利用
jekyll和github搭建的博客，界面简洁，零广告. 甚至，它还可以结合MathJax
排版公式和代码. 完美! 


## About this Blog

这个博客模板改自[**闫肃的博客**](http://yansu.org/). 
它是通过 [Jekyll](http://jekyllrb.com/) 生成，部署在 [Github](https://pages.github.com)，
主题基于 [3-Jekyll](https://github.com/P233/3-Jekyll) 修改生成，
非常感谢 [Peiwen Lu](https://github.com/P233) 开发出这么漂亮的主题.

我博客的源码托管在[Github](https://github.com/polyHong/polyHong.github.io)上，
如果有任何改进意见，欢迎讨论.
