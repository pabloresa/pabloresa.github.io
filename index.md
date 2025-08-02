---
layout: default
title: "Projects"
---

# Welcome!

Here you have a selection of my projects:

<ul>
  {% for project in site.projects %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a><br/>
      {{ project.description }}
      {% if project.image %}
        <div><img src="{{ project.image }}" alt="{{ project.title }}" width="300"></div>
      {% endif %}
    </li>
  {% endfor %}
</ul>
