---
layout: page
title: Repositories
permalink: repositories
---
<main>
  {% for page in site.pages %}
    {% if page.collection == "gh-repos" %}
      <h2><a href="{{ page.url }}">{{ page.title }}</a></h2>
      {% if page.content contains '<!--more-->' %}
        {{ page.content | split:'<!--more-->' | first }}
      {% endif %}
    {% endif %}
  {% endfor %}
</main>
