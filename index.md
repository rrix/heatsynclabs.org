---
layout: page
title: Hacker's Ramblings
---
{% include JB/setup %}

{% for post in site.posts limit:10 %}

[{{post.title}}]({{ BASE_PATH }}{{ post.url }})
------------

{{ post.date | date_to_string }} &raquo; [{{ post.title }}]("{{ BASE_PATH }}{{ post.url }}")

{{ post.content }}

{% endfor %}



