---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<div class="blog-cards">
{% for post in site.posts %}
  <div class="blog-card">
    <h2 class="blog-card-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>
    <div class="blog-card-meta">
      {{ post.date | date: "%B %d, %Y" }}
      {% if post.tags.size > 0 %}
        <span class="blog-card-tags">
          {% for tag in post.tags %}
            <span class="blog-card-tag">{{ tag }}</span>
          {% endfor %}
        </span>
      {% endif %}
    </div>
    <p class="blog-card-excerpt">{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
  </div>
{% endfor %}
</div>