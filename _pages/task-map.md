---
permalink: /task-map/
title: "Task Map"
layout: default
sidebar: false
classes: wide page__center no-title
---

<style>

.wp-columns {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 35px;
  width: 100%;
  max-width: 1600px;
  margin: 0 auto;
  padding: 10px 20px;
}

@media (min-width: 1800px) {
  .wp-columns {
    max-width: 95vw;
    padding-left: 2vw;
    padding-right: 2vw;
  }
}

.wp-column {
  background: #ffffff;
  border-radius: 16px;
  padding: 22px 22px 30px;
  box-shadow: 0 6px 18px rgba(0,0,0,0.05);
}

/* Column titles */
.wp-column-title {
  font-size: 1.4rem;
  font-weight: 700;
  text-align: center;
  padding-bottom: 10px;
  margin-bottom: 25px;
  color: #003d66;
}

.wp-main-number {
  font-size: 2rem;
  font-weight: 700;
  color: #003d66;
}

.wp-main-subtitle {
  font-size: 1.2rem;
  font-weight: 500;
  color: #555;
  margin-top: 5px;
}

/* Subgroup block */
.wp-subblock {
  border-radius: 10px;
  padding: 15px;
  margin: 20px 0;
  background: #FDF6FF;
  border: 5px solid #F0DEF5;
}

/* Header section */
.wp-subblock-header {
  display: flex;
  align-items: left;
  gap: 15px;
  margin-bottom: 15px;
  justify-content: flex-start;
}

.wp-lead-photo {
  width: 85px;
  height: 85px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  background-color: #f0f0f0;
}

.wp-subblock-text {
  display: flex;
  flex-direction: column;
}

.wp-subtitle {
  font-size: 1.15rem;
  font-weight: 600;
  color: #003d66;
}

.wp-lead {
  font-size: 0.9rem;
  color: #555;
  font-style: italic;
  margin-top: 3px;
}

/* Kanban */
.kanban {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
  margin-top: 10px;
}

.column {
  background: #ffffff;
  padding: 12px;
  border-radius: 10px;
  border: 1px solid #eee;
}

.column h3 {
  font-size: 0.85rem;
  text-transform: uppercase;
  color: white;
  padding: 6px;
  border-radius: 6px;
  text-align: center;
  margin-bottom: 10px;
}

