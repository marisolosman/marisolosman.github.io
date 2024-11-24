---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign current_year = "" %}

{% for post in site.publications reversed %}
  {% assign post_year = post.date | date: "%Y" %}
  
  {% if post_year != current_year %}
  <!-- Add a new year header -->
  <h2>{{ post_year }}</h2>
  {% assign current_year = post_year %}
  {% endif %}
  
  <!-- Render the publication -->
  {% include archive-single.html %}
{% endfor %}


