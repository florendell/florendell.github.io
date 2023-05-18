---
layout: page
title: Research
permalink: /projects/
description: My research focuses on understanding the extent and impacts of anthropogenic contamination on freshwater biota, in particular documenting the uptake and ecotoxicological impacts of microplastics. My research and laboratory skills lie in ecotoxicology, spectral analysis of synthetic particles, isolating microplastics from complex organic matrices and animal husbandry. Check out the projects below to find out more! 
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

*Research Background and Training*
  + Microplastic analysis applying micro-FTIR imaging, ATR-FTIR and other techniques (Aalborg University, Department of Civil Engineering)
  - Adverse Outcome Pathways in Environmental Toxicology practical applications, methods and challenges (Norwegian University of Science and Technology)
  * Creative Technologies Upskilling Module (Dundee Univeristy)
  + Electrofishing training 
  + Scottish Accreditation Board Home Office Personal Licence (March 2021) in Marine and Freshwater Fish 
  * Communicating Scientific Research 
  
  *Key research competencies*
  + Statisical coding in R studio, Python with applications to Raspberry Pis and Arduino
  * Microscopy work includes micro-FTIR, Confocal
  - Aquatic husbandry with sea urchins, lamprey, fish eggs, home office licence
  - GIS ArcGIS/QGIS

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
    <div class="row row-cols-2">
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
    <div class="row row-cols-2">
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
