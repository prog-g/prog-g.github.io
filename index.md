---
layout: default
title: prog-g
---

# このサークルについて
毎月第2,4水曜日に工学部棟E402でお菓子を食べながらプログラミングしてます  
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


## タグで検索
<div>
  {% for page in site.html_pages %}
    <a href="{{ site.url }}{{ site.baseurl }}/tags/{{ page.tag }}.html">{{ page.tag }}</a>
  {% endfor %}
</div>
