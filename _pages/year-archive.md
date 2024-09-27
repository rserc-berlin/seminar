---
title: "Events by Year"
permalink: /year-archive/
layout: default
author_profile: false
---


# Upcoming Events

<hr>

{% assign today = site.time %}
{% assign upcoming_events = site.posts | where_exp: "post", "post.date >= today" | sort: 'date' %}

{% for post in upcoming_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url }}">Read More</a>
  <hr> <!-- Divider between posts -->
{% endfor %}

# Past Events

<hr>

{% assign past_events = site.posts | where_exp: "post", "post.date < today" | sort: 'date' | reverse %}

{% for post in past_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url }}">Read More</a>
  <hr> <!-- Divider between posts -->
{% endfor %}

