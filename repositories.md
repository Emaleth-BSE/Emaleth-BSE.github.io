---
layout: page
title: Repositories
permalink: repositories
---
<ul>
    {% for page in site.gh-repos %}
      <li><a href="{{ page.url }}">{{ page.title }}</a></li>
    {% endfor %}
</ul>
