---
layout: splash
permalink: /
hidden: true
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/banner-big.png
---
<style>
.home {
  --purple: #68246d;
  --purple-light: #8b3a92;
  --purple-deep: #421456;
  --tint: #f3e8f5;
  --navy: #0f2a3a;
  --text: #334155;
  --muted: #64748b;
  --border: #e2e8f0;
  --shadow: 0 4px 16px rgba(15, 42, 58, .07);
  --shadow-hover: 0 10px 28px rgba(15, 42, 58, .12);
  font-size: .9rem;
  line-height: 1.55;
  color: var(--text);
}
.home *, .home *::before, .home *::after { box-sizing: border-box; }
.home h2, .home h3, .home h4, .home p { margin: 0; padding: 0; border: 0; }
.home a:focus-visible, .home summary:focus-visible {
  outline: 3px solid var(--purple);
  outline-offset: 3px;
  border-radius: 4px;
}
/* ---------- Banners ---------- */
.banner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem 2.5rem;
  margin: 0 0 1rem;
  padding: 1.3rem 1.75rem;
  border-radius: 8px;
}
.banner:first-child { margin-top: 2rem; }
.banner-text { min-width: 0; }
.banner-label {
  display: block;
  margin-bottom: .2rem;
  font-size: .78rem;
  font-weight: 600;
}
.banner h2 {
  margin: 0 0 .3rem;
  font-size: 1.15rem;
  line-height: 1.3;
}
.banner p {
  max-width: 75ch;
  margin: 0;
  font-size: .82rem;
  line-height: 1.6;
}
.banner-button {
  width: 10rem;   
  flex: none;
  padding: .55rem 1.2rem;
  border-radius: 6px;
  font-size: .82rem;
  font-weight: 600;
  text-align: center; 
  white-space: nowrap;
  text-decoration: none !important;
  transition: background .15s ease;
}

