---
layout: default
title: Blog
permalink: /blog/
---

<style>
.blog-cards {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-top: 1.5rem;
}

.blog-card {
  border: 1px solid #e0e0e0;
  border-radius: 10px;
  padding: 1.5rem;
  background: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
  transition: box-shadow 0.2s ease, transform 0.2s ease;
}

.blog-card:hover {
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12);
  transform: translateY(-2px);
}

.blog-card-title {
  margin: 0 0 0.4rem;
  font-size: 1.25rem;
}

.blog-card-title a {
  text-decoration: none;
  color: #222;
}

.blog-card-title a:hover {
  color: #0056b3;
}

.blog-card-meta {
  font-size: 0.85rem;
  color: #888;
  margin-bottom: 0.75rem;
}

.blog-card-tags {
  display: inline;
}

.blog-card-tag {
  display: inline-block;
  background: #f0f0f0;
  color: #555;
  font-size: 0.75rem;
  padding: 0.15rem 0.5rem;
  border-radius: 4px;
  margin-left: 0.4rem;
}

.blog-card-excerpt {
  font-size: 0.95rem;
  color: #444;
  line-height: 1.6;
  margin: 0;
}
</style>

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