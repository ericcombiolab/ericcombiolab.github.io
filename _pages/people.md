---
layout: page
title: People
permalink: /people/
description: Our talented lab members!
nav: true
nav_order: 3
display_categories: [Postdoc, Ph.D. Student, RA, Alumni]
horizontal: true
profile_align: right
profile_image: prof_zhang.png
profile_image_circular: false
profile_content: about_ericluzhang.md
profile_cv_pdf: Dr_ZhangLu_C.V.pdf
---

<!-- pages/people.md -->
<div class="projects">
  <a id="PI" href=".#PI">
    <h2 class="category">PI</h2>
  </a>
  
  <div class="profile float-{% if page.profile_align == 'left' %}left{% else %}right{% endif %}">
    {% if page.profile_image %}
      {% assign profile_image_path = page.profile_image | prepend: 'assets/img/' %}
      {% if page.profile_image_circular %}
        {% assign profile_image_class = 'img-fluid z-depth-1 rounded-circle' %}
      {% else %}
        {% assign profile_image_class = 'img-fluid z-depth-1 rounded' %}
      {% endif %}
      {% capture sizes %}(min-width: {{site.max_width}}) {{ site.max_width | minus: 30 | times: 0.3}}px, (min-width: 576px) 30vw, 95vw"{% endcapture %}
      {% include figure.liquid loading="eager" path=profile_image_path class=profile_image_class  zoomable=true %}
    {% endif %}
  </div>
  <div class="clearfix">
    {% if page.profile_content %}
      {% capture profile_content %}{% include_relative {{ page.profile_content }} %}{% endcapture %}
      {{ profile_content | markdownify }}
    {% endif %}

  </div>
  

  <div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
    <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <a id="{{ category }}" href=".#{{ category }}">
        <h2 class="category">{{ category }}</h2>
      </a>
      {% assign categorized_projects = site.people | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 row-cols-md-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.liquid %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="row row-cols-1 row-cols-md-3">
        {% for project in sorted_projects %}
          {% include projects.liquid %}
        {% endfor %}
      </div>
      {% endif %}
    {% endfor %}
  {% else %}
  <!-- Display projects without categories -->
  {% assign sorted_projects = site.people | sort: "importance" %}
    <!-- Generate cards for each project -->

  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
