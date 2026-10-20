---
title: "HPC Days in the Community"
layout: splash
permalink: /network/hpcdays/
classes: wide
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/banner-big.png
---

<section class="community-intro">

<h2>HPC Days in the Community</h2>

<p>
HPC Days brings together people from across the computational science community.
Here are some reflections, highlights, and stories shared by attendees and partners.
</p>

</section>


{% assign platforms = "blog,linkedin,bluesky" | split: "," %}

{% for platform in platforms %}

{% assign posts = site.data.hpcdays | where: "platform", platform %}


{% if posts.size > 0 %}

<section class="community-section">

{% if platform == "blog" %}
<h2>📰 Blog Posts</h2>
<p class="section-description">
Longer reflections, summaries, and stories from the HPC Days community.
</p>

{% elsif platform == "linkedin" %}
<h2>💼 LinkedIn Highlights</h2>
<p class="section-description">
Community reflections and conversations shared on LinkedIn.
</p>

{% elsif platform == "bluesky" %}
<h2>☁️ Bluesky Conversations</h2>
<p class="section-description">
Short updates and conversations from the HPC Days community.
</p>

{% endif %}


<div class="community-grid">

{% for post in posts %}

<article class="community-card">

<div class="platform-badge">

{% if post.platform == "blog" %}
📰 Blog
{% elsif post.platform == "linkedin" %}
💼 LinkedIn
{% elsif post.platform == "bluesky" %}
☁️ Bluesky
{% endif %}

</div>


<h3>{{ post.title }}</h3>


<p class="community-author">
{{ post.author }}
</p>


{% if post.description %}
<p>
{{ post.description }}
</p>
{% endif %}


<a href="{{ post.url }}" 
   target="_blank" 
   rel="noopener"
   class="community-button">

Read post →

</a>


</article>


{% endfor %}

</div>

</section>


{% endif %}

{% endfor %}



<section class="community-footer">

<h2>Share your HPC Days experience</h2>

<p>
Have you written about HPC Days or shared your experience online?
We would love to include your contribution here.
</p>

</section>


<style>


.community-intro {
  max-width: 900px;
  margin: 3rem auto 4rem;
  text-align: center;
}


.community-intro h2 {
  color: #68246d;
  font-size: clamp(2rem,4vw,3rem);
}


.community-intro p {
  font-size:1.15rem;
  line-height:1.7;
}



.community-section {
  margin: 4rem 0;
}


.community-section h2 {
  color:#68246d;
  font-size:2rem;
  margin-bottom:0.5rem;
}


.section-description {
  margin-bottom:2rem;
  color:#666;
}



.community-grid {

display:grid;

grid-template-columns:
repeat(auto-fit,minmax(300px,1fr));

gap:2rem;

}



.community-card {

background:white;

border-radius:20px;

padding:2rem;

box-shadow:
0 12px 35px rgba(0,0,0,0.08);

border-top:5px solid #68246d;

display:flex;

flex-direction:column;

transition:
transform .3s ease,
box-shadow .3s ease;

}



.community-card:hover {

transform:translateY(-8px);

box-shadow:
0 25px 60px rgba(0,0,0,0.15);

}



.platform-badge {

display:inline-flex;

align-self:flex-start;

background:#f4e9f5;

color:#68246d;

font-weight:700;

padding:.35rem .8rem;

border-radius:999px;

font-size:.9rem;

margin-bottom:1rem;

}



.community-card h3 {

font-size:1.35rem;

margin-bottom:.5rem;

}



.community-author {

font-size:.9rem;

color:#777;

font-weight:600;

}



.community-button {

margin-top:auto;

display:inline-block;

align-self:flex-start;

background:#68246d;

color:white !important;

padding:.7rem 1.6rem;

border-radius:999px;

font-weight:700;

text-decoration:none;

transition:.2s ease;

}



.community-button:hover {

background:#8b3a92;

transform:translateY(-2px);

}



.community-footer {

margin:5rem auto;

padding:3rem;

max-width:900px;

background:#f8f3f8;

border-radius:20px;

text-align:center;

}


.community-footer h2 {

color:#68246d;

}


</style>