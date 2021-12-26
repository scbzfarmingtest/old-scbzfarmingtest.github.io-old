---
layout: default
title: 近闻
permalink: /recent/
---

# 近闻

## 最近7日的博文

<ul>
{% assign latestPost_year = site.posts.first.date | date: "%Y"  %}
{% assign latestPost_day = site.posts.first.date | date: "%j" | plus: 0  %}
{% assign latestPost_day_minus_week = site.posts.first.date | date: "%j" | minus: 7  %}

{% for post in site.posts %}
    <li>
    {% assign postYear = post.date | date: "%Y" %}
    {% assign postDay = post.date | date: "%j" | plus: 0 %}
    
    {% if latestPost_year == postYear and postDay > latestPost_day_minus_week and postDay <= latestPost_day  %}
        {{ post.date | date:"%Y %b.%d"}}&emsp;<a href="{{ post.url }}">{{ post.title }}</a>
    {% endif %}
    </li>
{% endfor %}
</ul>