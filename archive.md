---
layout: page
title: Archive
published: true
---

{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%Y"}}{% endcapture %}
  {% if currentyear != year %}
   {% unless forloop.first %}</ul>{% endunless %}
<h2>{{ currentyear }}</h2>
<ul>
    {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}
  {% if {{post.tag == null}} %}
<li>{{post.date | date: "%b %-d"}} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endif %}
{% endfor %}
{% if site.posts.size != 0 %}</ul>{% endif %}