/* Champions: solid purple, the one strong element */
.banner--champions { background: var(--navy); color: #fff; }
.banner--champions .banner-label { color: #e9d3ec; }
.banner--champions h2,
.banner--champions p { color: #fff; }
.banner--champions .banner-button { background: #fff; color: var(--purple) !important; }
.banner--champions .banner-button:hover { background: var(--tint); }
.banner--champions a:focus-visible { outline-color: #fff; }

/* Pathway: quiet, outlined */
.banner--pathway {
  background: #fff;
  border: 1px solid var(--border);
  border-left: 4px solid var(--purple);
}
.banner--pathway .banner-label { color: var(--purple); }
.banner--pathway h2 { color: var(--navy); }
.banner--pathway p { color: var(--muted); }
.banner--pathway .banner-button { background: var(--purple); color: #fff !important; }
.banner--pathway .banner-button:hover { background: var(--purple-deep); }

@media (max-width: 700px) {
  .banner { flex-direction: column; align-items: flex-start; padding: 1.15rem 1.25rem; }
}
/* ---------- Section titles ---------- */
.home-title {
  margin: 3rem 0 1rem !important;
  color: var(--purple);
  font-size: 1.3rem;
  font-weight: 700;
  line-height: 1.25;
  text-align: left;
}

/* ---------- News cards ---------- */
.news-grid {
  display: flex;
  gap: 1.1rem;
  padding: .4rem .25rem 1.2rem;
  margin: 0 -.25rem;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-padding: 0 .25rem;
  scrollbar-width: thin;
  scrollbar-color: #cbb5ce transparent;
  
}
.news-grid::-webkit-scrollbar { height: 8px; }
.news-grid::-webkit-scrollbar-thumb { background: #cbb5ce; border-radius: 8px; }
.news-grid--wrap {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 800px), 1fr));
  overflow: visible;
  padding-bottom: .5rem;
}
.news-card {
  flex: 0 0 320px;
  display: flex;
  flex-direction: column;
  padding: 1.1rem 1.2rem 1rem;
  background: #fff;
  border: 1px solid var(--border);
  border-top: 3px solid var(--purple);
  border-radius: 12px;
  box-shadow: var(--shadow);
  scroll-snap-align: start;
  transition: transform .2s ease, box-shadow .2s ease;
}
.news-grid--wrap .news-card { flex: none; }
.news-card:hover { transform: translateY(-2px); box-shadow: var(--shadow-hover); }
.news-date {
  color: var(--purple);
  font-size: .72rem;
  font-weight: 700;
  letter-spacing: .06em;
  text-transform: uppercase;
}
.news-card h3 {
  margin: .35rem 0 .45rem;
  color: var(--navy);
  font-size: 1rem;
  line-height: 1.35;
}
.news-card p { margin: 0 0 .5rem; font-size: .85rem; line-height: 1.6; }
.news-card p:last-child { margin-bottom: 0; }
.news-card a { color: var(--purple); font-weight: 600; text-underline-offset: 2px; }
.news-card a:hover { color: var(--purple-light); }

/* ---------- Past news ---------- */
.past-news { margin-top: .5rem; }
.past-news summary {
  display: inline-flex;
  align-items: center;
  gap: .4rem;
  color: var(--purple);
  font-size: 1.05rem;
  font-weight: 700;
  cursor: pointer;
  list-style: none;
}
.past-news summary::-webkit-details-marker { display: none; }
.past-news summary::after { content: "\25BE"; font-size: 1rem; transition: transform .2s ease; }
.past-news[open] > summary::after { transform: rotate(180deg); }
.past-news summary:hover { color: var(--purple-light); }
.past-news .news-grid--wrap { margin-top: 1rem; }
.past-news .past-news { margin-top: 1.5rem; }
.past-news .past-news summary { font-size: .95rem; }


/* ---------- All about SHAREing ---------- */
.tl-grid {
  margin-top: 2rem;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 350px), 1fr));
  gap: 1.25rem;
}
.tl-resource {
  position: relative;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  border: 1px solid var(--border);
  border-radius: 12px;
  background: #fff;
}
.tl-resource:hover, .tl-resource:focus-within { border-color: var(--purple); }
.tl-resource-media {
  height: 160px;               /* adjust to taste */
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
.tl-resource-body { display: flex; flex: 1; flex-direction: column; padding: 1.1rem 1.25rem 1.25rem; }
.tl-tag { margin-bottom: .3rem; color: var(--purple); font-size: .75rem; font-weight: 700; }
.tl-resource h3 { margin: 0 0 .4rem; color: var(--navy); font-size: 1.05rem; line-height: 1.3; }
.tl-resource p { flex: 1; margin: 0 0 1rem; color: var(--muted); font-size: .85rem; line-height: 1.6; }
.tl-link { color: var(--purple) !important; font-size: .85rem; font-weight: 700; text-decoration: none !important; }
.tl-link::after { content: ""; position: absolute; inset: 0; }
.tl-resource:hover .tl-link { text-decoration: underline !important; }

/* ---------- Social and acknowledgements ---------- */
.social-buttons { display: flex; justify-content: center; flex-wrap: wrap; gap: .8rem; margin: 2.5rem 0; }
.social-buttons .btn {
  margin: 0;
  padding: .65rem 1.6rem;
  background: var(--purple);
  border-radius: 999px;
  color: #fff;
  font-size: .85rem;
  font-weight: 700;
  transition: background .15s ease;
}
.social-buttons .btn:hover { background: var(--purple-light); }
.acknowledgements p { max-width: 70ch; font-size: .85rem; }
.acknowledgements img { display: block; width: auto; max-width: 100%; height: auto; max-height: 90px; margin-top: 1rem; }

@media (max-width: 600px) {
  .banner { padding: 1.2rem 1.15rem; }
  .news-card { flex-basis: 85%; }
  .home-title { margin-top: 2.5rem !important; }
}
@media (prefers-reduced-motion: reduce) {
  .news-card, .offering-card, .banner-button, .past-news summary::after { transition: none; }
  .news-card:hover, .offering-card:hover { transform: none; }
}
</style>
<div class="home">
<section class="banner banner--champions">
<div class="banner-text">
<span class="banner-label">Applications open 2 November</span>
<h2>Become a SHAREing HPC Champion</h2>
<p>We are launching the HPC Champions programme, and applications will open on <strong>2 November 2026</strong>. Find out what it involves and how to get ready to apply.</p>
</div>
<a href="/champions/hpc-champions" class="banner-button">Find out more</a>
</section>
<section class="banner banner--pathway">
<div class="banner-text">
<span class="banner-label">New resource</span>
<h2>Learning Pathway Builder</h2>
<p>Discover external training opportunities in HPC, AI, research software engineering, programming and performance optimisation. Browse the catalogue, check upcoming dates in the calendar, and build your own learning pathway or start from a curated one.</p>
</div>
<a href="/training/external-training-board" class="banner-button">Explore the catalogue</a>
</section>



<section class="section-wide">
<h2 class="home-title">Latest news</h2>
<div class="news-grid news-grid--wrap">
<div class="news-card">
<span class="news-date">October 2026</span>
<h3>Next round of SHAREing's Flexible Funds is now open</h3>
<p>The next round to propose a solution to a current open task is now open. Check out the current <a href="https://shareing-dri.github.io/task-map/">open tasks</a>. The current deadline to <a href="/about/propose-a-solution">propose a solution to an open task</a> is <strong>20 November 2026 at 23:59 (UK time)</strong>.</p>
</div>
<div class="news-card">
<span class="news-date">September 2026</span>
<h3>Our latest technical blog: getting started with benchmarking</h3>
<p>Following his experiences as one of the RSEs setting up SHAREing's performance assessment service, Thomas Flynn has written a blog to help developers get started with effective code benchmarking. See Thomas' blog in full <a href="/blogpost/benchmarking-practice/">here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">September 2026</span>
<h3>SHAREing receives a poster prize at RSECon26!</h3>
<p>We are delighted to share that SHAREing has won one of the poster prizes at RSECon26. Congratulations to the whole SHAREing team on this fantastic achievement, and a big thank you to the RSECon26 organising team for putting together such a great conference. <a href="https://zenodo.org/records/22129792">See the poster here</a>.</p>
</div>
</div>
<details class="past-news">
<summary>Past news</summary>
<div class="news-grid news-grid--wrap">
<div class="news-card">
<span class="news-date">September 2026</span>
<h3>Suggest a new SHAREing task</h3>
<p>The next SHAREing Flexible Fund round is now open for new task suggestions. Have an idea that fits one of our Work Package themes? <strong>Submit your suggestion by 22 September 2026</strong> to have it considered for the next funding call, which will open on <strong>2 October</strong> and close on <strong>20 November 2026</strong>. Find out more and <a href="/about/suggest-a-task">suggest a new task here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">September 2026</span>
<h3>New SHAREing tasks funded</h3>
<p>We are pleased to announce the new tasks funded through the latest SHAREing funding call, covering activities across our different Work Packages. These tasks will help address priorities identified by the UK DRI community and support the development of new skills, resources and training. <a href="https://shareing-dri.github.io/tasks-in-progress/">Find out more about the funded tasks here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">June 2026</span>
<h3>Durham HPC Days 2026</h3>
<p>This year's Durham HPC Days received great support from SHAREing. Eva Fernandez Amez takes us behind the scenes <a href="/blogpost/hpcdays-2026/">in this blog post</a>, offering a sneak peek into what goes into organising a conference, how it can best serve the community, and how it helps strengthen the projects that bring us together.</p>
</div>
<div class="news-card">
<span class="news-date">May 2026</span>
<h3>Collaboration Workshop 2026 (CW26)</h3>
<p>Our Community Manager, Eva Fernandez Amez, reflects on her experience at CW26 and shares the key takeaways from the SHAREing and CAKE workshop held during the conference. <a href="/blogpost/CW-26/">Read the full blog post</a>.</p>
</div>
<div class="news-card">
<span class="news-date">May 2026</span>
<h3>Next round of SHAREing's Flexible Funds is now open</h3>
<p>The next round to propose a solution to a current open task is now open. Check out the current open tasks or <a href="/about/suggest-a-task">suggest a new task</a>.</p>
<p>The deadline to <a href="/about/propose-a-solution">propose a solution to an open task</a> was <strong>8 July 2026</strong>.</p>
</div>
<div class="news-card">
<span class="news-date">April 2026</span>
<h3>DRI Retreat 2026</h3>
<p>Some of our team members had the opportunity to attend the DRI Retreat in Manchester this past March. Our Community Manager, Eva Fernandez Amez, reflects on her first experience at the retreat and shares key takeaways that we're looking to incorporate into SHAREing's work. <a href="/blogpost/dri-retreat-26/">Read the full blog post</a>.</p>
</div>
<div class="news-card">
<span class="news-date">March 2026</span>
<h3>Performance and Utilisation Monitoring of Accelerated Compute</h3>
<p>A report on our recent Performance and Utilisation Monitoring of Accelerated Compute workshop is now available on the <a href="/events/202602-performance-monitoring/">event's page</a>.</p>
</div>
<div class="news-card">
<span class="news-date">March 2026</span>
<h3>SIAM PP26</h3>
<p>SHAREing was presented recently at the SIAM Parallel Processing 2026 (PP26) conference as a poster submission by Thomas Flynn. He has also summarised his thoughts on the conference <a href="/blogpost/siampp26/">here</a>, including themes that are relevant to SHAREing and digital Research Technical Professionals (dRTPs) more broadly.</p>
</div>
<div class="news-card">
<span class="news-date">February 2026</span>
<h3>SHAREing Flexible Funds now open UK-wide</h3>
<p>SHAREing has opened its Flexible Fund opportunities to all contributors based at UK universities or other organisations eligible for UKRI funding. You no longer need to be part of a consortium institution to apply. You can <a href="/about/suggest-a-task">suggest a new task</a> (rolling call) or <a href="/about/propose-a-solution">propose a solution to an open task</a> (reviewed quarterly; deadline was <strong>23 March</strong>).</p>
<p>Explore open opportunities on the <a href="/task-map">Task Map</a>.</p>
</div>
<div class="news-card">
<span class="news-date">January 2026</span>
<h3>SHAREing Retreat, January 2026</h3>
<p>For the first time since the beginning of the project, the consortium came together in person, an important milestone and a valuable opportunity to reflect collectively on our progress. <a href="/blogpost/retreat-2026/">Read this blog post</a> for a summary of the outcomes.</p>
</div>
</div>
<details class="past-news">
<summary>2025 news</summary>
<div class="news-grid news-grid--wrap">
<div class="news-card">
<span class="news-date">December 2025</span>
<h3>CIUK 2025</h3>
<p>Multiple members of SHAREing attended CIUK 2025 in December, including talks from SHAREing's Martyn Guest and Eva Fernandez Amez. An overview of these talks can be found <a href="/events/202512-CIUK25/">here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">December 2025</span>
<h3>Correctness and Debugging Workshop</h3>
<p>A report on our recent Correctness and Debugging workshop series is now available on the <a href="/events/202511-correctness-workshop/">event's site</a>.</p>
</div>
<div class="news-card">
<span class="news-date">November 2025</span>
<h3>Performance Assessment Webinar</h3>
<p>In early November SHAREing organised an online seminar dedicated to performance assessments, with talks given by representatives from Durham University, Barcelona Supercomputing Centre, Cardiff University and DiRAC. Please see <a href="/events/202511-performance-webinar/">here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">October 2025</span>
<h3>HPC–AI Conference presentation</h3>
<p>At the HPC–AI Conference, Tobias Weinzierl introduced SHAREing in a dedicated talk highlighting its mission to strengthen the UK's Digital Research Infrastructure (DRI) landscape. The presentation covered SHAREing's goals, structure and upcoming activities, emphasising its role in connecting the UK's DRI community and advancing performance assessment and training initiatives. Please watch the recording <a href="https://durham.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=5a91c0b6-acc9-4a3c-9c00-b39200b39edd">here</a>.</p>
</div>
<div class="news-card">
<span class="news-date">October 2025</span>
<h3>Second round of call for projects</h3>
<p>SHAREing's second round of call for projects has been launched. This is a consortium-internal call only. For details on SHAREing's internal organisation, please consult the <a href="https://shareing-dri.github.io/about/organisation">description of SHAREing's internal organisation</a>.</p>
</div>
<div class="news-card">
<span class="news-date">August 2025</span>
<h3>First round of call for projects</h3>
<p>SHAREing's first round of call for projects has been launched. For details on SHAREing's internal organisation, please consult the <a href="https://shareing-dri.github.io/about/organisation">description of SHAREing's internal organisation</a>.</p>
</div>
<div class="news-card">
<span class="news-date">July 2025</span>
<h3>Work package scoping meetings</h3>
<p>The first work package scoping meetings have kicked off. Details can be found in the sections on <a href="/assessment/">performance assessment</a>.</p>
</div>
</div>
</details>
</details>
</section>

<h2 class="home-title">About SHAREing</h2>

<div class="tl-grid">
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/hpc-ai.jpg" alt="" loading="lazy"></div>

<div class="tl-resource-body">




<div class="tl-tag">Overview</div>
<h3>About SHAREing</h3>
<p>More about SHAREing, its vision and the people behind the project.</p>
<a href="/about-overview/" class="tl-link">Find out more about SHAREing</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/performance-assessment-1.jpg" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Assessments</div>
<h3>Performance and machine assessments</h3>
<p>SHAREing provides performance and machine assessments to the wider UK computational science community.</p>
<a href="/assessment/" class="tl-link">See the assessments</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/hpc-foundations-knowledge-graph.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Training</div>
<h3>Training</h3>
<p>SHAREing collects information around accelerator-focused training and also creates its own training material.</p>
<a href="/training/" class="tl-link">Explore training</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/ciuk.jpg" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Community</div>
<h3>SHAREing events</h3>
<p>Many of SHAREing's core outputs are delivered through a wide range of community events.</p>
<a href="/events/" class="tl-link">View the schedule</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/sc-booth.avif" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Resources</div>
<h3>SHAREing resources</h3>
<p>SHAREing's outcomes and materials are freely available to the UK research community.</p>
<a href="/resources/" class="tl-link">Access the resources</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="/assets/images/team-sc.avif" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag">Partners</div>
<h3>Community</h3>
<p>SHAREing is embedded in a strong network of Digital Research Infrastructure partners.</p>
<a href="/network/" class="tl-link">Explore the network</a>
</div>
</article>
</div>





<div class="social-buttons">
<a href="https://www.linkedin.com/company/shareing/" class="btn btn--primary">LinkedIn</a>
<a href="https://bsky.app/profile/shareing.bsky.social" class="btn btn--primary">Bluesky</a>
</div>
<section class="section-wide acknowledgements">
<h2 class="home-title">Acknowledgements</h2>
<p>This project has received funding through the UKRI Digital Research Infrastructure Programme under grant UKRI1801 (SHAREing).</p>
<img src="/assets/logos/ukri.png" alt="UKRI logo">
</section>
</div>