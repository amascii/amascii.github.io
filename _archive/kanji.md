---
layout: page
title: Kanji
permalink: /kanji/
---

Kanji progress goes here
- Done with RTK 1

<p>
<span style="color:orange;">
{% for kanji in site.data.kanji.kanji.list  limit:site.data.kanji.kanji.current %}
      {{ kanji }}
{% endfor %}
</span>

{% for kanji in site.data.kanji.kanji.list  offset:site.data.kanji.kanji.current %}
      {{ kanji }}
{% endfor %}
</p>
