---
title: Установка и запуск
permalink: /install/
layout: post
---

## {{ page.title }}

```bash
# Установка гемов
gem install jekyll bundler
```

```bash
# Создание нового сайта ‘./myblog’
jekyll new myblog
cd myblog
```

```bash
# Опционально: если вы планируете разместить проект на GitHub Pages, используйте вместо этого этот файл Gemfile
cat > Gemfile <<-END source 'https://rubygems.org' gem 'github-pages', group: :jekyll_plugins END
```

```bash
# Установка гемов
gem install jekyll bundler
```

Подробнее: [Jekyll Quickstart](https://jekyllrb.com/docs/)
