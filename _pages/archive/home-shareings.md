---
layout: splash
permalink: /about/home-shareings/
hidden: true
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/banner-big.png
---



<style>
.parallax-hero {
  position: relative;
  width: 100vw;        /* ocupa todo el ancho */
  min-height: 60vh;    /* ajusta la altura del hero */
  overflow: hidden;
}

.parallax-hero .parallax-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 120%; /* un poco más alto para el efecto de scroll */
  background-image: url('/assets/images/banner-big.png');
  background-size: cover;
  background-position: center;
  transform: translateY(0); /* será modificado con scroll */
  transition: transform 0.1s linear;
  z-index: 1;
}

.parallax-overlay {
  position: relative;
  z-index: 2;
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
  color: white;
  padding: 2rem;
  border-radius: 12px;
  background: linear-gradient(
    to top,
    rgba(104, 36, 109, 0.65),
    rgba(104, 36, 109, 0)
  );
}

.parallax-overlay h1 {
  font-size: clamp(2rem, 5vw, 3rem);
  margin-bottom: 1rem;
}

.parallax-overlay p {
  font-size: clamp(1rem, 2vw, 1.3rem);
  line-height: 1.5;
}
.feature-row .feature {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-row .feature:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0,0,0,0.15);
}



.social-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  margin: 3rem 0;
}
.hero-content {
  max-width: 900px;
  padding: 2rem;
  animation: fadeUp 0.8s ease-out;
}

.hero-content h1 {
  font-size: clamp(2.5rem, 5vw, 3.5rem);
  font-weight: 700;
}

.hero-content p {
  font-size: 1.25rem;
  margin: 1rem 0 2rem;
  line-height: 1.6;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}v
.news-grid {
  display: flex;
  gap: 1.5rem;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  padding-bottom: 2rem;
}

.news-card {
  flex: 0 0 360px;
  background: #fff;
  border-radius: 18px;
  padding: 1rem;
  border-top: 4px solid #68246d;
  scroll-snap-align: start;
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  margin-bottom: 1rem;
}

.news-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 45px rgba(0,0,0,0.15);
}

.news-date {
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: #68246d;
}

.news-card h3 {
  margin: 0.5rem 0;
  font-size: 1.25rem;
}


.news-card h4 {
 
  font-size: 1rem;
  font-weight: 600;
  font-size: 1rem;
  color: #68246d;
  align-items: left;
  text-align: left;
  gap: 0.5rem;
}

.news-card a {
  color: #68246d;       
  font-weight: 700;     
  transition: color 0.2s ease;
}

.section-wide.section-muted h4 {
  font-size: 1.5rem;
  font-weight: 700;
  text-align: left;
  margin-bottom: 0.5rem;
  color: #68246d;
}


.section-wide h4{
  font-size: 1.5rem;
  font-weight: 700;
  text-align: left;
  margin-bottom: 0.5rem;
  color: #68246d;
}

.news-card p {
  font-size: 0.95rem;
  line-height: 1.6;
  margin-bottom: 0.5rem !important;
}

.past-news {
  margin-top: 1.5rem;
}

.past-news summary {
  cursor: pointer;
  color: #68246d;
  list-style: none;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
   font-size: 1.5rem;
  font-weight: 700;
  text-align: left;
  margin-bottom: 0.5rem;
  color: #68246d;
}

.past-news summary::marker {
  display: none;
}

.past-news summary::after {
  content: "▾";
  font-size: 1.2rem;
  transition: transform 0.3s ease;
}

.past-news[open] summary::after {
  transform: rotate(180deg);
}

.past-news-grid {
  margin-top: 1.5rem;
}

.video-card {
  max-width: 1000px;
  margin: 4rem auto;
  position: relative;
  padding-bottom: 56.25%;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0,0,0,0.15);
}

.video-card iframe {
  position: absolute;
  width: 100%;
  height: 100%;
  border: 0;
}

/* =========================
   SOCIAL BUTTONS
========================= */
.social-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin: 3rem 0;
}

