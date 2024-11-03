---
layout: page
title: Assignments
description: Listing of assignments
---

# My Assignments

{% assign custom_order = "assignment-0,assignment-1,assignment-2,assignment-3,assignment-4,assignment-5,midterm,assignment-6" | split: ',' %}

{% for name in custom_order %}
  {% assign assignment = site.assignments | where: 'slug', name | first %}
  {% if assignment %}
    <div class="assignment">
      <h2>{{ assignment.title }}</h2>
      <p>{{ assignment.description }}</p>
    </div>
  {% endif %}
{% endfor %}