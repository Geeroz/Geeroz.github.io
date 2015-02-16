---
layout: page
title: Geeroz's Blog
tagline: blog about art & technology
---
{% include JB/setup %}

<div class="row">
{% for post in site.posts limit:10 %}
  <div class="panel panel-default">
  <div class="panel-heading">
    <a href="{{ BASE_PATH }}{{ post.url }}"><h2>{{ post.title }}</h2></a>
    <span class="label label-default">{{ post.date }}</span>
    <span class="glyphicon glyphicon-list" aria-hidden="true"></span>
    <span class="label label-info">{{ post.categories }}</span>
    <span class="glyphicon glyphicon-tag" aria-hidden="true"></span>
    {% for tag in post.tags %}
      <span class="label label-default">{{ tag }}</span>
    {% endfor %}
  </div>
    <div class="panel-body">
      {% if post.content contains "<!--more-->" %}
          {{ post.content | split:"<!--more-->" | first % }}
      {% else %}
        {{ post.content | strip_html | truncatewords:100 }}
      {% endif %}
      <p>
      <a class="btn" href="{{ BASE_PATH }}{{ post.url }}">Read more...</a>
      </p>
    </div>

  </div>
{% endfor %}
</div>
