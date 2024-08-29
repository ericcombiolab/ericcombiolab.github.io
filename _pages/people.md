---
layout: page
title: People
permalink: /people/
description: Group members.
nav: true
nav_order: 3
display_categories: [Postdoc, Ph.D. Student, RA, Alumni]
horizontal: false

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - align: right
    image: prof_zhang.png
    content: about_ericluzhang.md
    more_info: >
    Address: Department of Computer Science, DLB 629, Level 6, David C. Lam Building Shaw Campus, 
            Hong Kong Baptist University Kowloon Tong, Hong Kong
    Tel: 852-3411-5880    Email: ericluzhang at hkbu.edu.hk

---

<!-- pages/people.md -->

<div >
{% if page.profiles %}
  {% for profile in page.profiles %}
    <hr>
    <div class="profile float-{% if profile.align == 'left' %}left{% else %}right{% endif %}">
      {% if profile.image %}
        {% assign profile_image_path = profile.image | prepend: 'assets/img/' %}
        {% if profile.image_circular %}
          {% assign profile_image_class = 'img-fluid z-depth-1 rounded-circle' %}
        {% else %}
          {% assign profile_image_class = 'img-fluid z-depth-1 rounded' %}
        {% endif %}
        {% capture sizes %}(min-width: {{site.max_width}}) {{ site.max_width | minus: 30 | times: 0.3}}px, (min-width: 576px) 30vw, 95vw"{% endcapture %}
        {% include figure.liquid loading="eager" path=profile_image_path class=profile_image_class sizes=sizes alt=profile.image %}
      {% endif %}
      {% if profile.more_info %}
        <div class="more-info">{{ profile.more_info }}</div>
      {% endif %}
    </div>

    <div class="clearfix">
      {% if profile.content %}
        {% capture profile_content %}{% include_relative {{ profile.content }} %}{% endcapture %}
        {{ profile_content | markdownify }}
      {% else %}
        {{ content }}
      {% endif %}
    </div>
  {% endfor %}
{% endif %}
</div>
