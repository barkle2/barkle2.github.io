---
title: Understanding IT
permalink: /understand_it/
---

# IT 이해하기

비전공자가 IT를 활용하여 업무를 하는데 있어 느끼는 어려움 중의 하나는 IT 용어의 개념을 이해하는 것입니다. 사전지식 없이 영어로 된 생소한 IT 용어들을 이해하기 어려운 것이 사실입니다.  
다른 하나는 IT 전문가와 소통을 하는 방법을 터득하는 것입니다. 분명히 한국말인데, 시간이 지나고 보면 완전히 다르게 생각하고 있었던 것을 알게 되는 경우가 많습니다.
이 두 가지 어려움 해소하는데 도움이 될 만한 내용들을 소개해 보겠습니다.

<br>

{% for post in site.categories["IT 이해하기"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}
