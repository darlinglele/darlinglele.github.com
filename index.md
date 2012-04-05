---
layout: page
title: Darlinglele' Blog! 
tagline: Contiunous Learning 
---
## About Me
    Name : Lin Zhixiong 
    Email : darlinglele@gmail.com 
    Github : darlinglele 
## Recently Posts
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>

    {{ post.content }} {% endfor %}
</ul>

