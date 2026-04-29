---
layout: page
title: 分類瀏覽
permalink: /categories/
---

這裡依照「出題單位」進行分類。

{% for category in site.categories %}
  <h2 id="{{ category[0] | slugize }}">{{ category[0] | upcase }}</h2>
  <ul>
    {% for post in category[1] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%Y-%m-%d" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
