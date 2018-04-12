---
layout: default
title: prog-g
---

# このサークルについて
毎月第2,4水曜日に工学部棟E402でお菓子を食べながらプログラミングしてます  
Unityでゲームを作ったり、AndroidやWebアプリもやったりするよ  
初心者歓迎！

Twitter: [@prog_g](https://twitter.com/prog_g)  
E-mail: <programming.circle.gifu@gmail.com>

# 作ったもの
- [slack-choose-command](https://github.com/ahuglajbclajep/slack-choose-command)

# 最近の活動
<ul>
  {% for post in site.posts limit:5 %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

# タグで検索
<div>
  {% for page in site.html_pages %}
    <a href="{{ site.url }}{{ site.baseurl }}/tags/{{ page.tag }}.html">{{ page.tag }}</a>
  {% endfor %}
</div>
