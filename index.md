---
layout: default
title: Home
---

# Kevin's Blog

Welcome! Here are the latest posts.

<ul>
{% for post in site.posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%Y-%m-%d" }}</li>
{% endfor %}
</ul>
