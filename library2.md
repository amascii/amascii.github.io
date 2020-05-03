---
layout: page
title: Library
permalink: /library/
---

- Book pages may contain **spoilers**
- Books are listed in order read

<table>                                                       
<tr>
  <th>Title</th>
  <th>Author</th>
  <th>Comments</th>
  <th>Score</th>
</tr>

{% for book in site.books %}
<tr>
  <td> 
  {%- if book.has-content == true -%}
  <a href="{{ book.url }}"> {{ book.title }} </a>
  {%- else -%} 
  {{book.title}}
  {%- endif -%}
  </td>
  <td>{{ book.author }}</td>
  <td>{{ book.comment | markdownify}}</td>
  <td>{{ book.score }}</td>
</tr>

{% endfor %}
</table>
