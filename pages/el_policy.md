---
title: Employment and Labor Policy
permalink: /el_policy/
---

# 일자리 정책

고용과 노동에 관한 정책, 즉 일자리 정책은 우리의 삶에 점점 더 많은 영향을 주고 있습니다. 일자리 정책은 그 사회의 흥망성쇠를 결정할 뿐만 아니라 개인의 삶에도 지대한 영향을 미칩니다.
<br>

{% for post in site.categories["일자리 정책"] limit:10 %}
   <div class="post-preview">
   <h3> <a href="{{ site.baseurl }}{{ post.url }}"><b>{{ post.title }}</b></a> </h3>
   <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span><br>
   {% if post.badges %}{% for badge in post.badges %}<span class="badge badge-{{ badge.type }}">{{ badge.tag }}</span>{% endfor %}{% endif %}
   {{ post.content | split:'<!--more-->' | first }}
   <hr>
{% endfor %}

Want to see more? See the <a href="{{ site.baseurl }}/archive/">News Archive</a>.
