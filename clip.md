---
title: Clips
layout: page
---

<p>
Shorter notes, links, and thoughts. This is where I collect, where I organize, and where I think.
</p>
  {% for post in site.posts %}



    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

   {% if post.categories contains 'clips' %}
    <p><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a><small> • {{ post.date | date: site.date_format }}</small></p>
         {% endif %}
  {% endfor %}