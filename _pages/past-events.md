---
layout: default
title: Events
permalink: /past-events/
---

<style>

.events-page {
  padding: 3rem 1rem;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}


.events-header {
  margin-bottom: 1rem;
}

.events-header h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.events-header p {
  color: #666;
  font-size: 1.1rem;
}


.events-grid {
  display: grid;
  gap: 2rem;
}


.event-card {
  display: grid;
  grid-template-columns: 260px 1fr;
  gap: 1.5rem;
  border: 1px solid #e6e6e6;
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
  transition: all 0.25s ease;
}

.event-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.08);
}


.event-image {
  display: block;
  height: 100%;
  overflow: hidden;
}

.event-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.event-body {
  padding: 1.2rem 1.2rem 1.2rem 0;
}


.event-meta {
  font-size: 0.85rem;
  color: #777;
  margin-bottom: 0.5rem;

  background: transparent !important;
  padding: 0 !important;

}

.event-dates {
  margin-right: 1rem;
  font-weight: 500;
  font-size: 2rem;
}

.event-location {
  color: #999;
  display: block;
  margin-top: 1rem;
}


.event-title {
  margin: 0.3rem 0 0.6rem;
  font-size: 1.3rem;
}

.event-title a {
  text-decoration: none;
  color: #111;
}

.event-title a:hover {
  text-decoration: underline;
}


.event-summary {
  color: #444;
  margin-bottom: 0.8rem;
  line-height: 1.5;
}


.event-tags {
  margin-top: 0.5rem;
}

.tag {
  display: inline-block;
  background: #f0f0f0;
  color: #555;
  padding: 4px 10px;
  margin-right: 6px;
  border-radius: 999px;
  font-size: 0.75rem;
}

.event-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 10px 14px;
  background: #111;
  color: #fff;
  text-decoration: none;
  border-radius: 8px;
  font-size: 0.9rem;
  transition: all 0.2s ease;
}

.event-button:hover {
  background: #333;
  transform: translateY(-1px);
  color: #ffffff;
}
.event-card {
  cursor: pointer;
}

.event-button {
  background: transparent;
  border: 1px solid #111;
  color: #111;
}

.event-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 10px 14px;
  text-decoration: none;
  border-radius: 8px;
  font-size: 0.9rem;
  transition: all 0.2s ease;
  background: transparent;
  border: 1px solid #111;
  color: #111;
}

.button-past {
 display: flex;
  margin-top: 1rem;
    margin-bottom: 1rem;
    text-align: center;
}

.button-past a {
   text-align: center;
}


.event-button:hover {
  background: #333;
  transform: translateY(-1px);
  color: #ffffff;
}



@media (max-width: 700px) {
  .event-card {
    grid-template-columns: 1fr;
  }

  .event-image img {
    height: 140px;
  }

  .event-body {
    padding: 1rem;
  }
}

</style>
<section class="events-page">
  <div class="container">

    <header class="events-header">
      <h1>Events</h1>
      <p>Workshops, conferences, and activities involving SHAREing members.</p>
    </header>
    
    <a class="event-button button-past" href="/events/">
  Browse upcoming events
</a>

    <div class="events-grid">

{% assign today = "now" | date: "%Y-%m-%d" %}
{% assign sorted_events = site.events | sort: "date" | reverse %}

{% for event in sorted_events %}

  {% assign event_end = event.date | date: "%Y-%m-%d" %}

  {% if event_end <= today %}

    

    <article class="event-card">

      {% if event.image %}
        <a href="{{ event.url }}" class="event-image">
          <img src="{{ event.image | relative_url }}" alt="{{ event.title }}">
        </a>
      {% endif %}

      <div class="event-body">
      
              {% if event.categories %}
          <div class="event-tags">
            {% for category in event.categories %}
              <span class="tag">{{ category }}</span>
            {% endfor %}
          </div>
        {% endif %}
        
        

        <div class="event-meta">

          {% if event.start_date %}
            <span class="event-dates">
              {{ event.start_date | date: "%d %b %Y" }}
              {% if event.date != event.start_date %}
                to {{ event.date | date: "%d %b %Y" }}
              {% endif %}
            </span>
          {% else %}
            <span class="event-dates">
              {{ event.date | date: "%d %b %Y" }}
            </span>
          {% endif %}

          {% if event.location %}
            <span class="event-location">
              {{ event.location }}
            </span>
          {% endif %}

        </div>

        <h2 class="event-title">
          <a href="{{ event.url }}">{{ event.title }}</a>
        </h2>

        {% if event.summary %}
          <p class="event-summary">
            {{ event.summary }}
          </p>
        {% endif %}


        
        <a class="event-button" href="{{ event.url }}">
  Find out more
</a>

      </div>

    </article>

  

  {% endif %}

{% endfor %}

    </div>
  </div>
</section>
