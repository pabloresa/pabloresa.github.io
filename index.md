---
layout: default
title: "Projects"
---

# Welcome!

Here you have a selection of my projects:

<ul>
  {% for page in site.pages %}
    {% if page.title and page.permalink contains '/project_' %}
      <li>
        <a href="{{ page.url }}">{{ page.title }}</a><br/>
        {{ page.description }}
        {% if page.image %}
          <img src="{{ page.image }}" alt="{{ page.title }}" width="200">
        {% endif %}
      </li>
    {% endif %}
  {% endfor %}
</ul>

