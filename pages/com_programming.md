---
title: Computer Programming
permalink: /com_programming/
---

# 컴퓨터 프로그래밍

데이터 중심 행정에 있어서 컴퓨터 프로그래밍은 현장과 같습니다. 컴퓨터 프로그래밍을 전혀 모르는 상황에서 추진하는 데이터 중심 행정은 현실과 괴리되기 쉽습니다. 프로그래머로 취업할 수 있는 수준까지는 필요하지 않지만, 그래도 기초적인 내용은 알고 있어야 합니다. 하루에 1시간씩 한달정도 시간을 투자하면 어느 정도 개념이 잡힐 거라고 생각합니다.

<br>

{% for post in site.categories["컴퓨터 프로그래밍"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}
