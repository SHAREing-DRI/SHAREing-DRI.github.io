---
layout: splash
title: "Work Package 3: Professional skills training - Webinars"
permalink: /webinars/webinar-wp-3/
---

<style>
.wp-tabs-container {
  max-width: 1100px;
  margin: 2rem auto;
}

.tab-buttons {
  display: flex;
  gap: 1rem;
  margin-bottom: 1.5rem;
  justify-content: center; 
}

.tab-btn {
background: #0E2841;
  color: white !important;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  transition: background 0.25s ease, color 0.25s ease, border-color 0.25s ease;
}

.tab-btn:hover {
  background: #CDA3CD !important;
  border-color: #CDA3CD !important;
  color: #ffffff !important;
}

.tab-btn.active {
  background: #CDA3CD !important;
  border-color: #CDA3CD !important;
  color: #ffffff !important;
}




.tab-content {
  padding-top: 1rem;
}

.events-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(330px, 1fr));
  gap: 2rem;
}

.no-events-msg {
  font-style: italic;
  colour: #777;
  margin-top: 1rem;
}

.tab-content {
  display: none !important;
  visibility: hidden;
  height: 0;
  overflow: hidden;
}

.tab-content.active-tab {
  display: block !important;
  visibility: visible;
  height: auto;
  overflow: visible;
}

.workpackages-header {
  text-align: center;
  margin: 3rem auto 2rem auto;
  max-width: 900px;
}

.workpackages-header h1 {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #0E2841;
}

.workpackages-header p {
  color: #555;
  font-size: 1.15rem;
  margin: 0 auto;
}



</style>

<div class="workpackages-header">
  <h1>Work Package 3: Professional skills training - Webinars</h1>
  <p></p>
</div>
{% assign wp_category = "Webinar-WP-3" %}

{% assign upcoming = site.events 
  | where_exp: "e", "e.categories contains wp_category"
  | where_exp: "e", "e.date >= site.time"
  | sort: "date"
%}

{% assign past = site.events 
  | where_exp: "e", "e.categories contains wp_category"
  | where_exp: "e", "e.date < site.time"
  | sort: "date"
  | reverse
%}

<div class="wp-tabs-container">

  <div class="tab-buttons">
    <button class="tab-btn active" onclick="openTab('upcoming', this)">Upcoming Webinars</button>
    <button class="tab-btn" onclick="openTab('past', this)">Past Webinars</button>
  </div>

<div id="upcoming" class="tab-content active-tab">
    {% if upcoming != empty %}
      <div class="events-grid">
      {% for event in upcoming %}
        {% include event-card.html event=event %}
      {% endfor %}
      </div>
    {% else %}
      <p class="no-events-msg">No upcoming webinars.</p>
    {% endif %}
  </div>

  <div id="past" class="tab-content">
    {% if past != empty %}
      <div class="events-grid">
      {% for event in past %}
        {% include event-card.html event=event %}
      {% endfor %}
      </div>
    {% else %}
      <p class="no-events-msg">No past webinars.</p>
    {% endif %}
  </div>

</div>

<script>
function openTab(tabId, btn) {
  document.querySelectorAll('.tab-content').forEach(t => {
    t.classList.remove('active-tab');
  });
  document.getElementById(tabId).classList.add('active-tab');

  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}
</script>
