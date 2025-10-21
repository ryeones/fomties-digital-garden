---
layout: page
title: writings
permalink: /writings
---
*a collection of more developed writings on things i find interesting, challenges i’m facing or what i’m learning.*

<p style="font-size: 1.25rem; margin-top: 1em;">latest</p>
{% assign latest = site.posts | first %}

<article>
  <h4><a href="{{ latest.url | relative_url }}">{{ latest.title }}</a></h4>
  <small>
    {{ latest.date | date: "%B %-d, %Y" | downcase }}
    · {{ latest.content | number_of_words | divided_by: 180 | ceil }} minute read
  </small>

  <p style="color: #6f6e69;">
    {{ latest.excerpt | strip_html | truncatewords: 60 }}
    <a href="{{ latest.url | relative_url }}" style="color: #6f6e69; text-decoration: underline;">read more →</a>
  </p>
</article>
---
<p style="font-size: 1.25rem; margin-top: 1em;">topics</p>
<div class="topics">
  {% assign tags_list = site.tags | sort %}
  {% for tag in tags_list %}
    {% assign tag_slug = tag[0] | slugify %}
    <a href="{{ '/tags/' | append: tag_slug | relative_url }}">{{ tag[0] }}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
</div>

---
<p style="font-size: 1.25rem; margin-top: 1em;">writings</p>
<ul class="writings-list">
{% for post in site.posts %}
  <li>
    <span class="post-date">{{ post.date | date: "%Y · %m" }}</span>
    <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

