---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<ul class="post-list">
{% for post in site.categories.blog %}
  <li><small>{{ post.date | date: "%-d %B %Y" }}</small><a href="{{ post.url | relative_url }}">{{ post.title }}</a>{% if post.excerpt %} — {{ post.excerpt | strip_html | truncatewords: 25 }}{% endif %}</li>
{% endfor %}
</ul>
