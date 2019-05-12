---
layout: page
title: Posts Feed
desc: "A list of all blog posts"
---



<div class="posts">

  {% for post in site.posts  %}

  <div class="post">

    <h1 class="post-title">
      <a href="{{ site.baseurl }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

    <span class="post-date">- {{ post.date | date_to_string }}</span>

{% for t in post.tags %}
  <a class="button" href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}">{{ t | downcase }}</a>
{% endfor %}
  
  <a href="{{ site.baseurl }}/tag/" class="button"> {{ post.tags | join: ", " }} </a> 

    {{ post.content }}
  
  </div>
  {% endfor %}
</div>
