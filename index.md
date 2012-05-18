---
layout: page
title: 一大只熊的Blog! 
tagline: Contiunous Learning 
---
#### About Me
    Name : Lin Zhixiong 
    Email : darlinglele@gmail.com 
    Github : https://github.com/darlinglele 

#### Recently Posts
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo;<h3> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3></li>

    {{ post.content }} {% endfor %}
</ul>

