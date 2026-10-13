
---
layout: default
title: Home
---

theme: jekyll-theme-minimal
Welcome to my Networking Field Notes!

I'm an IT student building practical networking and troubleshooting skills through hands-on labs. Here, I document what I learn, the challenges I encounter, and the solutions that help me understand technology better.


Here are my latest posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a> 
      <small>({{ post.date | date: "%B %d, %Y" }})</small>
    </li>
  {% endfor %}
</ul>
