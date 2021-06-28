---
layout: page
title: Blog posts
---

<ul>
  {% for post in site.categories.blog %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> ({{ post.date | date_to_string }})
    </li>
  {% endfor %}
</ul>
<br/>