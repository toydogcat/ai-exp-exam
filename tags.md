---
layout: page
title: 標籤雲
permalink: /tags/
---

這裡依照「年份」、「科目」與「考點」進行快速搜尋。

{% capture site_tags %}{% for tag in site.tags %}{{ tag[0] | slugize }}{% unless forloop.last %}|{% endunless %}{% endfor %}{% endcapture %}
{% assign tag_words = site_tags | split: "|" | sort %}

<div class="tag-cloud" style="margin-bottom: 2em; line-height: 2;">
{% for item in tag_words %}
  <a href="#{{ item }}" style="margin-right: 15px; background: #f0f0f0; padding: 5px 10px; border-radius: 5px; text-decoration: none; color: #333;">#{{ item }}</a>
{% endfor %}
</div>

<hr>

{% for item in tag_words %}
  <h3 id="{{ item }}">{{ item }}</h3>
  <ul>
    {% for post in site.tags[item] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%Y-%m-%d" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
