---
layout: page
permalink: /teaching.html
title: teaching
page-title: Teaching
description: I teach a variety of courses in the Department of Cognitive Science that sit at the intersection of cognition in computing. Many of my courses are part of the Design & Interaction specialization of the Cognitive Science major, as well as the Design Minor. 
nav: true
nav_order: 2
nav_rank: 2
---

{% assign groups = site.classes | sort: "group_rank" | map: "group" | uniq %}
{% for group in groups %}
## {{ group }}

{% assign classes = site.classes | where: "group", group | sort: "group_order" %}
{% for c in classes %}
<p>
  <div class="card hoverable">
    <div class="row no-gutters">

      <div class="col-sm-4 col-md-3">
        {% if c.image %}
          <img
            src="{{ '/assets/img/teaching/' | append: c.image | relative_url }}"
            class="card-img img-fluid"
            alt="{{ c.course_code }} {{ c.course_name }}" />
        {% endif %}
      </div>

      <div class="team col-sm-8 col-md-9">
        <div class="card-body">

          <!-- Title line: CODE + Name -->
          <h5 class="card-title mb-1">
            <span class="mr-2 font-weight-bold">{{ c.course_code }} 
            {{ c.course_name }}
            </span> <br>
            <span>{{ c.course_subtitle }}</span>
          </h5>

          <!-- Term + Credits -->
          <h6 class="card-subtitle mb-2 text-muted">
            {% if c.term %}{{ c.term }}{% endif %}
            {% if c.term and c.credits %} • {% endif %}
            {% if c.credits %}{{ c.credits }} credits{% endif %}
          </h6>

          <!-- Catalog description -->
          {% if c.catalog_description %}
            <p class="card-text mb-2">
              <strong>Catalog:</strong> {{ c.catalog_description }}
            </p>
          {% endif %}

          <!-- Your custom description (from body) -->
          {% if c.content %}
             <div class="card-text mb-2">
              <strong>Instructor note:</strong>
             <div class="font-italic">
              {{ c.content | markdownify }}
             </div>
                </div>
            {% endif %}


          <!-- Tags / requirements -->
          {% if c.tags %}
            <p class="card-text mb-2">
              {% for tag in c.tags %}
                <span class="badge badge-course mr-1 mb-1">{{ tag }}</span>
              {% endfor %}
            </p>
          {% endif %}

          <!-- Links -->
          <p class="card-text mb-0">
            {% if c.links.syllabus %}
              <a class="card-link" href="{{ c.links.syllabus | relative_url }}" target="_blank">
                <i class="fas  fa-book"></i> Recent Syllabus
              </a>
            {% endif %}

            {% if c.links.evaluation %}
              <a class="card-link" href="{{ c.links.evaluation | relative_url }}" target="_blank">
                <i class="fas fa-chart-bar"></i> Student Evaluations
              </a>
            {% endif %}
          </p>

        </div>
      </div>

    </div>
  </div>
</p>
{% endfor %}
{% endfor %}
