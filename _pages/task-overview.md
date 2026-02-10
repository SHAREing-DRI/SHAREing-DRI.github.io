---
permalink: /task-overview/
title: "Task Map"
layout: default
sidebar: false
classes: wide page__center no-title
---




<style>


.wp-columns {
  display: grid;
grid-template-columns: repeat(4, minmax(100px, 1fr));
  gap: 18px;             
  width: 100%;
  max-width: 1500px;      
  margin: 0 auto;
  padding: 8px;
  transform-origin: top center;
  align-items: stretch;
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
  border-radius: 14px;
  padding: 10px 8px 14px;  
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  border-top: 4px solid #68246d;
    display: flex;
   flex-direction: column;
    height: 100%;
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
   min-height: 60px; 
}

.wp-main-number {
  font-size: 1.55rem;
  font-weight: 700;
  color: #003d66;
 
}

.wp-main-subtitle {
  font-size: 0.7rem;
  font-weight: 500;
  color: #555;
  margin-top: 5px;
  
    line-height: 1.4;
  min-height: calc(1.4em * 2);

  display: -webkit-box;
  -webkit-line-clamp: 2;     
  -webkit-box-orient: vertical;
  overflow: hidden;
}



.wp-subblock {
  border-radius: 8px;
  padding: 10px;
  margin: 14px 0;
  background: #ffffff;
  border: 3px solid #002A41;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
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

.wp-subblocks-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  row-gap: 12px;

  align-items: stretch;
}

.wp-header-wrapper {
  display: grid;
  grid-template-rows: auto 1fr;
  row-gap: 8px;
}


.wp-subtitle {
  font-size: 0.5rem;
  font-weight: 600;
  color: #003d66;
  text-align: center;
    line-height: 1.4;
  min-height: calc(1.4em * 4);

  display: -webkit-box;
  -webkit-line-clamp: 4;      
  -webkit-box-orient: vertical;
  overflow: hidden;
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


.wp-subblocks-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  row-gap: 12px;
}


.kanban {
  display: flex;         
  gap: 12px;              
  margin-top: 8px;
  flex-wrap: wrap;      
    min-height: 110px; /
}

