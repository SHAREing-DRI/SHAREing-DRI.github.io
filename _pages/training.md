---
layout: splash
title: "Training & Upskilling"
permalink: /training/
classes: wide
---
<style>
.tl-page {
  --tl-purple: #940594;
  --tl-purple-dark: #740574;
  --tl-deep: #421456;
  --tl-soft: #faf5fa;
  --tl-line-purple: #e4cde4;
  --tl-navy: #002a41;
  --tl-text: #334155;
  --tl-muted: #596579;
  --tl-border: #e2e8f0;
  --tl-bg: #f8fafc;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 1rem 4rem;
  color: var(--tl-text);
  line-height: 1.6;
}
.tl-page *, .tl-page *::before, .tl-page *::after { box-sizing: border-box; }
.tl-page img { margin: 0; }
.tl-page a:focus-visible {
  outline: 3px solid var(--tl-purple);
  outline-offset: 3px;
  border-radius: 4px;
}

.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  height: 40vh;
  background-image: url('/assets/images/performance-assessment-1.jpg');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
   color: #fff;
}

.parallax-overlay {
  width: 100%;
  height: 100%;
background: linear-gradient(to top, #68246D, rgba(104, 36, 109, 0.45));
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
  color: #fff !important;
}



.parallax-overlay p {
  font-size: 0.8rem;
  margin-top: 1rem;
}



/* ---------- Header ---------- */

.tl-header {
  margin-bottom: 2rem;
}

.tl-header h1 {
  margin: 0 0 .6rem;
  color: var(--tl-navy);
  font-size: 2.25rem;
  line-height: 1.15;
}
.tl-intro {
  max-width: 60ch;
  margin: 0 0 1.25rem;
  color: var(--tl-muted);
  font-size: 1.05rem;
  margin-bottom: 2rem;
}
.tl-nav { display: flex; flex-wrap: wrap; gap: .5rem; margin-top: 1rem; }
.tl-nav a {
  padding: .4rem .9rem;
  border: 1px solid var(--tl-border);
  border-radius: 999px;
  background: #ffffff;
  color: var(--tl-text) !important;
  font-size: .88rem;
  text-decoration: none;
}
.tl-nav a:hover {
  border-color: var(--tl-purple);
  color: var(--tl-purple) !important;
}

/* ---------- Sections ---------- */
.tl-main section { margin-bottom: 3.5rem; scroll-margin-top: 5rem; }
.tl-section-head { margin-bottom: 1.25rem; }
.tl-section-head h2 {
  margin: 0;
  color: var(--tl-navy);
  font-size: 1.4rem;
  line-height: 1.3;
}
.tl-section-head p {
  margin: .2rem 0 0;
  color: var(--tl-muted);
  font-size: .95rem;
}


/* ---------- Upcoming event ---------- */
.tl-event {
  display: grid;
  grid-template-columns: 150px minmax(0, 1fr);
  gap: 1rem;
  align-items: stretch;
  padding: 1rem;
  border: 1px solid var(--tl-border);
  border-radius: 12px;
  background: #ffffff;
  margin-bottom:1rem;
}

/* Date panel */
.tl-date {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: .35rem;
  min-width: 0;
  padding: 1.25rem .75rem;
  border-radius: 8px;
  background: var(--tl-border);
  color: var(--tl-navy);
  text-align: center;
  line-height: 1.2;
}

.tl-date-days {
  font-size: 1.8rem;
  font-weight: 700;
  letter-spacing: -.04em;
  white-space: nowrap;
}

.tl-date-month {
  font-size: .9rem;
  font-weight: 500;
  white-space: nowrap;
}

/* Event details */
.tl-event-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: .5rem .5rem .5rem 0;
  min-width: 0;
}

.tl-event h3 {
  margin: 0 0 .2rem;
  color: var(--tl-navy);
  font-size: 1.25rem;
  line-height: 1.35;
}

