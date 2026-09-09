---
permalink: /workpackages/workpackage-1/
title: "Work package 1: Performance Assessment"
classes: wide
layout: splash
---

{% assign suggest_url = page.apply | default: site.data.propose_links.default %}

<style>


:root {
  --shareing-purple: #B906B9;
  --shareing-purple-dark: #740574;
  --shareing-purple-mid: #940594;
  --shareing-dark: #002A41;

  --text-main: #3f4a54;
  --text-muted: #68737d;

  --background: #f7f9fc;
  --background-soft: #f1f4f7;
  --border: #e1e6eb;
  --white: #ffffff;
}


.wp-hero {
  position: relative;
  margin-top: 1rem;
  margin-bottom: 1rem;
  padding: 3rem 3.25rem;

  background: linear-gradient(
    135deg,
    #f8fafd 0%,
    #eef2f6 100%
  );

  border: 1px solid var(--border);
  border-radius: 16px;

  overflow: hidden;
}


/* Purple accent */

.wp-hero::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;

  width: 7px;

  background: linear-gradient(
    to bottom,
    var(--shareing-purple),
    var(--shareing-purple-dark)
  );
}


.wp-hero::after {
  content: "";
  position: absolute;
  width: 360px;
  height: 360px;
  right: -180px;
  top: -210px;
  border-radius: 50%;
  background: rgba(185, 6, 185, 0.055);
}


.wp-hero-content {
  position: relative;
  z-index: 2;
  max-width: 1200px;
}



.wp-eyebrow {
  margin: 0 0 0.6rem !important;
  color: var(--shareing-purple) !important;
  font-size: 0.78rem !important;
  font-weight: 700 !important;
  letter-spacing: 0.16em;
  text-transform: uppercase;
}



.wp-hero-title {
  margin: 0 !important;
  color: var(--shareing-dark) !important;
  font-size: clamp(2.3rem, 5vw, 3.5rem) !important;
  font-weight: 800 !important;
  line-height: 1.05 !important;
  letter-spacing: -0.02em;
}


.wp-hero-subtitle {
  max-width: 1200px;
  margin: 1rem 0 1.5rem !important;
  color: var(--text-main) !important;
  font-size: 0.9rem !important;
  line-height: 1.6 !important;
}


.wp-lead {
  display: inline-flex;
  align-items: center;
  gap: 0.8rem;
  margin: 0 !important;
  padding: 0.45rem 1rem 0.45rem 0.5rem;
  background: var(--white);
  border: 1px solid var(--border);
  border-left: 4px solid var(--shareing-purple);
  border-radius: 9px;
  color: var(--shareing-dark) !important;
  font-size: 0.9rem !important;
  font-weight: 600;
  box-shadow:
    0 2px 8px rgba(0, 42, 65, 0.05);
}


.wp-lead-photo {
  width: 44px;
  height: 44px;
  flex-shrink: 0;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #ffffff;
  box-shadow:
    0 1px 5px rgba(0, 42, 65, 0.15);
}


.wp-lead-info {
  display: flex;
  flex-direction: column;
  line-height: 1.2;
}


.wp-lead-label {
  margin-bottom: 0.15rem;
  color: var(--text-muted);
  font-size: 0.68rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}


.wp-introduction {
  margin: 0 0 2.5rem;
  padding: 1.6rem 1.8rem;
  background: none;
  border-radius: 12px;

}


.wp-introduction-label {
  margin: 0 0 0.5rem !important;
  color: var(--shareing-purple) !important;
  font-size: 0.72rem !important;
  font-weight: 700 !important;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}


.wp-introduction p {
  margin: 0 !important;
  color: var(--text-main);
  font-size: 0.98rem !important;
  line-height: 1.7 !important;
}



.wp-actions {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1rem;
}


.wp-action-card {
  position: relative;
  padding: 1.4rem 1.5rem 1.45rem 1.6rem;
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}


.wp-action-card::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 5px;
  background: var(--shareing-purple);
}


.wp-action-card:hover {
  transform: translateY(-2px);
  box-shadow:
    0 6px 20px rgba(0, 42, 65, 0.08);
}


