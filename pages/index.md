---
layout: page
title: 환영합니다
permalink: /
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

<div class="section-index">
    <hr class="panel-line">
    {% for post in site.docs  %}        
    <div class="entry">
    <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
    <p>{{ post.description }}</p>
    </div>{% endfor %}
</div>

