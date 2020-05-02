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
  <th>Comments</th>
  <th>Read in</th>
</tr>

{% for book in site.books %}
<tr>
  <td> <a href="{{ book.url }}"> {{ book.title }} </a></td>
  <td>{{ book.author }}</td>
  <td>{{ book.comments | markdownify }}</td>
  <td>{{ book.month }}, {{ book.year }}</td>
</tr>

{% endfor %}
</table>
