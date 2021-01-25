---
layout: page
title: Repositories
permalink: repositories
---
<ul>
    {% for page in site.pages %}
      {% if page.collection == "gh-repos" %}
        <li><a href="{{ page.url }}">{{ page.title }}</a></li>
        {% if page.content contains '<!--more-->' %}
          {{ page.content | split:'<!--more-->' | first }}        
      {% endif %}
    {% endfor %}
</ul>

