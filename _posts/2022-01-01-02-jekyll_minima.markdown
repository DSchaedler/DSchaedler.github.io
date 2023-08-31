---
layout: post
title:  "Jekyll Minima"
date:   2022-01-01 11:23:00 -0500
tags: technology
---
Seems only fitting for the first real post on this blog to be meta.

I had quite the time getting the minima theme to work on this blog, between trying to install gems, and getting the ubuntu dev tools installed on my Chromebook. Turns out all I needed was 

{% highlight markdown %}
# Build settings
plugins:
  - jekyll-remote-theme
remote_theme: jekyll/minima
minima:
  skin: dark

{% endhighlight %}

in my `_config.yml` file. Things don't have to be complicated, but the internet makes them so.
