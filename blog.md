---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<ul>
{% for post in site.posts %}
<li>
<a href="{{_posts.url}}">{{ post.title }}</a>
</li>
{% endfor %}
</ul>