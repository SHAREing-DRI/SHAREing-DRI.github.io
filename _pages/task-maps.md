---
permalink: /task-maps/
title: "Task Map"
layout: default
sidebar: false
classes: wide page__center no-title
---

<style>


.wp-columns {
  display: grid;
  grid-template-columns: repeat(4, minmax(200px, 1fr)); /* ancho mínimo 200px */
  gap: 12px;             
  width: 100%;
  max-width: 1400px;      
  margin: 0 auto;
  padding: 8px;
  align-items: start; /* fuerza que las columnas empiecen arriba */
}

@media (max-width: 1600px) {
  .wp-columns {
    grid-template-columns: repeat(4, 1fr);
  }
}


@media (max-width: 1100px) {
  .wp-columns {
    grid-template-columns: 1fr;
  }
}


@media (max-width: 1100px) {
  .wp-columns {
    grid-template-columns: 1fr;
  }
}


.wp-column {
  background: #ffffff;
  border-radius: 12px;
  padding: 10px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  border-top: 4px solid #68246d;
  display: flex;
  flex-direction: column;
  height: auto; /* permite que crezca según contenido */
}


.wp-column-title {
  font-size: 1.35rem;
  font-weight: 700;
  text-align: center;
  padding-bottom: 10px;
  margin-bottom: 20px;
  color: #003d66;
    font-size: 1.15rem;
  margin-bottom: 18px;
}

.wp-main-number {
  font-size: 1.55rem;
  font-weight: 700;
  color: #003d66;
 
}

.wp-main-subtitle {
  font-size: 1rem;
  font-weight: 500;
  color: #555;
  margin-top: 5px;
}


.wp-subblocks-wrapper {
  display: grid;
  grid-template-columns: 1fr; /* cada subgrupo ocupa toda la columna del WP */
  row-gap: 12px;
}

.wp-subblock {
  background: #FDF6FF;
  border: 3px solid #F0DEF5;
  border-radius: 8px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start; /* asegura que el contenido empiece arriba */
}


.wp-subblock-header {
  display: flex;
  gap: 10px;
  align-items: flex-start;
  margin-bottom: 12px;
}

