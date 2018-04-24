---
layout: archive
permalink: /blog/
title: "Posts by Year"
author_profile: true
type: pages
scope:
    path: ""
    type: pages
toc: true
toc_label: "R&eacute;sum&eacute;"
header:
  overlay_image: /assets/images/sunset-gsl.jpg
---

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for year in postsByYear %}
  <h2 id="{{ year.name | slugify }}" class="archive__subtitle">{{ year.name }}</h2>
  {% for post in year.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
