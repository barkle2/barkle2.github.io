---
title: 교육자료
description: 직원들에게 참고가 될만한 자료들입니다.
---

# 교육자료

<br>

{% for post in site.categories["교육자료"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}