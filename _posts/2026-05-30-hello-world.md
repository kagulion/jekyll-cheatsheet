---
layout: post
title: "Мой первый пост"
author: jill
---

{% assign author = site.authors | where: "short_name", page.author | first %}

{% if author %}
  <div class="author-card">
    <strong>Автор: {{ author.name }}</strong> ({{ author.position }})
  </div>
{% endif %}

{{ content }}
