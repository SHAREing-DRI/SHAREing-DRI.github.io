---
permalink: /workpackages-map/
title: "Task Map"
layout: single
sidebar: false
classes: wide page__center no-title
layout: default
---


<style>
.task-map { display: flex; flex-direction: column; gap: 60px; }

.wp-row { margin-bottom: 50px; }

.wp-row h2 {
  color:#003d66;
  border-bottom:2px solid #ccc;
  padding-bottom:6px;
}

.kanban {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 14px;
  margin-top: 15px;
}

.column {
  background:#f4f6f9;
  border-radius:6px;
  padding:10px;
  min-height:200px;
}

.column h3 {
  text-align: center;
  color:white;
  padding:6px;
  border-radius:4px;
}

.open-col h3 { background:#B906B9; }
.progress-col h3 { background:#940594; }
.propose-col h3 { background:#4c7bd9; }
.completed-col h3 { background:#490349; }

.task {
  background:white;
  border-radius:4px;
  padding:8px;
  margin:6px 0;
  font-size:0.9rem;
}

.task a {
  text-decoration:none;
  color:#003d66;
}

.task:hover { box-shadow:0 2px 6px rgba(0,0,0,0.1); }
</style>

<div class="task-map">

{% assign wp_list = "wp1.1,wp1.2,wp1.3" | split: "," %}

{% for wp in wp_list %}

{% assign open = site.tasks | where:"workpackage",wp | where:"status","open" %}
{% assign progress = site.tasks | where:"workpackage",wp | where:"status","progress" %}
{% assign propose = site.tasks | where:"workpackage",wp | where:"status","propose" %}
{% assign completed = site.tasks | where:"workpackage",wp | where:"status","completed" %}

<div class="wp-row">
  <h2>{{ wp | upcase }}</h2>

  <div class="kanban">

    <div class="column open-col">
      <h3>Open</h3>
      {% for task in open %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
      {% if open.size == 0 %}<div class="task">No tasks</div>{% endif %}
    </div>

    <div class="column progress-col">
      <h3>Ongoing</h3>
      {% for task in progress %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
      {% if progress.size == 0 %}<div class="task">No tasks</div>{% endif %}
    </div>

    <div class="column propose-col">
      <h3>Propose</h3>
      {% for task in propose %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
      {% if propose.size == 0 %}<div class="task">—</div>{% endif %}
    </div>

    <div class="column completed-col">
      <h3>Completed</h3>
      {% for task in completed %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
      {% if completed.size == 0 %}<div class="task">—</div>{% endif %}
    </div>

  </div>
</div>

{% endfor %}

</div>




