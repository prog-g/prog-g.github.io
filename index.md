---
layout: default
title: prog-g
---

# このサークルについて
隔週で水曜日の13:30から工学部棟E403でお菓子を食べながらプログラミングをしています  
Unityでゲームを作ったり、AndroidやWebアプリもやったりするよ  
初心者歓迎！


## 作ったもの
<ul>
  {% for artifact in site.data.artifacts %}
    <li>
      <a href="{{ artifact.repository }}">{{ artifact.name }}</a>
    </li>
  {% endfor %}
</ul>


## 最近の活動
<ul>
  {% for post in site.posts limit:5 %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
[もっとみる](allposts)


## タグで検索
<div>
  {% for page in site.html_pages %}
    <a href="{{ site.url }}{{ site.baseurl }}/tags/{{ page.tag }}.html">{{ page.tag }}</a>
  {% endfor %}
</div>
