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

<ul class="tags">
{% assign sorted = post.tags | sort %}
{% for tag in sorted %}
  {% assign t = tag | first %}
  <li><a href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}" class="newBtn">{{ t | downcase }}</a></li>
{% endfor %}
</ul>

    {{ post.content }}
  </div>
  {% endfor %}
</div>
