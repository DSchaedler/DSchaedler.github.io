---
layout: post
title: Personal
permalink: /personal/
---
<ul>
  {% for post in site.tags.personal %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
