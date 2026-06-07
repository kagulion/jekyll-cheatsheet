---
title: Front Matter
permalink: /front-matter/
layout: post
---

## {{ page.title }}

Front Matter — это блок данных в формате YAML в самом начале файла. Он задает метаданные страницы.

### Основные переменные

```yaml
---
layout: post       # Шаблон, используемый для страницы
title: Заголовок   # Название страницы
permalink: /url/   # Кастомный URL страницы
published: false   # Исключить страницу из сборки
date: 2026-06-07   # Дата публикации (переопределяет дату в имени файла)
---
```

### Доступ к переменным

Все переменные, определенные в Front Matter, доступны в шаблонах через объект `page`:

```liquid
{% raw %}<h1>{{ page.title }}</h1>{% endraw %}
```

### Front Matter Defaults

Вы можете задать значения по умолчанию для Front Matter в `_config.yml`:

```yaml
defaults:
  - scope:
      path: "" # Все файлы
      type: "posts"
    values:
      layout: "post"
      author: "Имя автора"
```

Подробнее: [Front Matter](https://jekyllrb.com/docs/front-matter/)
