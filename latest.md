---
layout: post
permalink: /latest/
---
{% assign page.title = site.posts.first.title %}
{% assign page.date = site.posts.first.date %}
{{ site.posts.first.content }}
