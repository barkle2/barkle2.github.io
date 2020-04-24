---
title: IT Concepts
permalink: /it_concepts/
---

# IT 개념 설명

IT 분야를 이해하는데 있어 가장 어려운 점 중의 하나가 IT 용어의 개념을 이해하는 것입니다.
그렇지만 실제 IT 분야 종사자들도 수많은 IT 용어의 개념을 정확하게 알기는 어렵습니다. 업무를 하는 과정에서 점차 알아가는 경우가 더 많습니다.
우리도 이 설명 내용을 기초로 각자가 점차 개념을 다듬어 나갈 수 있도록 가능한 쉽게 설명하려고 노력하였습니다.

<br>

{% for post in site.categories["IT 개념"].posts limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   {% if post.content contains '<!--more-->' %}
      <a href="{{ site.baseurl }}{{ post.url }}">read more</a>
   {% endif %}
   <hr>
{% endfor %}

Want to see more? See the <a href="{{ site.baseurl }}/archive/">News Archive</a>.
