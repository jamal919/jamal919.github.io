---
layout: default
title: Blog
permalink: /blog/
---
<!-- This loops through blog posts -->
{% for post in site.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="small">
    <span>{{ post.date | date: "%A, %B %d, %Y" }}</span>
    <span> | </span>
    {% if post %}
    {% assign categories = post.categories %}
    {% else %}
    {% assign categories = page.categories %}
    {% endif %}
    <span>
    Category: 
    {% for category in categories %}
    <a href="{{site.baseurl}}/categories/#{{category|slugize}}">{{category}}</a>
    {% unless forloop.last %}&nbsp;{% endunless %}
    {% endfor %}
    </span>
  </p>
  <div class="content">
    {{ post.excerpt }}
  </div>
{% endfor %}
