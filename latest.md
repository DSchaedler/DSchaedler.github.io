---
layout: base
permalink: /latest/
---
<article class="post h-entry" itemscope itemtype="http://schema.org/BlogPosting">

  <header class="post-header">
    <h1 class="post-title p-name" itemprop="name headline">{{ site.posts.first.title }}</h1>
    <p class="post-meta">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      <time class="dt-published" datetime="{{ site.posts.first.date | date_to_xmlschema }}" itemprop="datePublished">
        {{ site.posts.first.date | date: date_format }}
      </time>
      {%- if page.modified_date -%}
        ~ 
        {%- assign mdate = page.modified_date | date_to_xmlschema -%}
        <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
          {{ mdate | date: date_format }}
        </time>
      {%- endif -%}
      {%- if site.posts.first.author -%}
        • {% for author in site.posts.first.author %}
          <span itemprop="author" itemscope itemtype="http://schema.org/Person">
            <span class="p-author h-card" itemprop="name">{{ author }}</span></span>
            {%- if forloop.last == false %}, {% endif -%}
        {% endfor %}
      {%- endif -%}
      {%- if site.posts.first.tags -%}
          • {% for tags in site.posts.first.tags %}
            <span itemprop="tags" itemscope itemtype="http://schema.org/meta">
              <span class="p-tags h-card" itemprop="tagList">{{ tags }}</span></span>
              {%- if forloop.last == false %}, {% endif -%}
          {% endfor %}
        {%- endif -%}</p>
  </header>
  
  <div class="post-content e-content" itemprop="articleBody">
    {{ site.posts.first.content }}
  </div>

  {%- if site.disqus.shortname -%}
    {%- include disqus_comments.html -%}
  {%- endif -%}
    
</article>
