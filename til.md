---
layout: single-column
title: Today I Learned
---

Quick posts, usually about single small topics.

<ul>
  {% for til in site.categories.til %}
  <li>
    <a href="{{ til.url }}">{{ til.title }}</a>
  </li>
  {% endfor %}
</ul>
<br/>