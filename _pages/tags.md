---
layout: page
title: tags
permalink: /tags
---
### topics

*a space to place all my top level mocs - in simpler terms, a way to easily categorise things i'm interested in*

<div class="topics">
  {% assign tags_list = site.tags | sort %}
  {% for tag in tags_list %}
    <a href="{{ '/tags/' | append: tag[0] | slugify | relative_url }}">{{ tag[0] }}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
</div>