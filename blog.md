---
layout: default
title: Blog
---

## Blog

{% if site.posts.size == 0 %}
<p>No posts yet. Check back soon!</p>
{% else %}
<div class="blog-list">
    {% for post in site.posts %}
    <div class="blog-post-item">
        <h3 class="blog-post-title">
            <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
        </h3>
        <p class="blog-post-date">{{ post.date | date: "%B %-d, %Y" }}</p>
        {% if post.description %}
        <p class="blog-post-excerpt">{{ post.description }}</p>
        {% elsif post.excerpt %}
        <p class="blog-post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
        {% endif %}
    </div>
    {% endfor %}
</div>
{% endif %}
