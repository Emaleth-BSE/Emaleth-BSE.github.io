---
layout: page
title: Repositories
permalink: repositories
---
{% for page in site.pages %}
  {% if page.collection == "gh-repos" %}
    <h2><a href="{{ page.url }}">{{ page.title }}</a></h2>
    {% if page.content contains '<!--more-->' %}
      <article>{{ page.content | split:'<!--more-->' | first }}</article>
    {% endif %}
  {% endif %}
{% endfor %}
