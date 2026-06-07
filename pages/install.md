---
title: Установка и запуск
permalink: /install/
layout: default
skills:
  - HTML
  - CSS
  - JS
aboutMe: I'm a hero
---

# {{ page.title }}

This is a website about {{ site.title }}

## My Skills

{% for skill in page.skills %}

- {{ skill }}
  {% endfor %}

## About mew
