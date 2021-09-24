---
layout: default
title: 岐阜大学プログラミングサークル
---

# このサークルについて

毎週水曜日の 13:00 から工学部棟 E403 にて LT をしたり、お菓子を食べながらプログラミングをしたりしています。
それぞれが好きなことに取り組み、ゲームの開発、Web 系、人工知能、競プロなど手広くやっています。
初心者歓迎！

Slack でプログラミングについて語り合っています。
サークルへ加入希望の方は[招待リンク](https://join.slack.com/t/prog-g/signup) から Slack ワークスペースへご参加ください。

Slack ワークスペースはサークル所属の学生の交流の場としており、登録できるメールアドレスは岐大の学生のものに限定しております。
加入希望の方以外の参加はご遠慮ください。
加入前のご質問等は[お問い合わせ](#お問い合わせ)からお願いします。

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
  {% for post in site.posts limit:10 %}
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

# お問い合わせ

見学の希望やご質問等は[Twitter](https://twitter.com/prog_g)の DM または下記メールアドレスまでお願いします。

<img src="/assets/images/Email.svg" height="16px">
