---
layout: page
title: Archive
---

### Posts

{% for post in site.posts %}
  * {{ post.date | date: "%B %-d, %Y" }} &raquo; [ {{ post.title}} ]({{ post.url }})
  {% if post.summary %}
      <small>{{ post.summary }}</small>
    {% endif %}
    ---

{% endfor %}
