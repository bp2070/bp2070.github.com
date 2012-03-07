---
layout: page
title: Home
---
{% include JB/setup %}
# Latest Posts
{% assign posts = site.posts %}
{% assign listing_limit = 5 %}
{% include post-listing.html %}
