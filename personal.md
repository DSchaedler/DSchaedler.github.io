---
layout: post
title: Personal
permalink: /personal/
---
<ul>
  {% for post in site.tags.Personal %}
    <li>{{ post.date | date: "%Y-%m-%d" }} | <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
