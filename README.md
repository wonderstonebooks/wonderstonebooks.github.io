# Wonderstone Books

Author site, built by GitHub Pages' native Jekyll. No build pipeline or dependencies to maintain.

## Adding a book

Add a Markdown file to `_books/` named `slug.md`:

```markdown
---
title: Book Title
subtitle: A Novel
order: 3
cover: /assets/img/book-title.jpg
description: One-sentence hook shown on the Books page and in link previews.
buy:
  - label: Amazon
    url: https://...
  - label: Bookshop.org
    url: https://...
---

Back-cover copy in GitHub-flavored Markdown.
```

Push to `main`. It appears at `/books/slug/` and on the Books page, sorted by `order`. Put cover images in `assets/img/` (2:3 aspect ratio).

## Preview locally

```sh
docker run --rm -p 4000:4000 -v "$PWD":/site -w /site ruby:3.3 \
  sh -c 'gem install github-pages webrick && jekyll serve --host 0.0.0.0'
```
