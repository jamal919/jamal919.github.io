---
layout: default
title: Blog
permalink: /blog/
---
<!-- This loops through blog posts -->
{% for post in site.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="small">
    <span>{{ post.date }}</span>
  </p>
  <div class="content">
    {{ post.excerpt }}
  </div>
{% endfor %}