.wp-lead-photo {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
  background-color: #f0f0f0;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}

.wp-subblock-text {
  display: flex;
  flex-direction: column;
  
}

.wp-subtitle {
  font-size: 0.6rem;
  font-weight: 600;
  color: #003d66;
}

.wp-lead {
  font-size: 0.8rem;
  color: #555;
  font-style: italic;
  margin-top: 3px;
}

.wp-content {
  font-size: 0.4rem;
  color: #555;
  font-style: italic;
  margin-top: 3px;
}

.kanban {
  display: flex;
  gap: 12px;
  margin-top: 8px;
  flex-wrap: nowrap;     /* No se bajan */
  overflow-x: auto;      /* Scroll horizontal si hace falta */
}

.column {
  flex: 1 1 120px;       /* ancho mínimo 120px */
  display: flex;
  flex-direction: column; 
}

/* Botón debajo */
.propose-task {
  margin-top: 12px;      /* espacio con la kanban */
  text-align: center;
  width: 100%;
}

.column h3 {
  font-size: 0.7rem;
  text-transform: uppercase;
  color: white;
  padding: 5px;
  border-radius: 6px;
  text-align: center;
  margin-bottom: 8px;
}

.open-col h3 { background:#B906B9; }
.progress-col h3 { background:#940594; }
.completed-col h3 { background:#490349; }

.task {
  background:#ffffff;
  border-radius: 6px;
  padding: 7px;
  font-size: 0.7rem;
  margin-bottom: 6px;
  border: 2px solid #EAEAEA;
  box-shadow: 0 1px 4px rgba(0,0,0,0.05);
  font-weight: 700;
}

.task a {
  text-decoration: none;
  color: #003d66;
  font-size: 0.6rem;
  line-height: 0.2;  
}

.tasks-wrapper .extra-task {
  display: none;  /* Oculta tareas extra */
}

.tasks-wrapper.expanded .extra-task {
  display: block; /* Muestra cuando se expande */
}

.toggle-tasks {
  display: inline-block;
  margin-top: 5px;
  padding: 4px 8px;
  font-size: 0.7rem;
  font-weight: 600;
  border-radius: 4px;
  background: #003d66;
  color: #fff;
  border: none;
  cursor: pointer;
  transition: all 0.2s ease;
}

.toggle-tasks:hover {
  background: #68246d;
}



.propose-task {
  margin-top: 10px;
  text-align: center;
  padding: 10px 0;
  color: #ffffff;
}

.propose-task-link {
  display: block;
  padding: 5px;
  font-size: 0.75rem;
  font-weight: 600;
  border-radius: 5px;
  background: #003d66;
  color: #ffffff !important;
  text-decoration: none;
  transition: all 0.2s ease;
}

.propose-task-link:hover {
  background: #CDA3CD !important;
  border-color: #CDA3CD !important;
}


/* ===== TASK HOVER EFFECTS ===== */

.open-col .task:hover {
  box-shadow: 0 0 10px rgba(185, 6, 185, 0.45);
  border-color: #B906B9;
  background: rgba(185, 6, 185, 0.08);
  transform: translateY(-2px);
}

.progress-col .task:hover {
  box-shadow: 0 0 10px rgba(148, 5, 148, 0.45);
  border-color: #940594;
  background: rgba(148, 5, 148, 0.08);
  transform: translateY(-2px);
}

.completed-col .task:hover {
  box-shadow: 0 0 10px rgba(73, 3, 73, 0.45);
  border-color: #490349;
  background: rgba(73, 3, 73, 0.08);
  transform: translateY(-2px);
}
.eligibility-box {
 
  font-size: 0.7rem !important;      
  color: #333 !important;               
  line-height: 1.4 !important;
  margin: 1rem 0 !important;         
  display: block !important;            
}
.eligibility-box strong {
  font-weight: 600 !important;
}

</style>


<div style="max-width:1400px; margin:0 auto; padding:0 15px; display:flex; flex-direction:column; gap:0.5rem; margin-top:0.01rem">

  <!-- Open Tasks Card -->
  <div style="background:#f7f9fc; border-left:8px solid #B906B9; padding:0.5rem 0.75rem; border-radius:6px; margin-top:1rem;">
    <h3 style="margin:0; color:#002A41; font-size:16px;">Open Tasks</h3>
    <p style="margin:0; line-height:1.4; font-size:12px;">
      These are tasks already defined by the SHAREing Working Groups (WPs). They are published and ready for applications. Anyone interested <strong>can apply to take them on</strong>. Open Tasks are like mini-projects with clear goals and scope — your role is to help deliver them according to the WP plan.
    </p>
  </div>

  <!-- Propose a Task Card -->
  <div style="background:#f7f9fc; border-left:8px solid #005a9c; padding:0.5rem 0.75rem; border-radius:6px;">
    <h3 style="margin:0; color:#002A41; font-size:16px;">Suggest a New Task</h3>
    <p style="margin:0; line-height:1.4; font-size:12px;">
      Have an idea that could benefit SHAREing? Use this option to submit a task proposal. Focus on <strong>what</strong> you want to do and <strong>why</strong> it matters for SHAREing and the WPs.
      <br>
      Your proposal will be reviewed by the relevant WP. If approved, it will become an Open Task listed on the website, open for anyone to apply. As the person who suggested the task, <strong>you will have priority to lead it</strong>, but others can also apply if interested. At this stage, there’s no need to include costings or detailed plans — just provide a clear description and show how the task aligns with SHAREing’s goals. The detailed “how” and paperwork will be part of the formal bid later.
    </p>
  </div>

  <!-- Eligibility Box -->
  <div class="eligibility-box" style="max-width:100%">
    ⚠️ <strong>Eligibility:</strong> At this time, only dRTP members who are formally affiliated with one of the SHAREing consortium universities and institutions: Durham, Manchester, Queen Mary University of London, Swansea, Cardiff, CoSeC, or Sheffield can submit or propose tasks.
  </div>

</div>




<div class="wp-columns">

{% assign wp_groups =
  "wp1:wp1.1,wp1.2,wp1.3,wp1.4,wp1.5|
   wp2:wp2.1,wp2.2,wp2.3,wp2.4,wp2.5,wp2.6,wp2.7,wp2.8|
   wp3:wp3.1,wp3.2,wp3.3,wp3.4,wp3.5,wp3.6,wp3.7,wp3.8|
    wp4:wp4.1,wp4.2,wp4.3,wp4.4" | split:"|" %}

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

<!-- WP LEAD BLOCK -->

{% assign wp_file = "workpackages-" | append: wp_number | append: "-team-lead" %}
{% assign wp_lead_data = site.data[wp_file] %}

<div class="wp-lead-block" style="display:flex; align-items:center; font-size:0.8rem; gap:12px; background:#FDF6FF; padding:8px 12px; border-radius:10px; border:1px solid #F0DEF5; margin-bottom:12px;">
  <img src="{{ wp_lead_data.lead_photo }}" alt="{{ wp_lead_data.lead-wp }}" style="width:50px; height:50px; border-radius:50%; object-fit:cover;">
  <div style="display:flex; flex-direction:column;">
    <div style="font-weight:600; color:#003d66;">{{ wp_lead_data.lead-wp }}</div>
  </div>
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
         
          <div class="wp-subblock-text">
            <div class="wp-subtitle">{{ meta.title }}</div>
          
          </div>
        </div>

        <!-- Kanban -->
        <div class="kanban">
<div class="column open-col">
  <h3>Open</h3>
  {% assign num_to_show = 2 %}
  {% if open.size > 0 %}
    <div class="tasks-wrapper">
      {% for task in open limit:num_to_show %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}

      {% assign extra_tasks = open | slice: num_to_show, open.size %}
      {% for task in extra_tasks %}
        <div class="task extra-task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
    </div>

    {% if open.size > num_to_show %}
      <button class="toggle-tasks">Show more</button>
    {% endif %}
  {% endif %}
</div>








<div class="column progress-col">
  <h3>Progress</h3>
  {% assign num_to_show = 2 %}
  {% if progress.size > 0 %}
    <div class="tasks-wrapper">
      {% for task in progress limit:num_to_show %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}

      {% assign extra_tasks = progress | slice: num_to_show, progress.size %}
      {% for task in extra_tasks %}
        <div class="task extra-task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
    </div>

    {% if progress.size > num_to_show %}
      <button class="toggle-tasks">Show more</button>
    {% endif %}
  {% endif %}
</div>






<div class="column completed-col">
  <h3>Completed</h3>
  {% assign num_to_show = 2 %}
  {% if completed.size > 0 %}
    <div class="tasks-wrapper">
      {% for task in completed limit:num_to_show %}
        <div class="task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}

      {% assign extra_tasks = completed | slice: num_to_show, completed.size %}
      {% for task in extra_tasks %}
        <div class="task extra-task"><a href="{{ task.url }}">{{ task.title }}</a></div>
      {% endfor %}
    </div>

    {% if completed.size > num_to_show %}
      <button class="toggle-tasks">Show more</button>
    {% endif %}
  {% endif %}
</div>

          

<!-- Kanban de tareas -->
<div class="kanban">
  <div class="column open-col">...</div>
  <div class="column progress-col">...</div>
  <div class="column completed-col">...</div>
</div>

<!-- Botón de sugerir, siempre debajo -->
<div class="propose-task">
  <a href="..." class="propose-task-link" target="_blank" rel="noopener">
    Suggest a new task for {{ wp | upcase }}
  </a>
</div>


  </div>

</div>

    {% endfor %}

  </div>

{% endfor %}

</div>



<script>

document.addEventListener("DOMContentLoaded", function() {
  document.querySelectorAll(".toggle-tasks").forEach(function(button) {
    button.addEventListener("click", function() {
      const wrapper = this.previousElementSibling; // tasks-wrapper
      wrapper.classList.toggle("expanded");
      this.textContent = wrapper.classList.contains("expanded") ? "Show less" : "Show more";
    });
  });
});

</script>

