---
layout: splash
title: "SHAREing's network"
permalink: /network/
classes: wide
---
<style>
.tl-page {
  --tl-purple: #940594;
  --tl-deep: #421456;
  --tl-soft: #faf5fa;
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
.tl-page a:focus-visible { outline: 3px solid var(--tl-purple); outline-offset: 3px; border-radius: 4px; }
.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  height: 40vh;
  background-image: url('/assets/images/group.avif');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #fff;
   background-position: 100% 20%;
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
  padding: 0 1rem;
}
.parallax-overlay h1 { font-size: 3rem; margin: 0 0 .5rem; color: #fff !important; }
.parallax-overlay p { max-width: 52ch; margin: 0; font-size: 1.05rem; color: #fff; }
.tl-nav { display: flex; flex-wrap: wrap; gap: .5rem; margin: 1.5rem 0 2.5rem; justify-content: center; }
.tl-nav a {
  padding: .4rem .9rem;
  border: 1px solid var(--tl-border);
  border-radius: 999px;
  background: #fff;
  color: var(--tl-text) !important;
  font-size: .88rem;
  text-decoration: none;
}
.tl-nav a:hover { border-color: var(--tl-purple); color: var(--tl-purple) !important; }
.tl-main section { margin-bottom: 3.5rem; scroll-margin-top: 5rem; }
.tl-section-head { width: min(1200px, 100vw - 2rem);
  position: relative;
  left: 50%;
  transform: translateX(-50%); margin-bottom: 1.25rem; }
.tl-section-head h2 { margin: 0; color: var(--tl-navy); font-size: 1.4rem; line-height: 1.3; }
.tl-section-head p { margin: .2rem 0 0; color: var(--tl-muted); font-size: .95rem; }
.tl-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.25rem;
 width: min(1200px, 100vw - 2rem);
  position: relative;
  left: 50%;
  transform: translateX(-50%);
}

.tl-resource {
  position: relative;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  border: 1px solid var(--tl-border);
  border-radius: 12px;
  background: #fff;
}
.tl-resource:hover, .tl-resource:focus-within { border-color: var(--tl-purple); }
.tl-resource-media {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 120px;
  padding: 1.25rem;
  border-bottom: 1px solid var(--tl-border);
  background: var(--tl-bg);
}
.tl-resource-media img { max-width: 100%; max-height: 100%; object-fit: contain; }
.tl-resource-body { display: flex; flex: 1; flex-direction: column; padding: 1.15rem 1.3rem 1.3rem; }
.tl-tag { margin-bottom: .3rem; color: var(--tl-purple); font-size: .82rem; font-weight: 700; }
.tl-resource h3 { margin: 0 0 .45rem; color: var(--tl-navy); font-size: 1.1rem; line-height: 1.3; }
.tl-resource p { flex: 1; margin: 0 0 1rem; color: var(--tl-muted); font-size: .92rem; }
.tl-link { color: var(--tl-purple) !important; font-size: .92rem; font-weight: 700; text-decoration: none; }
.tl-link::after { content: ""; position: absolute; inset: 0; }
.tl-resource:hover .tl-link { text-decoration: underline; }
.tl-catalogue {
  width: min(1200px, 100vw - 2rem);
  position: relative;
  left: 50%;
  transform: translateX(-50%);
  display: grid;
  grid-template-columns: minmax(0, 1fr) auto;
  gap: 1.5rem;
  align-items: center;
  padding: 1.5rem 1.75rem;
  border-radius: 16px;
  background: linear-gradient(135deg, var(--tl-deep), var(--tl-purple));
  color: #fff;
}
.tl-catalogue h2 { margin: 0 0 .3rem; color: #fff; font-size: 1.25rem; line-height: 1.3; }
.tl-catalogue p { max-width: 56ch; margin: 0; color: #f5e6f5; font-size: .92rem; }
.tl-catalogue-button {
  display: inline-block;
  padding: .7rem 1.3rem;
  border-radius: 8px;
  background: #fff;
  color: var(--tl-deep) !important;
  font-size: .92rem;
  font-weight: 700;
  text-decoration: none;
  white-space: nowrap;
}
.tl-catalogue-button:hover { background: #f3e8f3; text-decoration: none; }
.tl-catalogue a:focus-visible { outline-color: #fff; }
@media (max-width: 720px) {
  .parallax-hero { height: 32vh; background-attachment: scroll; }
  .parallax-overlay h1 { font-size: 2rem; }
  .parallax-overlay p { font-size: .95rem; }
  .tl-catalogue { grid-template-columns: 1fr; gap: 1rem; padding: 1.4rem; }
  .tl-catalogue-button { justify-self: start; }
}
@media (prefers-reduced-motion: no-preference) { html { scroll-behavior: smooth; } }
</style>
<section class="parallax-hero">
<div class="parallax-overlay">
<h1>Community</h1>
<p>The people, organisations and partners behind SHAREing.</p>
</div>
</section>


<div class="tl-page">
<nav class="tl-nav" aria-label="On this page">
<a href="#explore">Explore the network</a>
<a href="#partners">Partner organisations</a>
<a href="#involved">Get involved</a>
</nav>
<div class="tl-main">
<section id="explore">
<div class="tl-section-head">
<h2>Explore the network</h2>
<p>Choose the part of SHAREing you want to know more about.</p>
</div>


<div class="tl-grid">


<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">People</div>
<h3>HPC Champions</h3>
<p>Join the first cohort of dRTPs building expertise in performance analysis. Travel and accommodation are funded for the VI-HPS workshop in Durham.</p>
<a href="/network/hpc-champions" class="tl-link">Become a HPC Champions</a>
</div>
</article>


<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">People</div>
<h3>Our Team</h3>
<p>Meet our consortium team and the people behind SHAREing</p>
<a href="/about-overview/team-consortium" class="tl-link">Our Team</a>
</div>
</article>

<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">Backing</div>
<h3>Supporters</h3>
<p>The organisations and funders that make SHAREing's work possible.</p>
<a href="/network/supporters" class="tl-link">Visit our supporters</a>
</div>
</article>

<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">Guidance</div>
<h3>Advisory Board</h3>
<p>The people who guide SHAREing's priorities and help keep our work useful to the community.</p>
<a href="/about/advisory-board" class="tl-link">See the Advisory Board</a>
</div>
</article>







<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">Collaboration</div>
<h3>Industry</h3>
<p>How SHAREing works with companies, and how you can collaborate with us.</p>
<a href="/industry/" class="tl-link">Work with industry</a>
</div>
</article>


<article class="tl-resource">
<div class="tl-resource-body">
<div class="tl-tag">Meetings and training</div>
<h3>Events</h3>
<p>Workshops, meetings and training sessions you can attend or contribute to.</p>
<a href="/events/" class="tl-link">Browse events</a>
</div>
</article>



</div>
</section>
<section id="partners">
<div class="tl-section-head">
<h2>Partner organisations</h2>
<p>Projects and consortia we work alongside. These links open their own websites.</p>
</div>
<div class="tl-grid">
<article class="tl-resource">
<div class="tl-resource-media"><img src="https://www.cake.ac.uk/assets/images/cake-logo/CAKE_logo1.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag"></div>
<h3>CAKE</h3>
<p>The DRI's Computational Abilities Knowledge Exchange project coordinates and streamlines SHAREing's knowledge exchange and dissemination.</p>
<a href="https://cake-dri.github.io/" class="tl-link">Visit the CAKE website</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="https://erlangenhub.ox.ac.uk/wp-content/uploads/2025/04/cropped-Erlangen-AI-Hub-logo1-RGB-1-scaled-1-2048x242.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag"></div>
<h3>Erlangen AI Hub</h3>
<p>We cooperate with Hub members to link SHAREing's work to foundational mathematics research.</p>
<a href="https://erlangenhub.ox.ac.uk/" class="tl-link">Visit the Erlangen AI Hub website</a>
</div>
</article>
<article class="tl-resource">
<div class="tl-resource-media"><img src="https://www.exageo.org/wp-content/uploads/2024/11/exageo-logo-main.png" alt="" loading="lazy"></div>
<div class="tl-resource-body">
<div class="tl-tag"></div>
<h3>ExaGeo</h3>
<p>We cooperate with members of the ExaGeo consortium.</p>
<a href="https://www.exageo.org/" class="tl-link">Visit the ExaGeo website</a>
</div>
</article>
</div>
</section>


<section id="involved">
<div class="tl-catalogue">
<div>
<h2>Want to be part of the network?</h2>
<p>Whether you support research computing, work in industry or want to become an HPC Champion, we would like to hear from you.</p>
</div>
<a href="/contact/" class="tl-catalogue-button">Get in touch</a>
</div>
</section>
</div>
</div>