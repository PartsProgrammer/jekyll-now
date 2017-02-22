---
layout: post
title: TestPost
---

<h4>カテゴリnewsの記事一覧</h4>
{% for category in  site.categories %}
  <h4>{{ category[0] }}の記事一覧</h4>
  <ul>
  {% for post in site.categories.{{ category[0] }} %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}
