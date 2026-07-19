---
layout: page
title: Archive
permalink: /archive/
---

Every issue, newest first.

{% assign by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in by_year %}
<h2 class="archive-year">{{ year.name }}</h2>
<ul class="archive-list">
  {% for post in year.items %}
  <li>
    <span class="archive-date">{{ post.date | date: "%b %-d" }}</span>
    <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
  </li>
  {% endfor %}
</ul>
{% endfor %}
