---
layout: page
title: Technology
permalink: /technology/
---
<ul>
  {% for post in site.tags.Technology %}
    <li>{{ post.date | date: "%Y-%m-%d" }} | <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
