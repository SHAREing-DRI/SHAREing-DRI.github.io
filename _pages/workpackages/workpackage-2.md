---
permalink: /workpackages/workpackage-2/
title: "Workpackage 2: Technical training"
classes: wide
layout: splash
---
<style>
/* WORKPACKAGE BASE STYLES*/
.wp-section {
  background: #f7f9fc;
  border-left: 4px solid #005a9c;
  border-radius: 8px;
  padding: 1.5rem 2rem;
  margin-bottom: 3rem;
}

.wp-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.wp-header img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  border: 2px solid #005a9c;
  object-fit: cover;
}

.workpackages-header {
  text-align: center;
  margin: 1.5rem 0 2rem 0;
  font-size: 1.5rem;
}

.wp-title {
  font-size: 1.8rem !important;
  font-weight: 800 !important;
  color: #002A41 !important;
  margin: 0 !important;
  line-height: 1.1;
}

.wp-lead {
  font-size: 1.5rem !important;
  color: #555;
  margin-top: 0.2rem;
}

.wp-purpose {
  font-size: 1rem;
  margin-bottom: 1rem;
  color: #333;
}

/* TASK CARDS  */
.task-card {
  background: #ffffff;
  border: 1px solid #e4e4e4;
  border-radius: 8px;
  padding: 1rem 1.5rem;
  margin-bottom: 0.75rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: box-shadow 0.2s;
}

.task-card:hover {
  box-shadow: 0 2px 10px rgba(0,0,0,0.08);
}

.apply-btn {
  padding: 0.5rem 1rem;
  background: #005a9c;
  color: white;
  text-decoration: none;
  border-radius: 5px;
  font-weight: 600;
}

.apply-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    color: #ffffff;
}


/* ACCORDION */
.accordion-btn {
  width: 100%;
  background: #f4f6f9;
  border: #002A41;
  padding: 14px;
  font-weight: bold;
  text-align: left;
  cursor: pointer;
  border-top: 1px solid #d9dee6;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.accordion-btn.active {
  background: #e9edf3;
}

.accordion-panel {
  display: none;
  padding: 10px 0 5px;
}

.arrow {
  font-size: 14px;
}


/* TAB COLOURS BY TYPE */

.open-tab {
  background-color: #D7DEE9;
  border-left: 20px solid #B906B9;
}
.open-tab.active {
  background-color: #D7DEE9;
}
.open-task .apply-btn {
  background-color: #B906B9;
}

