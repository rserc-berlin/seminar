---
title: "Upcoming Events"
permalink: /year-archive/
layout: single
class: wide
author_profile: false
#text-align: center;
#<div style="max-width: 800px; margin: 0 auto;">
---



{% assign today = site.time %}
{% assign upcoming_events = site.posts | where_exp: "post", "post.date >= today" | sort: 'date' %}

{% for post in upcoming_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url | relative_url }}">Read More</a>
  <hr>
{% endfor %}


<br><br> <!-- Two line breaks -->

# Past Events

{% assign past_events = site.posts | where_exp: "post", "post.date < today" | sort: 'date' | reverse %}

{% for post in past_events %}
  <h2>{{ post.title }}</h2>
  <p><strong>Date:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
  <p>{{ post.excerpt }}</p>
  <a href="{{ post.url | relative_url }}">Read More</a>
  <hr>
{% endfor %}




