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
  
  <!-- Highlight your last name in the content -->
  {% capture highlighted_content %}
    {{ post.content | replace: "Osman", "<u>Osman</u>" | replace: "M. Osman", "<u>M. Osman</u>" | replace: "Marisol Osman", "<u>Marisol Osman</u>" }}
  {% endcapture %}
  
  <!-- Render the publication with highlighted content -->
  <div>
    {{ highlighted_content }}
  </div>
{% endfor %}


