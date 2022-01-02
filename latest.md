---
layout: post
permalink: /latest/
---
{% assign post.title = site.posts.first.title %}
{% assign post.date = site.posts.first.date %}
{{ site.posts.first.content }}
