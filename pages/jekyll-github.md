---
title: Jekyll Github
permalink: /jekyll-github/
layout: post
---

## {{ page.title }}

### Плагин jekyll-github-metadata

GitHub Pages автоматически включает этот плагин. Он предоставляет информацию о репозитории через переменную `site.github`.

Примеры доступных данных:
- `site.github.url` — URL репозитория
- `site.github.repo_name` — Имя репозитория
- `site.github.contributors` — Список контрибьюторов
- `site.github.issues_url` — URL для Issues

### Деплой через GitHub Actions

Современный способ сборки — использование GitHub Actions, что позволяет использовать любые плагины (не только разрешенные GitHub Pages).

Пример `.github/workflows/jekyll.yml` (базовый):

```yaml
{% raw %}name: Deploy Jekyll site to Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4{% endraw %}
```

Подробнее: [GitHub Metadata Plugin](https://github.com/jekyll/github-metadata)
