---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 2
display_categories: [research, coursework, others]
horizontal: true
---

For me, the most alluring aspect of robotics is that you can start with pure mathematical theory, like differential manifolds, and end up screwing in bolts and welding circuits. You can seek out simple mathematical patterns in practical engineering and use elegant mathematical derivations to advance your robots. I love the pure creativity of this process.

对我来说，机器人最有魅力的一点是你可以从纯粹的数学理论例如微分流形一路做到拧螺丝、焊电路。你能够从工程实践中寻找简单的数学规律，并用优雅的数学推导服务于工程突破。我喜欢这种纯粹的创造的过程。

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-1">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}

<!-- Display projects without categories -->

{%- assign sorted_projects = site.projects | sort: "importance" -%}

  <!-- Generate cards for each project -->

{% if page.horizontal -%}

  <div class="container">
    <div class="row row-cols-1">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
