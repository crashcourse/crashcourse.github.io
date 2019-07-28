---
id: c-programming-101
name: C Programming 101
title: C Programming 101
permalink: /courses/c-programming-101/chapters/
course_permalink: /courses/c-programming-101/

subtext: "Learn programming in C, data structures and algorithms in the best way possible: by working on projects"
thumbnail_path: /static/core/img/course-images/c-programming-square.svg

layout: course_dashboard/base
selected_tab: chapters
title: Chapters | C Programming 101
---

{% assign chapters = site.pages | where: "type", "chapter" %}
{% assign relevant_chapters = chapters | where: "course", "c-programming-101" %}
{% assign sorted_relevant_chapters = relevant_chapters | sort: "order" %}

<section style="padding-top: 1rem; padding-bottom: 8rem;">
    <div class="container-fluid">
      {% for chapter in sorted_relevant_chapters %}
        {% assign remainder = forloop.index | modulo: 3 %}
        {% if remainder == 1 %}
          <div class="row">
          {% endif %}

          <div class="col-lg-4">
            <a href="{{ chapter.permalink }}">
              <div class="course-content-card cc-card-shadow mt-5">
              <span class="small-title gray-text float-right">#{{ forloop.index }}</span>

            <h4 class="title primary-text">
              {{ chapter.name }}
            </h4>

            <p class="subtext">
              {{ chapter.subtext }}
            </p>

            <div class="punch-footer">
              <span class="small-title d-inline-block {% if chapter.difficulty_level == 'ADVANCED' %} pink-text {% elsif chapter.difficulty_level == 'INTERMEDIATE' %} orange-text  {% else %} light-purple-text {% endif %}">
                {{chapter.difficulty_level}}</span>
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