.wp-action-card h3 {
  margin: 0 0 0.55rem !important;
  color: var(--shareing-dark) !important;
  font-size: 1.15rem !important;
  font-weight: 750 !important;
}


.wp-action-card p {
  margin: 0 !important;
  color: var(--text-main);
  font-size: 0.9rem !important;
  line-height: 1.6 !important;
}


.eligibility-box {
  margin: 0 0 2.8rem !important;
  padding: 0.75rem 1rem;
  background: #f7f8fa;
  border-radius: 7px;
  color: var(--text-muted) !important;
  font-size: 0.82rem !important;
  line-height: 1.5 !important;
}


.eligibility-box strong {
  color: var(--shareing-dark);
  font-weight: 650 !important;
}


.wp-section {
  margin-bottom: 2rem;
  padding: 1.5rem 1.6rem 1.6rem;
  background: var(--white);
  border-left: 4px solid #005a9c;
  border-radius: 12px;
  box-shadow:
    0 2px 10px rgba(0, 42, 65, 0.035);
}


.wp-header {
  display: block;
  margin: 0 0 1rem;
}


.wp-title {
  margin: 0 0 0.35rem !important;
  color: var(--shareing-dark) !important;
  font-size: 1.35rem !important;
  font-weight: 750 !important;
  line-height: 1.2 !important;
}


.wp-content {
  margin: 0 !important;
  color: var(--text-muted) !important;
  font-size: 0.88rem !important;
  line-height: 1.55 !important;
}


.wp-controls {
  display: flex;
  justify-content: flex-end;
  margin: -0.2rem 0 0.8rem;
}


.close-all {
  float: none;
  margin: 0;
  padding: 0.35rem 0.7rem;
  background: transparent;
  border: 1px solid #d7dde3;
  border-radius: 5px;
  color: var(--text-muted);
  font-size: 0.72rem;
  font-weight: 500;
  cursor: pointer;
  transition:
    background 0.2s ease,
    border-color 0.2s ease,
    color 0.2s ease;
}


.close-all:hover {
  background: #f4f6f8;
  border-color: #c5ccd3;
  color: var(--shareing-dark);
  box-shadow: none;
}

.accordion-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 0.45rem;
  padding: 0.85rem 1rem;
  background: #f7f9fb;
  border: 1px solid var(--border);
  border-left: 5px solid var(--shareing-purple);
  border-radius: 7px;
  color: var(--shareing-dark);
  font-size: 0.88rem;
  font-weight: 700;
  text-align: left;
  cursor: pointer;
  transition:
    background 0.2s ease,
    border-color 0.2s ease;
}


.accordion-btn:hover {
  background: #f1f4f7;
}


.accordion-btn.active {
  background: #f1f4f7;
}


.accordion-panel {
  display: none;
  padding: 0.35rem 0 0.7rem;
}


.arrow {
  font-size: 0.7rem;

  color: var(--text-muted);
}



.open-tab {
  border-left-color: var(--shareing-purple);
}

.open-task {
  border-left: 4px solid var(--shareing-purple);
}

.open-task .apply-btn {
  background: var(--shareing-purple);
}



.propose-tab {
  border-left-color: var(--shareing-purple);
}

.propose-task {
  border-left: 4px solid var(--shareing-purple);
}

.propose-task .apply-btn {
  background: var(--shareing-purple);
}



.progress-tab {
  border-left-color: var(--shareing-purple-mid);
}

.progress-task {
  border-left: 4px solid var(--shareing-purple-mid);
}

.progress-task .apply-btn {
  background: var(--shareing-purple-mid);
}


.completed-tab {
  border-left-color: var(--shareing-purple-dark);
}

.completed-task {
  border-left: 4px solid var(--shareing-purple-dark);
}

.completed-task .apply-btn {
  background: var(--shareing-purple-dark);
}


.task-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 0.45rem;
  padding: 0.7rem 0.8rem;
  background: var(--white);
  border: 1px solid #e4e8ec;
  border-radius: 6px;
  color: var(--text-main);
  font-size: 0.82rem;
  transition:
    box-shadow 0.2s ease,
    transform 0.2s ease;
}


