---
layout: post
title: Personal
permalink: /personal/
---
<ul>
  {% for post in site.tags.personal %}
    <li>{{ post.date | date: "%Y-%m-%d %H:%M" }} | <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
