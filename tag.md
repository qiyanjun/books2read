---
layout: home
title: Book Index (by Tags)
desc: "Posts organized by tags"
---

Click on a tag to see relevant list of posts.

<ul class="tags">
{% assign sorted = site.tags | sort %}
{% for tag in sorted %}
  {% assign t = tag | first %}
  <li><a href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}" class="newBtn">{{ t | downcase }}</a></li>
{% endfor %}
</ul>

---

{% assign sorted = site.tags | sort %}
{% for tag in sorted %}
  {% assign t = tag | first %}
  {% assign posts = site.posts  | sort: 'date' | reverse %}

<h2><a name="{{t | downcase | replace:" ","-" }}"></a><a class="internal" href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}">{{ t | downcase }}</a></h2>

<table id="datatab3" summary="Table of readings" border="1">
<tr>
 <h3><b>
  <th>No.</th>
  <!--<th>Date-Read</th>-->
  <th>Title and Information</th>
  <th>Tags</th>
  </b>
  </h3>
</tr>

<!---<ul>
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    <span class="date">- {{ post.date | date: "%B %-d, %Y"  }}</span>
  </li>
  {% endif %}
{% endfor %}
</ul> -->


{% assign counter = 1 %}

{% for post in posts %}
  {% if post.tags contains t %}

<tr>
<td>{{ counter }}</td>
<!--<td><span class="date"> {{ post.date | date: "%Y, %-b, %-d "  }}</span></td> -->
<td><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }} </a></td>
<td>
    {% for t in post.tags %}
    <a class="button2" href="{{ site.baseurl }}/tag/#{{t | downcase | replace:" ","-" }}">{{ t | downcase }}</a>
  {% endfor %}
</td>
</tr>

  {% assign counter=counter | plus:1 %}

  {% endif %}
{% endfor %}
</table>  

---

{% endfor %}
