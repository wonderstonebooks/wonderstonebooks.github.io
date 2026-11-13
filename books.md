---
layout: default
title: Books
permalink: /books/
---

# Books

{% assign books = site.books | sort: "order" %}
{% if books.size > 0 %}
<ul class="book-list">
  {% for book in books %}
  <li>
    <a href="{{ book.url | relative_url }}"><img class="cover" src="{{ book.cover | relative_url }}" alt="Cover of {{ book.title }}" width="120" height="180"></a>
    <div>
      <h2><a href="{{ book.url | relative_url }}">{{ book.title }}</a></h2>
      <p>{{ book.description }}</p>
      {% include buy-links.html links=book.buy %}
    </div>
  </li>
  {% endfor %}
</ul>
{% else %}
Coming soon...
{% endif %}
