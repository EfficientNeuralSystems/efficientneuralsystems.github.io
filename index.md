---
layout: default
title: Home
---

## Welcome

The Laboratory for Efficient Neural Systems (LENS) investigates how naturally and artificially intelligent systems can achieve efficiency in inference and training.

We are based at the Department for Machine Learning and Neural Computing, School of AI, Radboud University, Nijmegen, The Netherlands.

## Latest news

<ul class="post-list">
{% for post in site.categories.news limit:3 %}
  <li><small>{{ post.date | date: "%-d %B %Y" }}</small><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

[All news →](/news/)