.open-col h3 { background:#B906B9; }
.progress-col h3 { background:#940594; }
.completed-col h3 { background:#490349; }

.task {
  background:#ffffff;
  border-radius: 8px;
  padding: 10px;
  font-size: 0.85rem;
  margin-bottom: 8px;
  box-shadow: 0 1px 4px rgba(0,0,0,0.05);
  border: 2px solid #EAEAEA;
  font-weight: 700;
}

.task a {
  text-decoration: none;
  color: #003d66;
}

.propose-task {
  margin-top: 12px;
  text-align: center;
  padding: 10px 0;
  color: #ffffff;
}

.propose-task-link {
  display: block;
  padding: 6px 6px;
  font-size: 0.85rem;
  font-weight: 600;
  border-radius: 6px;
  background: #003d66;
  color: #fff;
  text-decoration: none;
  transition: all 0.2s ease;
  color: #ffffff !important;
  text-shadow: none !important;
  box-shadow: none !important;
}

.propose-task-link:hover {
  background: #CDA3CD !important;
  border-color: #CDA3CD !important;
  color: #ffffff !important;
}


/* Task hover shadows by category */
.open-col .task:hover {
  box-shadow: 0 0 10px rgba(185, 6, 185, 0.45);
  border-color: #B906B9;
  background: rgba(185, 6, 185, 0.08);
  transform: translateY(-2px);
  transition: all 0.2s ease;
}

.progress-col .task:hover {
  box-shadow: 0 0 10px rgba(148, 5, 148, 0.45);
  border-color: #940594;
  background: rgba(148, 5, 148, 0.08);
  transform: translateY(-2px);
  transition: all 0.2s ease;
}

.completed-col .task:hover {
  box-shadow: 0 0 10px rgba(73, 3, 73, 0.45);
  border-color: #490349;
  background: rgba(73, 3, 73, 0.08);
  transform: translateY(-2px);
  transition: all 0.2s ease;
}

@media (max-width: 1100px) {
  .wp-columns {
    grid-template-columns: 1fr;
  }
}


</style>

<div class="wp-columns">

{% assign wp_groups =
  "wp1:wp1.1,wp1.2,wp1.3|
   wp2:wp2.3,wp2.4|
   wp3:wp3.3,wp3.4" | split:"|" %}

{% for group in wp_groups %}

  {% assign parts = group | split:":" %}
  {% assign wp_main = parts[0] | strip %}
  {% assign wp_list = parts[1] | split:"," %}
  {% assign wp_number = wp_main | replace:"wp","" %}

  <!-- Find WP collection file: WP1.md, WP2.md, WP3.md -->
  {% assign wp_filename = "WP" | append: wp_number | append: ".md" %}
  {% assign wp_page = site.workpackages | where:"path", wp_filename | first %}

  <!-- If 'path' doesn't match because of subdirectory under 'collections/' -->
  {% if wp_page == nil %}
    {% assign wp_page = site.workpackages | where_exp:"p","p.path contains wp_filename" | first %}
  {% endif %}

  <!-- Correct permalink to user-facing page in _pages/workpackages/ -->
  {% assign wp_target = "/workpackages/workpackage-" | append: wp_number | append:"/" %}

  <div class="wp-column">

    <!-- MAIN WP HEADER -->
    <div class="wp-column-title">
      <a href="{{ wp_target }}">
        <div class="wp-main-number">Work Package {{ wp_number }}</div>
        <div class="wp-main-subtitle">{{ wp_page.title }}</div>
      </a>
    </div>

    {% assign wp_file = "workpackages-" | append: wp_number | append: "-team-lead" %}

    {% for wp in wp_list %}

      {% assign meta = site.data[wp_file][wp] %}
      {% assign open = site.tasks | where:"workpackage",wp | where:"status","open" %}
      {% assign progress = site.tasks | where:"workpackage",wp | where:"status","progress" %}
      {% assign completed = site.tasks | where:"workpackage",wp | where:"status","completed" %}

      <!-- SUBGROUP BLOCK -->
      <div class="wp-subblock">

        <!-- Header section -->
        <div class="wp-subblock-header">
          <img src="{{ meta.lead_photo }}" alt="{{ meta.lead }}" class="wp-lead-photo">
          <div class="wp-subblock-text">
            <div class="wp-subtitle">{{ meta.title }}</div>
            <div class="wp-lead"><strong>Lead:</strong> {{ meta.lead }}</div>
          </div>
        </div>

        <!-- Kanban -->
        <div class="kanban">
          <div class="column open-col">
            <h3>Open</h3>
            {% if open.size > 0 %}
              {% for task in open %}
                <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
              {% endfor %}
            {% endif %}
          </div>

          <div class="column progress-col">
            <h3>Ongoing</h3>
            {% if progress.size > 0 %}
              {% for task in progress %}
                <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
              {% endfor %}
            {% endif %}
          </div>

          <div class="column completed-col">
            <h3>Completed</h3>
            {% if completed.size > 0 %}
              {% for task in completed %}
                <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
              {% endfor %}
            {% endif %}
          </div>
          

    <div class="propose-task" style="grid-column: 1 / 4; width: 100%;">
  <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=i9hQcmhLKUW-RNWaLYpvlBhRpzyeDrFBkd8HIFx_xpdUN0ZMWlk5N1lYSVVORldSTllSSTFWWFYzNS4u"
     class="propose-task-link"
     target="_blank"
     rel="noopener">
    Propose your task for {{ wp | upcase }}
  </a>
</div>

  </div>

</div>

    {% endfor %}

  </div>

{% endfor %}

</div>

