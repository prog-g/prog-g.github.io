---
layout: default
title: 岐阜大学プログラミングサークル
---

# このサークルについて

毎週水曜日の 13:00 から工学部棟 E403 にて LT をしたり、お菓子を食べながらプログラミングをしています。
それぞれが好きなことに取り組み、ゲームやアプリの開発、Web 技術、人工知能、競プロなど手広くやっています。
初心者歓迎！

Slack でプログラミングについて語り合っています。
[Slack の招待リンク](https://join.slack.com/t/prog-g/signup) を作りました。
登録できるメールアドレスを岐大生のものに限定していますが、学外の方も [Twitter](https://twitter.com/prog_g) などで声をかけてもらえれば参加可能です。

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
    {% if page.tag %}
      <a href="{{ site.url }}{{ site.baseurl }}/tags/{{ page.tag }}.html">{{ page.tag }}</a>
    {% endif %}
  {% endfor %}
</div>
