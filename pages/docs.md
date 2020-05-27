---
layout: page
title: 전체 보기
permalink: /docs/
---

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>

    <h3 class="category-head"><b>{{ category_name }}</b></h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <li class="archive-item">
      {{ post.date | date: "%b %-d, %Y" }}: <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
    </li>
    {% endfor %}
  </div>
{% endfor %}
</div>
