---
layout: default
title: prog-g
---

# 最近の投稿
<ul>
  {% for post in site.posts limit:5 %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
