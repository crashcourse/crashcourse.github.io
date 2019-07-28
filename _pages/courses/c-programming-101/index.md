---
id: c-programming-101
name: C Programming 101
title: C Programming 101
permalink: /courses/c-programming-101/
course_permalink: /courses/c-programming-101/

subtext: "Learn programming in C, data structures and algorithms in the best way possible: by working on projects"
thumbnail_path: /static/core/img/course-images/c-programming-square.svg

layout: course_dashboard/base
selected_tab: projects
title: Projects | C Programming 101
---

{% assign projects = site.pages | where: "type", "project" %}
{% assign relevant_projects = projects | where: "course", "c-programming-101" %}
{% assign sorted_relevant_projects = projects | sort: "order" %}

<section style="padding-top: 1rem; padding-bottom: 8rem;">
    <div class="container-fluid">
      {% for project in sorted_relevant_projects %}
        {% assign remainder = forloop.index | modulo: 3 %}
        {% if remainder == 1 %}
          <div class="row">
          {% endif %}

          <div class="col-lg-4">
            <a href="{{ project.permalink }}">
              <div class="course-content-card cc-card-shadow mt-5">
              <span class="small-title gray-text float-right">#{{ forloop.index }}</span>

            <h4 class="title primary-text">
              {{ project.name }}
            </h4>

            <p class="subtext">
              {{ project.subtext }}
            </p>

            <div class="punch-footer">
              <span class="small-title d-inline-block {% if project.difficulty_level == 'ADVANCED' %} pink-text {% else if project.difficulty_level == 'INTERMEDIATE' %} orange-text  {% else %} light-purple-text {% endif %}">
                {{project.difficulty_level}}</span>
            </div>
          </div>
        </a>
      </div>

      {% if remainder == 0 or forloop.last %}
      </div>
    {% endif %}

  {% endfor %}
</div>
</section>
