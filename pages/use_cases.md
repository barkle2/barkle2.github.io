---
title: Use Cases of IT Technology
permalink: /use_cases/
---

# IT 활용사례

IT를 활용한 정책 사례를 공유하고, 더 나은 정책을 수립하기 위한 아이디어를 고민해 볼 수 있으면 좋겠습니다.

<br>

{% for post in site.categories["IT 활용사례"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}
