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

    <span> {{ post.tags | join: ", " }} </span>

{% for tag in post.tags %}
  {% assign t = tag | first %}
<a href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}">{{t}}</a> 
{% endfor %}

    {{ post.content }}
  
  </div>
  {% endfor %}
</div>
