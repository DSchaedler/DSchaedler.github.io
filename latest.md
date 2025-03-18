---
layout: post
permalink: /latest/
---
<article class="post h-entry" itemscope itemtype="http://schema.org/BlogPosting">
  {% if page.previous %}
    <a href="{{ site.url | append: page.previous.url }}" style="text-align:left;float:left;">
      &#60;&#60; {{ page.previous.title }} | {{ page.previous.tags }}
    </a>
  {% endif %}
  {% if page.next %}
    <a href="{{ site.url | append: page.next.url }}" style="text-align:right;float:right;">
      {{ page.next.title }} | {{ page.next.tags }} &#62;&#62;
    </a>
  {% endif %}

  <br>
  <br>

  <div class="post-content e-content" itemprop="articleBody">
    {{ site.posts.first.content }}
  </div>

  {%- if site.disqus.shortname -%}
    {%- include disqus_comments.html -%}
  {%- endif -%}

  <a class="u-url" href="{{ page.url | relative_url }}" hidden></a>

  {% if page.previous %}
    <a href="{{ site.url | append: page.previous.url }}" style="text-align:left;float:left;">
      &#60;&#60; {{ page.previous.title }} | {{ page.previous.tags }}
    </a>
  {% endif %}
  {% if page.next %}
    <a href="{{ site.url | append: page.next.url }}" style="text-align:right;float:right;">
      {{ page.next.title }} | {{ page.next.tags }} &#62;&#62;
    </a>
  {% endif %}
    
</article>
