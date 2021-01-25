---
layout: page
title: Repositories
permalink: repositories
---
<ul>
    {% for page in site.pages %}
      {% if page.collection == "gh-repos" %}
        <li><a href="{{ page.url }}">{{ page.title }}</a></li>
        <p>{{ page.content | truncatewords:75 }}</p>
      {% endif %}
    {% endfor %}
</ul>
