---
title: Github Pages
permalink: /github-pages/
layout: post
---

## {{ page.title }}

GitHub Pages позволяет бесплатно хостить Jekyll сайты прямо из репозитория.

### Gem 'github-pages'

GitHub Pages использует специальный gem, который фиксирует версии Jekyll и плагинов:

```ruby
# В вашем Gemfile
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
```

### Настройка _config.yml

При использовании GitHub Pages, если сайт находится не в корне домена (например, `user.github.io/project/`), настройте `baseurl`:

```yaml
# _config.yml
url: "https://user.github.io"
baseurl: "/project"
```

При этом ссылки на статику должны включать `baseurl`:
```liquid
{% raw %}<link rel="stylesheet" href="{{ '/assets/css/style.css' | relative_url }}">{% endraw %}
```

Подробнее: [GitHub Pages and Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)
