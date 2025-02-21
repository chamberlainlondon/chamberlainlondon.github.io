---
layout: archive
title: "Portfolio"
permalink: /portfolio/
author_profile: true
---
------
{% include base_path %}

<h2>Work Projects</h2>
{% for post in site.portfolio reversed %}
  {% if post.pubtype == 'work' %}
      {% include archive-single.html %}
  {% endif %}
{% endfor %}

<h2>Personal Projects</h2>
{% for post in site.portfolio reversed %}
  {% if post.pubtype == 'personal' %}
      {% include archive-single.html %}
  {% endif %}
{% endfor %}

<h2>Case Competitions</h2>
{% for post in site.portfolio reversed %}
  {% if post.pubtype == 'cases' %}
      {% include archive-single.html %}
  {% endif %}
{% endfor %}