.task-card:hover {
  transform: translateX(2px);
  box-shadow:
    0 3px 10px rgba(0, 0, 0, 0.06);
}


.task-card div {
  font-size: 0.82rem;
}


.task-card .apply-btn {
  flex-shrink: 0;
  padding: 0.35rem 0.65rem;
  border-radius: 5px;
  color: #ffffff !important;
  font-size: 0.72rem;
  font-weight: 650;
  text-decoration: none;
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}


.task-card .apply-btn:hover {
  transform: translateY(-1px);
  box-shadow:
    0 3px 8px rgba(0, 0, 0, 0.15);
  color: #ffffff !important;
}


.task-card.empty {
  display: block;
  color: var(--text-muted);
  font-style: italic;
}



@media (max-width: 700px) {
  .wp-hero {
    padding: 2rem 1.5rem;
  }

  .wp-hero-title {
    font-size: 2.25rem !important;
  }

  .wp-actions {
    grid-template-columns: 1fr;
  }

  .wp-section {
    padding: 1.2rem;
  }

}


@media (max-width: 520px) {

  .wp-hero {
    padding: 1.8rem 1.2rem;
  }

  .wp-hero-title {
    font-size: 2rem !important;
  }

  .wp-hero-subtitle {
    font-size: 0.92rem !important;
  }

  .wp-lead {
    width: auto;
    max-width: 100%;
  }

  .task-card {
    flex-direction: column;

    align-items: flex-start;
  }

  .task-card .apply-btn {
    align-self: flex-start;
  }

}

</style>

<script>

document.addEventListener("DOMContentLoaded", () => {


  document.querySelectorAll(".accordion-btn").forEach(btn => {

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

        if (arrow) {
          arrow.textContent = "►";
        }

      } else {

        panel.style.display = "block";

        panel.classList.add("open");

        btn.classList.add("active");

        if (arrow) {
          arrow.textContent = "▼";
        }

      }

    });

  });


  document
    .querySelectorAll('.accordion-btn[data-open="true"]')
    .forEach(btn => {

      const panel = document.getElementById(
        btn.getAttribute("data-target")
      );

      const arrow = btn.querySelector(".arrow");

      if (!panel) return;

      panel.style.display = "block";

      panel.classList.add("open");

      btn.classList.add("active");

      if (arrow) {
        arrow.textContent = "▼";
      }

    });


  document.querySelectorAll(".close-all").forEach(btn => {

    btn.addEventListener("click", (e) => {

      e.preventDefault();

      const wp = btn.getAttribute("data-wp");


      document
        .querySelectorAll(`[data-target^="${wp}"]`)
        .forEach(tab => {

          const panel = document.getElementById(
            tab.getAttribute("data-target")
          );

          const arrow = tab.querySelector(".arrow");

          if (!panel) return;


          panel.style.display = "none";

          panel.classList.remove("open");

          tab.classList.remove("active");

          if (arrow) {
            arrow.textContent = "►";
          }

        });

    });

  });

});

</script>


<div class="wp-hero">

  <div class="wp-hero-content">


<p class="wp-eyebrow">
  Work Package 01
</p>

<h1 class="wp-hero-title">
  Performance Assessment
</h1>

<p class="wp-hero-subtitle">
This work package defines and improves SHAREing’s performance assessment framework by selecting relevant codes and systems, analysing assessment results to identify wider sector trends, and shaping a comprehensive methodology that can be applied across UK compute centres. It evaluates existing assessment practices, commissions studies to address methodological gaps, collaborates with training work packages on needed skills, and reviews the status of UK testbeds to establish best practices, consolidate essential information, and recommend future testbed developments that will best support progress in the community.
</p>


<!-- Lead -->

<div class="wp-lead">

  <img
    class="wp-lead-photo"
    src="/assets/profilepics/thomas.jpg"
    alt="Thomas Flynn"
  >

  <div class="wp-lead-info">

    <span class="wp-lead-label">
      Work package lead
    </span>

    Thomas Flynn

  </div>