.social-buttons .btn {
  padding: 0.9rem 2rem;
  border-radius: 999px;
  font-weight: 600;
  transition: transform 0.2s ease;
}

.social-buttons .btn:hover {
  transform: translateY(-3px);
}


.offerings {
  margin: 4rem 0;
}

.section-title {
  text-align: center;
  font-size: clamp(2rem, 4vw, 2.5rem);
  margin-bottom: 3rem;
  color: #68246d;
}

.offerings-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.offering-card {
  background: #fff;
  border-radius: 20px;
  padding: 2rem 1.8rem;
  text-align: center;
  box-shadow: 0 12px 35px rgba(0,0,0,0.08);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
  display: flex;
  flex-direction: column;
}

.offering-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 25px 60px rgba(0,0,0,0.15);
}

.offering-card img {
  width: 300px;
  height: 250px;
  object-fit: cover;
  border-radius: 12px;
  filter: contrast(0.95) saturate(0.9) brightness(1.05);
  image-rendering: auto;
}

.offering-card h3 {
  font-size: 1.25rem;
  margin-bottom: 0.75rem;
}

.offering-card p {
  font-size: 0.95rem;
  line-height: 1.6;
  flex-grow: 1;
  margin-bottom: 1.5rem;
}

.offering-card .btn {
  align-self: center;
  padding: 0.7rem 1.8rem;
  border-radius: 12px;
  font-size: 1rem;
  background-color: #68246d; /* morado inicial */
  color: white;
  font-weight: 700;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease; /* animación suave */
}

/* Hover */
.offering-card .btn:hover {
  background-color: #8b3a92; 
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(0,0,0,0.1); 
}

</style>


<section class="section-wide section-muted">
  <h4>Latest News</h4>
  
  <div class="news-grid">
  
   <!-- ADD NEWS HERE -->
   
   
   
   
   
   <!-- COPY AND PASTE THIS TEMPLATE -->
    
       <div class="news-card">
  <div class="news-content">
    <span class="news-date">December 2025</span>
    <h3>Correctness and Debugging Workshop</h3>
    <p>
      A report on our recent Correctness and Debugging workshop series is now available on the
      <a href="/events/202511-correctness-workshop/">event's site</a>.
    </p>
  </div>
</div>
     <!-- COPY AND PASTE THIS TEMPLATE -->
     
     
     
     
   
       <div class="news-card">
  <div class="news-content">
    <span class="news-date">November 2025</span>
        <h3>Performance Assessment Webinar</h3>
        <p>In early November SHAREing organised an online seminar dedicated to performance assessments with talks given by representatives from Durham University, Barcelona Supercomputing Centre, Cardiff University and DiRAC. Please see  <a href="http://127.0.0.1:4000/events/202511-performance-webinar/">here</a></p>
      </div>
    </div>
      
    
    
    
   <details class="past-news">
    <summary>Past news</summary>
    
       <div class="news-card">
  <div class="news-content">
    <span class="news-date">October 2025</span>
        <h3>HPC–AI Conference Presentation</h3>
        <p>At the HPC–AI Conference, Tobias Weinzierl introduced SHAREing in a dedicated talk highlighting its mission to strengthen the UK’s Digital Research Infrastructure (DRI) landscape. The presentation covered SHAREing’s goals, structure, and upcoming activities, emphasising its role in connecting the UK’s DRI community and advancing performance assessment and training initiatives. Please watch the recording <a href="https://durham.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=5a91c0b6-acc9-4a3c-9c00-b39200b39edd">here</a></p>
      </div>
    </div>
    
       <div class="news-card">
  <div class="news-content">
    <span class="news-date">October 2025</span>
        <h3>Second round of call for projects</h3>
        <p>SHAREing’s second round of call for projects has been launched. This is a consortium-internal call only. For details on SHAREing’s internal organisation, please consult the  <a href="https://shareing-dri.github.io/about/organisation">description of SHAREing’s internal organisation.</a></p>
      </div>
    </div>
    
    <div class="news-grid past-news-grid">


      <div class="news-card">
        <span class="news-date">August 2025</span>
        <h3>First round of call for projects</h3>
        <p>
          SHAREing’s first round of call for projects has been launched. For details on SHAREing’s internal organisation, please consult the  <a href="https://shareing-dri.github.io/about/organisation">description of SHAREing’s internal organisation.</a>
        </p>
      </div>

      <div class="news-card">
        <span class="news-date">July 2025</span>
        <h3>Workpackage scoping meetings</h3>
        <p>
          The first workpackage scoping meetings have kicked off. Details can be found in the sections on
          <a href="/assessment/">performance assessment</a>.
        </p>
      </div>

    </div>
  </details>



