---
title: О проекте
permalink: /about-us/
skills:
  - HTML
  - CSS
  - JS
---

# {{ page.title }}

Это страница о проекте {{ site.title }}

## My Skills

{% for skill in page.skills %}

- {{ skill }}
  {% endfor %}
