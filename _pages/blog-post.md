---
layout: splash
title: "About SHAREing"
permalink: /blog-post/
classes: wide

---
<style>

.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  height: 50vh;
  background-image: url('/assets/images/sc-booth.jpg');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
}

.parallax-overlay {
  width: 100%;
  height: 100%;
  background: linear-gradient(to top, rgba(0,42,65,0.9), rgba(0,42,65,0.45));
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: #fff;
}

.parallax-overlay h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
}


.about-card {
  background: #ffffff;
  padding: 2rem 1.5rem;
  border-top: 4px solid #68246d;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 10px 18px rgba(0,0,0,0.05);
  display:flex;
  flex-direction: column;
}



.about-card img {
  width: 300px;
  height: 200px;
  object-fit: cover;
  border-radius: 12px;
  filter: contrast(0.95) saturate(0.9) brightness(1.05);
  image-rendering: auto;
}


.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 3fr));
  gap: 2rem;
  margin: 3rem;
}

.about-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 10px 25px rgba(0,0,0,0.08);
  text-align: center;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.about-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 35px 55px rgba(0,0,0,0.3);
}



.about-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.6rem 1.4rem;
  background: #68246D;
  color: white !important;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: background 0.2s ease, transform 0.2s ease;
    margin-top: auto;
}

.about-button:hover {
  background: #4e1a53;
  transform: scale(1.05);
}

.author-block {
  display: flex;
  align-items: center;
  gap: 0.9rem;
  margin-bottom: 3rem;
}

.author-avatar {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 6px 16px rgba(0,0,0,0.8);
}

.author-info {
  font-size: 0.9rem;
  color: #888;
}

.author-info strong {
  display: block;
  font-size: 0.95rem;
  color: #111;
  font-weight: 600;
}

.external-badge {
  display: inline-block;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #fff;
  background: #002A41;
  padding: 0.25rem 0.6rem;
  border-radius: 999px;
  margin-bottom: 0.5rem;
}

@media (max-width: 1200px) {
  .about-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 800px) {
  .about-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 500px) {
  .about-grid {
    grid-template-columns: 1fr;
    padding: 0 1.25rem; 
    gap: 1.5rem;
  }
}
</style>

<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1> Blog Posts</h1>
  </div>
</section>

<section>
  <h2></h2>
  <p>
   Explore insights, updates, and stories from both the SHAREing team and the wider HPC community. This space showcases contributions highlighting progress, events, and discussions across high-performance computing.
  </p>
</section>

<section class="about-grid">

  {% comment %}
  Loop through all posts in the _blogpost collection, sorted by date descending
  {% endcomment %}
  {% assign sorted_posts = site.blogpost | sort: 'date' | reverse %}

  {% for post in sorted_posts %}
    <div class="about-card">
      {% if post.hero_image and post.hero_image != "" %}
        <img src="{{ post.hero_image }}" alt="{{ post.title }}">
      {% endif %}
      {% if post.category == "External" %}
        <span class="external-badge">External</span>
      {% endif %}
      <h3>{{ post.title }}</h3>
      <p>by {{ post.author }}</p>
      <a href="{{ post.url }}" class="about-button">Read</a>
    </div>
  {% endfor %}

</section>
  <h2>Contact</h2>
  <p>
    For enquires or collaboration, please contact the core team or your local partner institution. <a href="/contact"> Find out more here</a>
  </p>



