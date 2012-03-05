---
layout: page
title: HeatSync Labs
group: header
---
{% include JB/setup %}

{% for post in site.posts limit:10 %}

[{{post.title}}]({{ BASE_PATH }}{{ post.url }})
------------

&raquo; {{ post.date | date_to_string }} 

{{ post.content }}

{% endfor %}



