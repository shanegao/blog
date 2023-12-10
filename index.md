---
layout: default
title: Shane's Blog
tagline: 
---
{% include JB/setup %}
<div id="posts">
	{% for post in site.posts offset: 0 limit: 10 %}
        <h2><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>
        {{ post.date | date_to_string }}
        {{ post.content }}
    {% endfor %}	
</div>