</div>


  </div>

</div>






<div class="eligibility-box">

<strong>Eligibility:</strong>

SHAREing tasks are open to all contributors based at UK universities or other organisations eligible for UKRI funding

</div>

{% assign wp_list = "wp1.1,wp1.2,wp1.3" | split: "," %}

{% assign team_leads = site.data.workpackages-1-team-lead %}

{% for wp in wp_list %}

{% assign open = site.tasks
| where:"workpackage",wp
| where:"status","open"
%}

{% assign progress = site.tasks
| where:"workpackage",wp
| where:"status","progress"
%}

{% assign propose = site.tasks
| where:"workpackage",wp
| where:"status","propose"
%}

{% assign completed = site.tasks
| where:"workpackage",wp
| where:"status","completed"
%}

{% assign lead = team_leads[wp] %}

  <div class="wp-section">

<!-- Sub-WP heading -->

<div class="wp-header">

  <p class="wp-title">
    {{ lead.title
      | default: "Untitled workpackage"
      | remove: wp
    }}
  </p>

  <div class="wp-content">
    {{ lead.summary | default: "TBA" }}
  </div>

</div>


<!-- Controls -->

<div class="wp-controls">

  <button
    class="close-all"
    data-wp="{{ wp }}"
  >
    Close all tabs
  </button>

</div>


<button
  class="accordion-btn open-tab"
  data-target="{{ wp }}-open"
  data-open="true"
>

  <span>
    Current Open Tasks
  </span>

  <span class="arrow">
    ▼
  </span>

</button>


<div
  id="{{ wp }}-open"
  class="accordion-panel"
>

  {% if open.size == 0 %}

    <div class="task-card empty">
      No open tasks.
    </div>

  {% endif %}


  {% for task in open %}

    <div class="task-card open-task">

      <div>
        {{ task.title }}
      </div>

      <a
        class="apply-btn"
        href="{{ task.url }}"
      >
        See Details & Apply
      </a>

    </div>

  {% endfor %}

</div>



<button
  class="accordion-btn propose-tab"
  data-target="{{ wp }}-propose"
>

  <span>
    Suggest New Task
  </span>

  <span class="arrow">
    ►
  </span>

</button>


<div
  id="{{ wp }}-propose"
  class="accordion-panel"
>

  {% if propose.size == 0 %}

    <div class="task-card empty">
      No proposals.
    </div>

  {% endif %}


  {% for task in propose %}

    <div class="task-card propose-task">

      <div>
        {{ task.title }}
      </div>

      <a
        class="apply-btn"
        href="{{ suggest_url }}"
        target="_blank"
        rel="noopener noreferrer"
      >
        Suggest
      </a>

    </div>

  {% endfor %}

</div>

<button
  class="accordion-btn progress-tab"
  data-target="{{ wp }}-progress"
>

  <span>
    Ongoing Tasks
  </span>

  <span class="arrow">
    ►
  </span>

</button>


<div
  id="{{ wp }}-progress"
  class="accordion-panel"
>

  {% if progress.size == 0 %}

    <div class="task-card empty">
      No tasks in progress.
    </div>

  {% endif %}


  {% for task in progress %}

    <div class="task-card progress-task">

      <div>
        {{ task.title }}
      </div>

      <a
        class="apply-btn"
        href="{{ task.url }}"
      >
        View
      </a>

    </div>

  {% endfor %}

</div>


<button
  class="accordion-btn completed-tab"
  data-target="{{ wp }}-completed"
>

  <span>
    Completed Tasks
  </span>

  <span class="arrow">
    ►
  </span>

</button>


<div
  id="{{ wp }}-completed"
  class="accordion-panel"
>

  {% if completed.size == 0 %}

    <div class="task-card empty">
      No completed tasks.
    </div>

  {% endif %}


  {% for task in completed %}

    <div class="task-card completed-task">

      <div>
        {{ task.title }}
      </div>

      <a
        class="apply-btn"
        href="{{ task.url }}"
      >
        Results
      </a>

    </div>

  {% endfor %}

</div>

  </div>

{% endfor %}
