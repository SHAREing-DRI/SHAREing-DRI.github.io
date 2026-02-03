---
layout: default
title: Events
permalink: /outreach/
---
<div class="archive">
  <h1 class="page__title">Events</h1>

  <div class="events-list">
    {% assign sorted_events = site.events | sort_natural: "start_date" | reverse %}

    {% for event in sorted_events %}
      <div class="event-row archive__item">

        {% if event.image %}
          <div class="event-thumb">
            <a href="{{ event.url | relative_url }}">
              <img src="{{ event.image | relative_url }}" alt="{{ event.title }}">
            </a>
          </div>
        {% endif %}

        <div class="event-main">
          <h2 class="archive__item-title no_toc">
            <a href="{{ event.url | relative_url }}">
              {{ event.title }}
            </a>
          </h2>

          <p class="page__meta">
            <time>
              {{ event.start_date | date: "%d %b %Y" }}
              –
              {{ event.date | date: "%d %b %Y" }}
            </time>
            {% if event.location %}
              · 📍 {{ event.location }}
            {% endif %}
          </p>

          {% if event.categories %}
            <p class="event-categories">
              {% for cat in event.categories %}
                <span class="event-tag">{{ cat }}</span>
              {% endfor %}
            </p>
          {% endif %}

          {% if event.summary %}
            <p class="archive__item-excerpt">
              {{ event.summary }}
            </p>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
</div>


<style>
/* List container */
.events-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

/* One full-width row */
.event-row {
  display: grid;
  grid-template-columns: 140px 1fr;
  gap: 1.25rem;

  padding: 1rem;
  border: 1px solid #e6e6e6;
  border-radius: 4px;
  background: #fff;
}

/* Thumbnail */
.event-thumb img {
  width: 300px;
  height: 300px;
  object-fit: contain;
  background: #fafafa;
  border: 1px solid #ddd;
  border-radius: 3px;
}

/* Main content */
.event-main {
  padding: 0;
}

/* Categories like MM labels */
.event-categories {
  margin: 0.25rem 0 0.5rem 0;
}

.event-tag {
  display: inline-block;
  background: #f2f3f3;
  color: #555;
  padding: 0.15rem 0.45rem;
  border-radius: 3px;
  font-size: 0.75rem;
  margin-right: 0.3rem;
}

/* Responsive */
@media (max-width: 600px) {
  .event-row {
    grid-template-columns: 1fr;
  }

  .event-thumb img {
    height: 160px;
  }
}
</style>


