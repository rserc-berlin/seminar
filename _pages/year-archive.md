---
title: "Events by Year"
permalink: /year-archive/
layout: default
author_profile: false
---


<div style="text-align: center; max-width: 800px; margin: 0 auto;">

# Upcoming Events

{% assign today = site.time %}
{% assign upcoming_events = site.posts | where_exp: "post", "post.date >= today" | sort: 'date' %}

{% for post in upcoming_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url | relative_url }}">Read More</a>
  <hr>
{% endfor %}

# Past Events

{% assign past_events = site.posts | where_exp: "post", "post.date < today" | sort: 'date' | reverse %}

{% for post in past_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url | relative_url }}">Read More</a>
  <hr>
{% endfor %}

</div>


