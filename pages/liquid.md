---
title: Основы Liquid
permalink: /liquid/
layout: post
---

## {{ page.title }}

Liquid — это язык шаблонов, используемый в Jekyll.

### Вывод (Objects)

Вывод переменных осуществляется с помощью двойных фигурных скобок:

```liquid
{% raw %}{{ page.title }}
{{ site.url }}{% endraw %}
```

### Теги (Tags)

Теги управляют логикой шаблона. Оборачиваются в `{% raw %}{% %}{% endraw %}`.

**Условия:**
```liquid
{% raw %}{% if page.title == "Основы Liquid" %}
  <p>Это страница о Liquid!</p>
{% elsif page.layout == "post" %}
  <p>Это пост.</p>
{% else %}
  <p>Что-то другое.</p>
{% endif %}{% endraw %}
```

**Циклы:**
```liquid
<ul>
{% raw %}{% for post in site.posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}{% endraw %}
</ul>
```

### Фильтры (Filters)

Фильтры изменяют вывод и применяются через символ `|`.

```liquid
<!-- Перевод в верхний регистр -->
{% raw %}{{ "hello" | upcase }}{% endraw %} <!-- Выведет: HELLO -->

<!-- Форматирование даты -->
{% raw %}{{ post.date | date: "%Y-%m-%d" }}{% endraw %}

<!-- Количество элементов в массиве -->
{% raw %}{{ site.posts | size }}{% endraw %}

<!-- Ограничение количества слов -->
{% raw %}{{ post.content | truncatewords: 20 }}{% endraw %}
```

Подробнее: [Liquid Documentation](https://shopify.github.io/liquid/)