.tl-event p {
  max-width: 62ch;
  margin: 0 0 1.1rem;
  color: var(--tl-muted);
  font-size: .93rem;
  line-height: 1.65;
}

/* Registration link */
.tl-button {
  display: inline-flex;
  align-items: center;
  gap: .5rem;
  padding: .65rem 0;
  background: transparent;
  color: var(--tl-muted) !important;
  font-size: .92rem;
  font-weight: 700;
  text-decoration: none;
}

.tl-button:hover {
  color: var(--tl-text) !important;
  text-decoration: underline;
  text-underline-offset: 3px;
}

.tl-button:focus-visible {
  outline: 2px solid var(--tl-purple);
  outline-offset: 4px;
  border-radius: 2px;
}

/* Mobile */
@media (max-width: 600px) {
  .tl-event {
    grid-template-columns: 1fr;
    gap: 1rem;
    padding: 1rem;
  }

  .tl-date {
    flex-direction: row;
    justify-content: flex-start;
    gap: .6rem;
    align-self: start;
    padding: .65rem .85rem;
  }

  .tl-date-days {
    font-size: 1.2rem;
  }

  .tl-event-content {
    padding: 0;
  }

  .tl-event h3 {
    font-size: 1.15rem;
  }
}


/* ---------- Learning resources ---------- */
.tl-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.25rem;
}
.tl-resource {
  position: relative;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  border: 1px solid var(--tl-border);
  border-radius: 12px;
  background: #ffffff;
}
.tl-resource:hover,
.tl-resource:focus-within { border-color: var(--tl-purple); }
.tl-resource-media-small {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 160px;
  padding: 1.25rem;
  border-bottom: 1px solid var(--tl-border);
  background: var(--tl-bg);
}
.tl-resource-media-small img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.tl-resource-media {
  height: 160px;              
  padding: 0;
  overflow: hidden;
  border-bottom: 1px solid var(--tl-border);
  background: var(--tl-bg);
}
.tl-resource-media img {
  display: block;
  width: 100%;
  height: 100%;
  margin: 0;
  object-fit: cover;
}
.tl-resource-body {
  display: flex;
  flex: 1;
  flex-direction: column;
  padding: 1.15rem 1.3rem 1.3rem;
}
.tl-tag {
  margin-bottom: .3rem;
  color: var(--tl-purple);
  font-size: .82rem;
  font-weight: 700;
}
.tl-resource h3 {
  margin: 0 0 .45rem;
  color: var(--tl-navy);
  font-size: 1.1rem;
  line-height: 1.3;
}
.tl-resource p {
  flex: 1;
  margin: 0 0 1rem;
  color: var(--tl-muted);
  font-size: .92rem;
}
/* The whole card is clickable: the link stretches over it */
.tl-link {
  color: var(--tl-purple) !important;
  font-size: .92rem;
  font-weight: 700;
  text-decoration: none;
}
.tl-link::after { content: ""; position: absolute; inset: 0; }
.tl-resource:hover .tl-link { text-decoration: underline; }

