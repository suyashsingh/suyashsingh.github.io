---
title: Blog
layout: default
order: 2
---

{% for post in site.posts %}
  <div class="card border-light">
    <div class="card-body">
      <h1 class="card-title"><a href="{{ post.url }}">{{ post.title}}</a></h1>
      <p class="card-text">
      <a href="#" class="fa fa-clock-o" onclick="return false"></a>{{ post.readTime }} read | 
       <a href="#" class="fa fa-calendar" onclick="return false"></a>{{ post.date | date: "%b %-d, %Y" }} |
       <a href="#" class="fa fa-list-alt" onclick="return false"></a>{{ post.category }}<br>
       <a href="#" class="fa fa-tag" onclick="return false"></a>
       <span class="badge badge-info">{{ post.tag }}</span>
      </p>
      <a href="{{ post.url }}" class="btn btn-outline-success">Read More <span href="#" class="fa fa-arrow-circle-o-right" onclick="return false"></span></a>
    </div>  
  </div>
{% endfor %}
