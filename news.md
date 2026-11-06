---
layout: default
title: News
permalink: /news/
---

# News

<ul class="post-list">
{% for post in site.categories.news %}
  <li><small>{{ post.date | date: "%-d %B %Y" }}</small><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
