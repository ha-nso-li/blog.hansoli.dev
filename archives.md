---
layout: post
title: Archives
permalink: /archives/
content-type: eg
---

<style>
.date-content a {
    text-decoration: none;
    color: #4183c4;
}

.date-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<main>
    {% assign postsByMonth = site.posts | group_by_exp:"post", "post.date | date: '%B %Y'" %}

    {% for month in postsByMonth %}
      <h3 id="{{ month.name }}">{{ month.name }}</h3>
          {% for post in month.items %}
            <li id="date-content" style="padding-bottom: 0.6em; list-style: none;"><a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
    {% endfor %}

        <br/>
        <br/>
</main>
