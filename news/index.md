---
title: News
description: Latest news and updates from the SPS Lab.
nav:
  order: 5
  tooltip: News
---

<h1><i class="fas fa-bullhorn section-icon"></i> News</h1>

{% include section.html %}

<div class="news-list">
{% for post in site.posts %}
  <div class="news-item">
    <span class="news-date">{{ post.date | date: "%Y.%m" }}</span>
    <a class="news-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </div>
{% endfor %}
</div>
