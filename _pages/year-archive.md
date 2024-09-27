---
title: "Events by Year"
permalink: /year-archive/
layout: posts
author_profile: false
---


# Upcoming Events

{% assign today = site.time %}

{% for post in site.posts %}
  {% if post.date >= today %}
    <h2>{{ post.title }}</h2>
    <p>{{ post.date | date: "%B %d, %Y" }}</p>
    <p>{{ post.excerpt }}</p>
    <a href="{{ post.url }}">Read More</a>
  {% endif %}
{% endfor %}

# Past Events

{% for post in site.posts %}
  {% if post.date < today %}
    <h2>{{ post.title }}</h2>
    <p>{{ post.date | date: "%B %d, %Y" }}</p>
    <p>{{ post.excerpt }}</p>
    <a href="{{ post.url }}">Read More</a>
  {% endif %}
{% endfor %}
