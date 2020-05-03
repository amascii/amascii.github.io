---
layout: page
title: Library
permalink: /library/
---

2020 Reading List
<table>                                                                         
<tr>
  <th>Title</th>
  <th>Author</th>
  <th>Finished in</th>
  <th>Comments</th>
  <th>Rating</th>
</tr>

{% for book in site.books %}
<tr>
  <td> <a href="{{ book.url }}"> {{ book.title }} </a></td>
  <td>{{ book.author }}</td>
  <td>{{ book.month }}, {{ book.year }}</td>
  <td>{{ book.comments }}</td>
  <td>{{ book.rating }}/10</td>
</tr>

{% endfor %}
</table>
