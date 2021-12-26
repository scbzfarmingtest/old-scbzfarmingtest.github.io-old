---
layout: default
title: 分类
permalink: /categories/
---

# 分类

{% capture categories %}
  {% for category in site.categories %}
    {{ category[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedcategories = categories | split:' ' | sort %}

{% for category in sortedcategories %}
  <h2 id="{{ category }}">{{ category }}</h2>  
  {% assign cate = site.categories[category] %}
  <span>共({{ cate.size }})篇</span>
  <ul>
  {% for post in cate %}
        <li>{{ post.date | date:"%Y %b.%d"}}&emsp;<a href="{{ post.url }}">{{ post.title }}</a></li>  {% endfor %}
  </ul>
  <br/>
{% endfor %}