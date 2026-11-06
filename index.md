---
layout: default
title: Home
---

## Welcome

The Efficient Neural Systems lab studies ... *(Replace with two or three sentences about the lab's mission and research focus.)*

We are based at ... *(institution, department, city)*.

## Latest news

<ul class="post-list">
{% for post in site.categories.news limit:3 %}
  <li><small>{{ post.date | date: "%-d %B %Y" }}</small><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

[All news →](/news/)

## Join us

We are looking for ... *(how to apply, contact email)*.
