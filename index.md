---
layout: home
title: AI Exam Experience
---

歡迎來到 AI Exam 經驗分享與心得紀錄。這裡記錄了我們在建立高品質國考題庫過程中的各種發現、申論題參考答案以及學習心得。

## 最新文章
{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url | relative_url }}) - {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}
