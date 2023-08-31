---
layout: post
title: Technology
permalink: /technology/
---
<ul>
  {% for post in site.tags.technology %}
    <li>{{ post.date | date: "%Y-%m-%d" }} | <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