/* ---------- External catalogue banner ---------- */
.tl-catalogue {
  display: grid;
  grid-template-columns: minmax(0, 1fr) auto;
  gap: 1.5rem;
  align-items: center;
  padding: 1.5rem 1.75rem;
  border-radius: 16px;
  background: linear-gradient(135deg, var(--tl-deep), var(--tl-purple));
  color: #ffffff;
  margin-bottom: 1rem;
}
.tl-catalogue h2 {
  margin: 0 0 .3rem;
  color: #ffffff;
  font-size: 1.25rem;
  line-height: 1.3;
}
.tl-catalogue p {
  max-width: 56ch;
  margin: 0;
  color: #f5e6f5;
  font-size: .7rem;
}
.tl-catalogue-button {
  display: inline-block;
  padding: .7rem 1.3rem;
  border-radius: 8px;
  background: #ffffff;
  color: var(--tl-deep) !important;
  font-size: .92rem;
  font-weight: 700;
  text-decoration: none;
  white-space: nowrap;
}
.tl-catalogue-button:hover { background: #f3e8f3; text-decoration: none; }
.tl-catalogue a:focus-visible { outline-color: #ffffff; }

/* ---------- Past event reports ---------- */
.tl-reports {
  overflow: hidden;
  border: 1px solid var(--tl-border);
  border-radius: 12px;
  background: #ffffff;
  gap:1rem;
}
.tl-report {
  position: relative;
  display: grid;
  grid-template-columns: 72px minmax(0, 1fr) auto;
  gap: 1.1rem;
  align-items: center;
  padding: 1rem 1.25rem;
}
.tl-report + .tl-report { border-top: 1px solid var(--tl-border); }
.tl-report:hover,
.tl-report:focus-within { background: var(--tl-soft); }
.tl-report-media {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 72px;
  height: 56px;
  padding: 6px;
  border: 1px solid var(--tl-border);
  border-radius: 8px;
  background: #ffffff;
}
.tl-report-media img { max-width: 100%; max-height: 100%; object-fit: contain; }
.tl-report h3 {
  margin: 0 0 .15rem;
  color: var(--tl-navy);
  font-size: 1rem;
  line-height: 1.3;
}
.tl-report p {
  margin: 0;
  color: var(--tl-muted);
  font-size: .88rem;
  line-height: 1.5;
}
.tl-report-link {
  color: var(--tl-purple) !important;
  font-size: .9rem;
  font-weight: 700;
  text-decoration: none;
  white-space: nowrap;
}
.tl-report-link::after { content: ""; position: absolute; inset: 0; }
.tl-report:hover .tl-report-link { text-decoration: underline; }

/* ---------- Responsive ---------- */
@media (max-width: 720px) {
  .tl-header h1 { font-size: 1.8rem; }
  .tl-event { grid-template-columns: 1fr; gap: 1.1rem; padding: 1.25rem; }
  .tl-date {
    flex-direction: row;
    justify-content: flex-start;
    gap: .6rem;
    align-self: start;
    justify-self: start;
    padding: .6rem 1rem;
  }
  .tl-date-days { font-size: 1.25rem; }
  .tl-date-month { margin-top: 0; }
  .tl-catalogue { grid-template-columns: 1fr; gap: 1rem; padding: 1.4rem; }
  .tl-catalogue-media { width: 112px; }
  .tl-catalogue-button { justify-self: start; }
  .tl-report { grid-template-columns: 56px minmax(0, 1fr); }
  .tl-report-media { width: 56px; height: 48px; }
  .tl-report-link { grid-column: 2; justify-self: start; }

  
}
@media (prefers-reduced-motion: no-preference) {
  html { scroll-behavior: smooth; }
}
</style>


<div class="tl-page">

<header class="tl-header">
<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1>Training & Upskilling</h1>
  </div>
</section>
</header>

<section id="catalogue">
<div class="tl-catalogue">
<div>
<h2>Build your own learning pathway!</h2>
        <p>Discover external training opportunities in HPC, AI, research software engineering, programming and performance optimisation. Browse the catalogue, check upcoming dates in the calendar, and build your own learning pathway or start from a curated one.</p>
</div>
<a href="/training/external-training-board" class="tl-catalogue-button">Create your own learning pathway</a>
</div>
</section>




<header class="tl-header">
<nav class="tl-nav" aria-label="On this page">
<a href="#upcoming-events">Upcoming training</a>
<a href="#resources">Learning resources</a>
<a href="#reports">Past event reports</a>
</nav>
</header>

<div class="tl-main">




<section id="upcoming-events">
  <div class="tl-section-head">
    <h2>Upcoming training events</h2>
    <p>Register for our upcoming training sessions and workshops.</p>
  </div>

  <article class="tl-event">
    <time class="tl-date" datetime="2026-12-15/2026-12-17">
      <span class="tl-date-days">15-17</span>
      <span class="tl-date-month">Dec 2026</span>
    </time>

    <div class="tl-event-content">
      <h3>Maximising and Evidencing Impact Bootcamp</h3>
      <p>
        Develop your skills in purposeful project design and evaluation,
        from one-off events to large-scale research programmes.
      </p>
      <a href="https://shareing-dri.github.io/events/202612_Bootcamp/"
         class="tl-button">
        Register to attend
        <span aria-hidden="true">→</span>
      </a>
    </div>
  </article>


  <article class="tl-event">
    <time class="tl-date" datetime="2026-12-15/2026-12-17">
      <span class="tl-date-days">17-20</span>
      <span class="tl-date-month">May 2027</span>
    </time>

    <div class="tl-event-content">
      <h3>55th VI-HPS Tuning Workshop</h3>
      <p>
        Four days of hands-on training with leading performance analysis tools, alongside an introduction to the performance engineering cycle, a systematic approach to analysing and improving application performance.
      </p>
      <a href=""
         class="tl-button">
        Registration will open soon
        <span aria-hidden="true">→</span>
      </a>
    </div>
  </article>



</section>



<section id="resources">
<div class="tl-section-head">
<h2>Other training opportunities</h2>
</div>
<div class="tl-grid">

<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/isc26/pic1.jpeg" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Funding</div>
<h3>Become a HPC Champions</h3>
<p>Our new initiative helps digital Research Technical Professionals build deeper expertise through structured, personalised learning. First up: Performance Analysis, with a VI-HPS workshop in Durham, 17-20 May 2027. </p>
<a href="/champions/hpc-champions" class="tl-link">Find out more and apply</a>
</div>
</article>

</div>
</section>



<section id="resources">
<div class="tl-section-head">
<h2>Learning resources</h2>
<p>Standalone material you can use at any time.</p>
</div>
<div class="tl-grid">



<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/hpc_knowledge_graph.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Course material</div>
<h3>HPC Concepts</h3>
<p>Basic revision material that's worth revisiting before any assessment or benchmarking exercise. Made for newcomers without a background in HPC.</p>
<a href="/hpc-concepts-course/" class="tl-link">Open the HPC Concepts material</a>
</div>
</article>


<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/c-course.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Course material</div>
<h3>Introduction to Scientific Software Programming in C and C++</h3>
<p>The course is aimed at PhD students, research software engineers and MSc students.</p>
<a href="https://training-academy.dirac.ac.uk/course/view.php?id=23" class="tl-link">Access the Course</a>
</div>
</article>

<article class="tl-resource">
<div class="tl-resource-media-small"><img src="/assets/images/signpost.svg" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Interactive map</div>
<h3>GPU programming knowledge graph</h3>
<p>A map of what you can learn about programming for GPUs, with links to where to learn more about each topic.</p>
<a href="/training/gpu-programming-roadmap" class="tl-link">Explore the map</a>
</div>
</article>

</div>
</section>






<section id="reports">
<div class="tl-section-head">
<h2>Past event reports</h2>
<p>Summaries and outcomes from workshops we have already run.</p>
</div>
<div class="tl-reports">


<article class="tl-report">
<div class="tl-report-media"><img src="/assets/logos/SwanseaUniversity.svg" alt="Swansea University" loading="lazy"></div>
<div>
<h3>Performance and Utilisation Monitoring Workshop</h3>
<p>Report on our Performance and Utilisation Monitoring of Accelerated Compute workshop.</p>
</div>
<a href="/assets/pdfs/performance-utilisation-monitoring-report.pdf" class="tl-report-link">Read the report</a>
</article>


<article class="tl-report">
<div class="tl-report-media"><img src="/assets/events-banner/correctness.png" alt="Durham, VI-HPS, UCL" loading="lazy"></div>
<div>
<h3>Correctness and Debugging Workshop</h3>
<p>Report on our Correctness and Debugging workshop series.</p>
</div>
<a href="/events/202511-correctness-workshop" class="tl-report-link">Read the report</a>
</article>
</div>
</section>
</div>
</div>