<section class="section-wide offerings">
  <h2 class="section-title">All about SHAREing</h2>

  <div class="offerings-grid">

    <article class="offering-card">
      <img src="/assets/images/hpc-ai.jpg" alt="About SHAREing">
      <h3>About SHAREing</h3>
      <p>More about SHAREing, its vision and the people behind the project.</p>
      <a href="/about/" class="btn btn--primary">Find out more</a>
    </article>

    <article class="offering-card">
      <img src="/assets/images/performance-assessment-1.jpg" alt="Assessments">
      <h3>Performance and machine assessments</h3>
      <p>SHAREing provides performance and machine assessments to the wider UK computational science community.</p>
      <a href="/assessment/" class="btn btn--primary">Find out more</a>
    </article>

    <article class="offering-card">
      <img src="/assets/images/hpc-foundations-knowledge-graph.png" alt="Training">
      <h3>Training</h3>
      <p>SHAREing collects information around accelerator-focused training and also creates its own training material.</p>
      <a href="/training/" class="btn btn--primary">Find out more</a>
    </article>

    <article class="offering-card">
      <img src="/assets/images/ciuk.jpg" alt="Events">
      <h3>SHAREing events</h3>
      <p>Many of SHAREing’s core outputs are delivered through a wide range of community events.</p>
      <a href="/events/" class="btn btn--primary">View schedule</a>
    </article>

    <article class="offering-card">
      <img src="/assets/images/sc-booth.jpg" alt="Resources">
      <h3>SHAREing resources</h3>
      <p>SHAREing’s outcomes and materials are freely available to the UK research community.</p>
      <a href="/resources/" class="btn btn--primary">Access these</a>
    </article>

    <article class="offering-card">
      <img src="/assets/images/team.jpg" alt="Network">
      <h3>Network</h3>
      <p>SHAREing is embedded in a strong network of Digital Research Infrastructure partners.</p>
      <a href="/network/" class="btn btn--primary">Find out more</a>
    </article>

  </div>
</section>



<div class="social-buttons">
  <a href="https://www.linkedin.com/company/shareing/" class="btn btn--info btn--large">LinkedIn</a>
  <a href="https://bsky.app/profile/shareing.bsky.social" class="btn btn--info btn--large">Bluesky</a>
</div>



<section class="section-wide">
  <h4>Project Overview</h4>
  <p> At the HPC–AI Conference, Tobias Weinzierl introduced SHAREing in a dedicated talk highlighting its mission to strengthen the UK’s Digital Research Infrastructure (DRI) landscape. The presentation covered SHAREing’s goals, structure, and upcoming activities, emphasising its role in connecting the UK’s DRI community and advancing performance assessment and training initiatives. </p>
  <div class="video-card">
    <iframe
      src="https://durham.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=5a91c0b6-acc9-4a3c-9c00-b39200b39edd&autoplay=false&offerviewer=false&showtitle=false&showbrand=false"
      allowfullscreen>
    </iframe>
  </div>
</section>



<section class="section-wide">
  <h4>Acknowledgements</h4>
  <p> This project has received funding through the UKRI Digital Research Infrastructure Programme under grant UKRI1801 (SHAREing). </p>
  <img src="/assets/logos/ukri.png" alt="Training">

</section>


