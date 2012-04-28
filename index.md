---
layout: page
title: 大熊的Blog! 
tagline: Contiunous Learning 
---
#### About Me
    Name : Lin Zhixiong 
    Email : darlinglele@gmail.com 
    Github : https://github.com/darlinglele 

#### Recently Posts
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo;<strong> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></strong></li>

    {{ post.content }} {% endfor %}
</ul>

