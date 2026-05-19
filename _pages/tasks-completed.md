---
permalink: /tasks-completed/
title: "Tasks completed"
layout: splash
classes: wide
---

<style>



/* GRID */
.tasks-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}


.task-card {
  background: #ffffff;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 28px rgba(0,0,0,0.07);
  border-top: 4px solid #68246d;
  text-decoration: none;
  color: inherit;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  display: flex;
  flex-direction: column;
}

.task-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 18px 40px rgba(0,0,0,0.12);
}


.task-main-image {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.task-content {
  padding: 1.4rem;
}


.task-card .wp {
 display: inline-flex;
  align-items: center;

  padding: 0.45rem 1rem;
  margin-bottom: 1rem;

  border-radius: 999px;

  background: rgba(255,255,255,0.14);
  backdrop-filter: blur(10px);

  border: 1px solid rgba(255,255,255,0.18);


  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;

  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}


.task-card h3 {
  font-size: 1.15rem;
  margin-bottom: 1rem;
  color: #68246d;
  line-height: 1.4;
}


.task-person {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-top: auto;
}


.task-profile-pic {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  object-fit: cover;
  flex-shrink: 0;
  border: 2px solid #f0f0f0;
}


.task-person-info {
  display: flex;
  flex-direction: column;
}

.task-person-info .name {
  font-size: 0.92rem;
  font-weight: 600;
  color: #333;
}

.task-person-info .institution {
  font-size: 0.8rem;
  color: #777;
}

.assessment-header {
  text-align: center;
  margin: 1.5rem 0 2rem 0;
}

.assessment-header h1 {
  font-size: 2.1rem;
  margin-bottom: 0.3rem;
    margin-top: 0.3rem;
}

.assessment-header p {
  color: #555;
  font-size: 0.8rem;
  max-width: 1200px;
  margin: 1rem auto;
}


@media (max-width: 768px) {
  .parallax-hero {
    background-attachment: scroll;
    height: 30vh;
  }
  
    .parallax-overlay {
    padding: 1.5rem;
  }

  .parallax-overlay h1 {
    font-size: 2rem;
  }
   
}



</style>

<div class="assessment-header">
  <h1>Tasks Completed</h1>
  <p>
This page showcases the work that has been completed within SHAREing. These activities were proposed as solutions to open tasks across the different work packages. Browse these mini-projects and <a href='https://shareing-dri.github.io/contact/'>get in touch</a> if you would like to learn more about them. <br>

If you are interested in contributing similar work, please explore our current <a href='https://shareing-dri.github.io/task-map/'>open tasks and propose your own solution</a>.
</p>
</div>


<section class="section-wide">
  <div class="tasks-grid">

    {% for task in site.tasks %}
      {% if task.status == "completed" %}

      <a href="{{ task.url }}" class="task-card">

        {% if task.image %}
          <img 
            src="{{ task.image }}" 
            alt="{{ task.title }}" 
            class="task-main-image"
          >
        {% endif %}

        <div class="task-content">
        



          <p class="wp">{{ task.workpackage }}</p>

          <h3>{{ task.title }}</h3>

          {% if task.person.name %}
          <div class="task-person">

            {% if task.person.image %}
              <img 
                src="{{ task.person.image }}" 
                alt="{{ task.person.name }}"
                class="task-profile-pic"
              >
            {% endif %}

            <div class="task-person-info">

              <div class="name">
                {{ task.person.name }}
              </div>

              {% if task.person.institution %}
                <div class="institution">
                  {{ task.person.institution }}
                </div>
              {% endif %}

            </div>

          </div>
          {% endif %}

        </div>

      </a>

      {% endif %}
    {% endfor %}

  </div>
</section>
