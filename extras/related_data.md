---
title: 참고자료
description: 학습과 업무에 도움이 되는 자료들입니다.
---

# 참고자료

학습과 업무에 도움이 되는 자료들을 모아두었습니다.

<br>

{% for post in site.categories["참고자료"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}