.column {
  background: #ffffff;
  padding: 8px;
  border-radius: 8px;
  flex: 1 1 200px;     
  display: flex;
  flex-direction: column; 
 display: flex;
  flex-direction: column;
  justify-content: flex-start;
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


.tasks-wrapper {
  display: flex;
  flex-direction: column;
  gap: 6px;
  flex-grow: 1; 
    position: relative;
  display: flex;
  flex-direction: column;
  gap: 6px;
  flex-grow: 1;
  min-height: calc((1.3em * 2 + 14px) * 2); 
}



.extra-task {
  display: none; 
}

.tasks-wrapper.expanded .extra-task {
  display: block; 
}


.empty-task {
  visibility: hidden;
}


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
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;   
  overflow: hidden;

  line-height: 1.3;
  min-height: calc(1.3em * 2);

  text-decoration: none;
  color: #003d66;
  font-size: 0.6rem;
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



.toggle-tasks {
  margin-top: auto; 
  padding: 4px 8px;
  font-size: 0.7rem;
  cursor: pointer;
  border-radius: 6px;
  background: #003d66;
  color: #fff;
  border: none;
    min-height: 26px;
}
.toggle-tasks:hover {
  background: #68246d;
}





.open-col .task:hover {
  box-shadow: 0 0 10px rgba(185, 6, 185, 0.45);
  border-color: #B906B9;
  background: rgba(185, 6, 185, 0.08);
  transform: translateY(-2px);
}

.open-col .task {

  background: #FDDFFD;
  transform: translateY(-2px);
}

.progress-col .task:hover {
  box-shadow: 0 0 10px rgba(148, 5, 148, 0.45);
  border-color: #940594;
  background: rgba(148, 5, 148, 0.08);
  transform: translateY(-2px);
}

.progress-col .task {
  background: #E9C9E9;
  transform: translateY(-2px);
}


.completed-col .task{
  background: #DED0DE;
  transform: translateY(-2px);
}


.completed-col .task:hover {
  box-shadow: 0 0 10px rgba(73, 3, 73, 0.45);
  border-color: #490349;
  background: rgba(73, 3, 73, 0.08);
  transform: translateY(-2px);
}


.task-filter {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin: 1.2rem auto;
}

.filter-btn {
  padding: 6px 14px;
  font-size: 0.75rem;
  font-weight: 600;
  border-radius: 20px;
  border: 2px solid #003d66;
  background: white;
  color: #003d66;
  cursor: pointer;
  transition: all 0.2s ease;
}

.filter-btn:hover {
  background: #003d66;
  color: white;
}

.filter-btn.active {
  background: #003d66;
  color: white;
}


.no-tasks-message {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  width: 90%;
  font-size: 0.6rem;
  color: #666;
  font-style: italic;
  text-align: center;
  line-height: 1.4;
  pointer-events: none; 
}


.wp-suggest-task {
  text-align: center;
  margin-bottom: 12px;
}

.wp-suggest-task a {
  display: inline-block;
  padding: 5px 12px;
  font-size: 0.65rem;
  font-weight: 600;
  border-radius: 14px;
  border: 2px dashed #68246d;
  color: #68246d;
  text-decoration: none;
  transition: all 0.2s ease;
  background: #faf5fb;
}

.wp-suggest-task a:hover {
  background: #68246d;
  color: white;
  border-color: #68246d;
}


.eligibility-box {
  max-width: 1400px;
  margin: 2rem auto 1rem;
  padding: 16px 18px;
  border-radius: 14px;

  background: linear-gradient(135deg, #FDF6FF, #f7f9fc);
  border: 2px solid #F0DEF5;
  box-shadow: 0 6px 18px rgba(0,0,0,0.05);

  display: grid;
  grid-template-columns: auto 1fr;
  gap: 14px;

  font-size: 0.75rem;
  color: #002A41;
  line-height: 1.45;
}

.eligibility-icon {
  font-size: 1.6rem;
  line-height: 1;
  margin-top: 2px;
}

.eligibility-box strong {
  font-weight: 700;
}

.eligibility-actions {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-top: 10px;
 align-items: stretch;
}

.eligibility-pill {
  padding: 4px 10px;
  border: 1px solid #68246d;
  border-radius: 999px;
  font-size: 0.65rem;
  font-weight: 600;
  background: #faf5fb;
  border: 1px solid #003d66;
  color: #940594;
}

.eligibility-pill:hover {
  border-color: #490349;
  background: #FEECFE;
  transform: translateY(-2px);
}

.eligibility-pill a{
  color: #940594;
}





body.filter-open .progress-col,
body.filter-open .completed-col {
  display: none;
}

body.filter-progress .open-col,
body.filter-progress .completed-col {
  display: none;
}

body.filter-completed .open-col,
body.filter-completed .progress-col {
  display: none;
}

</style>


<div class="eligibility-box">
  <div class="eligibility-icon">🌍</div>

  <div>
   
    SHAREing tasks are open to <strong> all contributors based at UK universities or other organisations eligible for UKRI funding </strong>
    <br>
    You can <strong> apply to </strong> work on an <strong> existing open task </strong> or <strong> suggest a new task </strong> for one of the Working Packages.
    All applications and task suggestions are discussed through SHAREing’s open Working Group meetings and reviewed by consortium members. Approved task suggestions will be published on this page.
    Approved task applications may be supported and funded where they align with SHAREing priorities and UKRI eligibility criteria.

    <div class="eligibility-actions">
      <div class="eligibility-pill"><a href="/about/flexible-funds">
    Flexible Funds guidelines</a></div>
    <div class="eligibility-pill"><a href="/about/organisation">
    How SHAREing is organised</a></div>
      <div class="eligibility-pill"><a href="/contact/">
    Got a question? Get in touch</a></div>
    </div>
  </div>
</div>



<div class="task-filter">
  <button class="filter-btn active" data-status="open">Open</button>
  <button class="filter-btn" data-status="progress">In progress</button>
  <button class="filter-btn" data-status="completed">Completed</button>
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


  {% assign wp_filename = "WP" | append: wp_number | append: ".md" %}
  {% assign wp_page = site.workpackages | where:"path", wp_filename | first %}


  {% if wp_page == nil %}
    {% assign wp_page = site.workpackages | where_exp:"p","p.path contains wp_filename" | first %}
  {% endif %}

  {% assign wp_target = "/workpackages/workpackage-" | append: wp_number | append:"/" %}

  <div class="wp-column">


<div class="wp-column-title">
  <a href="{{ wp_target }}">
    <div class="wp-main-number">Work Package {{ wp_number }}</div>
    <div class="wp-main-subtitle">{{ wp_page.title }}</div>
  </a>
</div>

<div class="wp-suggest-task">
  <a href="/propose-task/?wp={{ wp_number }}">
    + Suggest a new task for this WP
  </a>
</div>




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


      <div class="wp-subblock">


        <div class="wp-subblock-header">
             <div class="wp-subblock-text">
            <div class="wp-subtitle">{{ meta.title }}</div>
          </div>
        </div>

        <div class="kanban">
        
        
        
        
<div class="column open-col">



<div class="tasks-wrapper">
  {% assign num_to_show = 2 %}

  {% if open.size == 0 %}
    <div class="no-tasks-message">
      There are no current open tasks for this subgroup.
    </div>

    {% for i in (1..num_to_show) %}
      <div class="task empty-task">&nbsp;</div>
    {% endfor %}

  {% else %}

    {% for task in open limit:num_to_show %}
      <div class="task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% assign extra_tasks = open | slice: num_to_show, open.size %}
    {% for task in extra_tasks %}
      <div class="task extra-task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% if open.size < num_to_show %}
      {% assign empty_slots = num_to_show | minus: open.size %}
      {% for i in (1..empty_slots) %}
        <div class="task empty-task">&nbsp;</div>
      {% endfor %}
    {% endif %}

  {% endif %}
</div>

  
  
  

{% if open.size > num_to_show %}
  <button class="toggle-tasks">Show more</button>
{% else %}
  <div class="toggle-tasks" style="visibility:hidden;">Show more</div>
{% endif %}

</div>







<div class="column progress-col">
 
 
 
 
<div class="tasks-wrapper">
  {% assign num_to_show = 2 %}

  {% if progress.size == 0 %}
    <div class="no-tasks-message">
      There are no current tasks in progress for this subgroup.
    </div>

    {% for i in (1..num_to_show) %}
      <div class="task empty-task">&nbsp;</div>
    {% endfor %}

  {% else %}

    {% for task in progress limit:num_to_show %}
      <div class="task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% assign extra_tasks = progress | slice: num_to_show, progress.size %}
    {% for task in extra_tasks %}
      <div class="task extra-task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% if progress.size < num_to_show %}
      {% assign empty_slots = num_to_show | minus: progress.size %}
      {% for i in (1..empty_slots) %}
        <div class="task empty-task">&nbsp;</div>
      {% endfor %}
    {% endif %}

  {% endif %}
</div>

  
  





  {% if progress.size > num_to_show %}
    <button class="toggle-tasks">Show more</button>
  {% else %}
    <div class="toggle-tasks" style="visibility:hidden;">Show more</div>
  {% endif %}
</div>






<div class="column completed-col">





<div class="tasks-wrapper">
  {% assign num_to_show = 2 %}

  {% if completed.size == 0 %}
    <div class="no-tasks-message">
      There are no current completed tasks for this subgroup.
    </div>

    {% for i in (1..num_to_show) %}
      <div class="task empty-task">&nbsp;</div>
    {% endfor %}

  {% else %}

    {% for task in completed limit:num_to_show %}
      <div class="task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% assign extra_tasks = completed | slice: num_to_show, completed.size %}
    {% for task in extra_tasks %}
      <div class="task extra-task">
        <a href="{{ task.url }}">{{ task.title }}</a>
      </div>
    {% endfor %}

    {% if completed.size < num_to_show %}
      {% assign empty_slots = num_to_show | minus: completed.size %}
      {% for i in (1..empty_slots) %}
        <div class="task empty-task">&nbsp;</div>
      {% endfor %}
    {% endif %}

  {% endif %}
</div>

  
  
  
  
  
  
  

  {% if completed.size > num_to_show %}
    <button class="toggle-tasks">Show more</button>
  {% else %}
    <div class="toggle-tasks" style="visibility:hidden;">Show more</div>
  {% endif %}
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

<script>
document.addEventListener("DOMContentLoaded", function () {

  document.body.classList.add("filter-open");

  document.querySelectorAll(".filter-btn").forEach(btn => {
    btn.addEventListener("click", function () {
      const status = this.dataset.status;


      document.body.classList.remove(
        "filter-open",
        "filter-progress",
        "filter-completed"
      );


      document.body.classList.add(`filter-${status}`);

      document.querySelectorAll(".filter-btn").forEach(b =>
        b.classList.remove("active")
      );
      this.classList.add("active");
    });
  });

});
</script>

