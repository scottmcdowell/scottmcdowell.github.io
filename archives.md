---
layout: page
title: Archive
permalink: /archive/
---

{% for post in site.posts %}
  {% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
  {% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
  {% if month != nmonth %}
  {% if forloop.index != 1 %}</ul>{% endif %}
  <h4 class="archive-month">{{ post.date | date: '%B %Y' }}</h4>
  <ul class="archive">
  {% endif %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> <time>{{ post.date | date: "%e %B %Y" }}</time></li>
{% endfor %}