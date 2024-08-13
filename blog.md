
---
layout: page
title: Blog
permalink: /blog/
---

{% for post in site.posts %}
  <article>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
    <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
  </article>
{% endfor %}
