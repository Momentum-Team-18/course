---
layout: home
title: Posts
permalink: daily-update
nav_order: 1
---

## Posts & Announcements

{: .pt-3 .home-posts-headline }

{% assign daily_posts = site.daily_posts | reverse %}
{% for post in daily_posts %}
{{ post }}
{% endfor %}
