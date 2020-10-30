---
title: 추천도서
description: 제가 읽은 책 중에서 추천할만한 책들을 소개해드립니다.
---

# 추천도서

<br>

{% for post in site.categories["추천도서"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}
