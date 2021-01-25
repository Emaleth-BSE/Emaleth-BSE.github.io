---
layout: page
title: Repositories
permalink: repositories
---
<ul>
    {% for page in site.pages %}
      {% if page.collection == "gh-repos" %}
        <li><a href="{{ page.url }}">{{ page.title }}</a></li>
        <p>{{ page.excerpt }}</p>
      {% endif %}
    {% endfor %}
</ul>
