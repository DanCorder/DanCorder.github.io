---
layout: page
title: Today I Learned
---

Quick posts, usually about single small topics.

<ul>
  {% for til in site.til %}
  <li>
    <a href="{{ til.url }}">{{ til.title }}</a>
  </li>
  {% endfor %}
</ul>
<br/>