.open-task    { border-left: 5px solid #B906B9; }




/* Propose */
.propose-tab {
  background-color: #D7DEE9;
  border-left: 20px solid #B906B9;
}

.propose-tab.active {
  background-color: #D7DEE9;
}
.propose-task .apply-btn {
  background-color: #B906B9;
}
.propose-task    {  border-left: 5px solid #B906B9;  }



/* Ongoing */
.progress-tab {
  background-color: #D7DEE9;
  border-left: 20px solid #940594;
}

.progress-tab.active {
  background-color: #D7DEE9;
}
.progress-task .apply-btn {
  background-color: #940594;
  color: #000;
}
.progress-task { border-left: 5px solid #940594; }



/* Past */
.completed-tab {
  background-color: #D7DEE9;
  border-left: 20px solid #490349
}

.completed-tab.active {
  background-color: #D7DEE9;
}.completed-task .apply-btn {
  background-color: #490349;
}
.completed-task    { border-left: 5px solid #490349; }


/* === RESPONSIVE === */
@media (max-width: 520px) {
  .task-card {
    flex-direction: column;
    align-items: flex-start;
  }
  .apply-btn {
    margin-top: 0.5rem;
  }
}


.open-task .apply-btn,
.propose-task .apply-btn,
.progress-task .apply-btn,
.completed-task .apply-btn {
  color: white !important;
}

/* Fix ongoing text being black */
.progress-task .apply-btn {
  color: white !important;
}

/* Fix completed */
.completed-task .apply-btn {
  background-color: #490349 !important;
}

.close-all {
  margin: 0.5rem 0 1rem;
  padding: 6px 12px;
  background: #002A41;
  border: none;
  border-radius: 6px;
  font-weight: 400;
  cursor: pointer;
  font-size: 0.9rem;
  float: right;
  color: white;
}

.close-all:hover {
  background: #ccc;
}


</style>

<script>
document.addEventListener("DOMContentLoaded", () => {

  /* ACCORDION TOGGLE */
  document.querySelectorAll('.accordion-btn').forEach(btn => {

    const panelId = btn.getAttribute("data-target");
    const panel = document.getElementById(panelId);
    const arrow = btn.querySelector(".arrow");

    if (!panel) return;

    btn.addEventListener("click", () => {

      const isOpen = panel.classList.contains("open");

      if (isOpen) {
        panel.style.display = "none";
        panel.classList.remove("open");
        btn.classList.remove("active");
        if (arrow) arrow.textContent = "►";
      } else {
        panel.style.display = "block";
        panel.classList.add("open");
        btn.classList.add("active");
        if (arrow) arrow.textContent = "▼";
      }

    });

  });


  /* AUTO OPEN DEFAULT */
  document.querySelectorAll('.accordion-btn[data-open="true"]').forEach(btn => {
    const panel = document.getElementById(btn.getAttribute("data-target"));
    const arrow = btn.querySelector(".arrow");

    if (!panel) return;

    panel.style.display = "block";
    panel.classList.add("open");
    btn.classList.add("active");
    if (arrow) arrow.textContent = "▼";
  });


  /* ✅ CLOSE ALL PER WORKPACKAGE */
  document.querySelectorAll('.close-all').forEach(btn => {

    btn.addEventListener('click', (e) => {

      e.preventDefault();  // prevent page jump

      const wp = btn.getAttribute('data-wp');

      document.querySelectorAll(`[data-target^="${wp}"]`).forEach(tab => {

        const panel = document.getElementById(tab.getAttribute("data-target"));
        const arrow = tab.querySelector(".arrow");

        if (!panel) return;

        panel.style.display = "none";
        panel.classList.remove("open");
        tab.classList.remove("active");
        if (arrow) arrow.textContent = "►";

      });

    });

  });

});
</script>

<div class="workpackages-header">
  <h1>Work package 2: Technical training</h1>
  <p></p>
</div>

This group reviews the status quo of technical skills training for RTPs in the UK. We identify shortcomings of existing training, missing ingredients, and best practices in the delivery of training. The group identifies and commissions user questionnaires, the creation of new training material and training events.

<p>
  ⚠️ <strong>Eligibility Notice:</strong> This call for tasks is currently open only to dRTP members who are formally affiliated with one of the SHAREing consortium universities:
  Durham, Manchester, Queen Mary University of London, Swansea, Cardiff, CoSeC, or Sheffield. Individuals who are not
  members of a dRTP at one of these institutions are not eligible to submit or propose tasks for this call.
</p>

<!-- ============================== -->
<!-- ====== WORKPACKAGE LOOP ====== -->
<!-- ============================== -->

{% assign wp_list = "wp2.3,wp2.4" | split: "," %}
{% assign team_leads = site.data.workpackages-2-team-lead %}
{% for wp in wp_list %}
  
{% assign open = site.tasks | where:"workpackage",wp | where:"status","open" %}
{% assign progress = site.tasks | where:"workpackage",wp | where:"status","progress" %}
{% assign propose = site.tasks | where:"workpackage",wp | where:"status","propose" %}
{% assign completed = site.tasks | where:"workpackage",wp | where:"status","completed" %}

<div class="wp-section">

 {% assign lead = team_leads[wp] %}

<div class="wp-header">
  <img src="{{ lead.lead_photo | default: '/assets/profilepics/generic.jpg' }}">
  <div>
    <p class="wp-title">{{ lead.title | default: "Untitled workpackage" | remove: wp }}
    </p>
    <p class="wp-lead">
      Lead: {{ lead.lead | default: "TBA" }}
    </p>
  </div>
</div>

<div class="wp-controls">
  <button class="close-all" data-wp="{{ wp }}">Close all tabs</button>
</div>

  <!-- OPEN -->
  <button class="accordion-btn open-tab" data-target="{{ wp }}-open" data-open="true">
   Current Open Tasks <span class="arrow">▼</span>
  </button>
  <div id="{{ wp }}-open" class="accordion-panel">

  {% if open.size == 0 %}
    <div class="task-card">No open tasks.</div>
  {% endif %}

  {% for task in open %}
    <div class="task-card open-task">
      <div>{{ task.title }}</div>
      <a class="apply-btn" href="{{ task.url }}">View & Apply</a>
    </div>
  {% endfor %}
  
  </div>



  <!-- PROPOSE -->
  <button class="accordion-btn propose-tab" data-target="{{ wp }}-propose">
   Propose Task <span class="arrow">►</span>
  </button>
  <div id="{{ wp }}-propose" class="accordion-panel">

  {% if propose.size == 0 %}
    <div class="task-card">No proposals.</div>
  {% endif %}

  {% for task in propose %}
    <div class="task-card propose-task">
      <div>{{ task.title }}</div>
      <a class="apply-btn" href="https://forms.office.com/Pages/ResponsePage.aspx?id=i9hQcmhLKUW-RNWaLYpvlBhRpzyeDrFBkd8HIFx_xpdUN0ZMWlk5N1lYSVVORldSTllSSTFWWFYzNS4u" target="_blank" rel="noopener noreferrer">Apply</a>
    </div>
  {% endfor %}

  </div>
  
  
  
  <!-- PROGRESS -->
  <button class="accordion-btn progress-tab" data-target="{{ wp }}-progress">
   Ongoing Tasks <span class="arrow">►</span>
  </button>
  <div id="{{ wp }}-progress" class="accordion-panel">

  {% if progress.size == 0 %}
    <div class="task-card">No tasks in progress.</div>
  {% endif %}

  {% for task in progress %}
    <div class="task-card progress-task">
      <div>{{ task.title }}</div>
      <a class="apply-btn" href="{{ task.url }}">View</a>
    </div>
  {% endfor %}

  </div>


  <!-- COMPLETED -->
  <button class="accordion-btn completed-tab" data-target="{{ wp }}-completed">
   Completed Tasks <span class="arrow">►</span>
  </button>
  <div id="{{ wp }}-completed" class="accordion-panel">

  {% if completed.size == 0 %}
    <div class="task-card">No completed tasks.</div>
  {% endif %}

  {% for task in completed %}
    <div class="task-card completed-task">
      <div>{{ task.title }}</div>
      <a class="apply-btn" href="{{ task.url }}">Results</a>
    </div>
  {% endfor %}

  </div>

</div>

{% endfor %}
