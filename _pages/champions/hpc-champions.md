---
title: "HPC Champions: Performance Analysis"
layout: splash
permalink: /champions/hpc-champions/
classes: wide
champions_pathway:
  - topic: "Introduction to UNIX"
    note: "Command-line and shell essentials."
    urls:
      - "https://librarycarpentry.org/lc-shell/"
  - topic: "Introduction to HPC"
    note: "What HPC systems are and how to use them."
    urls:
      - "https://www.archer2.ac.uk/training/courses/240000-intro-hpc-self-service/"
  - topic: "Fundamentals of HPC"
    note: "The core concepts that underpin performance."
    urls:
      - "https://shareing-dri.github.io/hpc-concepts-course/"
  - topic: "Scientific Programming in C/C++"
    note: "Later topics apply equally to Fortran users."
    urls:
      - "https://training-academy.dirac.ac.uk/enrol/index.php?id=23"
  - topic: "Parallelism: MPI and OpenMP"
    note: "Distributed- and shared-memory programming."
    urls:
      - "https://www.archer2.ac.uk/training/courses/210000-mpi-self-service/"
      - "https://www.archer2.ac.uk/training/courses/210000-openmp-self-service/"
  - topic: "Refresher: Fundamentals of HPC"
    kind: optional
    note: "Consolidate your knowledge before the workshop."
    urls:
      - "https://shareing-dri.github.io/hpc-concepts-course/"
  - topic: "VI-HPS Workshop, Durham"
    kind: final
    note: "Put it all into practice with leading performance analysis tools."
    urls:
      - "https://www.vi-hps.org/training/tws/tuning-workshop-series.html"
---

<div class="hc" id="hc" markdown="0">

<!-- ================= HERO ================= -->
<header class="hc-hero">
  <div class="hero-main">
    <span class="hero-kicker">Call for applications</span>
    <h1>HPC Champions: Performance Analysis</h1>
    <p>Join the first cohort of dRTPs building expertise in performance analysis. Travel and accommodation are funded for the VI-HPS workshop in Durham.</p>
    <div class="hero-actions">
      <a class="hc-btn hc-btn-light" href="">Applications open 2 November</a>
      <a class="hc-btn hc-btn-ghost" href="#journey">See the learning journey</a>
    </div>
  </div>
  <dl class="hero-facts">
    <div><dt>Apply by</dt><dd>23 Nov 2026</dd></div>
    <div><dt>Workshop</dt><dd>17-20 May 2027</dd></div>
    <div><dt>Where</dt><dd>Durham</dd></div>
    <div><dt>Funding</dt><dd>Travel and accommodation</dd></div>
  </dl>
</header>

<nav class="hc-nav" aria-label="On this page">
  <a href="#about">About</a>
  <a href="#journey">Learning journey</a>
  <a href="#included">What's included</a>
  <a href="#apply">Apply</a>
</nav>

<!-- ================= ABOUT ================= -->
<section class="hc-section" id="about">
  <h2>About HPC Champions</h2>
  <p class="hc-lead">HPC Champions is Durham’s HAI-End initiative for digital Research Technical Professionals (dRTPs) who want to build deep skills and expertise in one particular area.</p>

  <div class="hc-steps">
    <div><span>1</span><h3>Check the skills graph</h3><p>See which skills the workshop builds on.</p></div>
    <div><span>2</span><h3>Fill your gaps</h3><p>Study what you are missing before the workshop.</p></div>
    <div><span>3</span><h3>Attend, funded</h3><p>Arrive prepared. We cover your travel.</p></div>
  </div>

  <details class="hc-acc" open>
    <summary>What does this mean?</summary>
    <div class="hc-acc-body">
      <p>Traditionally, PhD students, postdocs, RSEs and academics from across the UK attend individual courses to gain the knowledge they need for their particular project. How much they get out of a workshop depends not only on its content but also on what they already know. This poses a challenge for instructors, who never know what skills participants will bring. It also quickly leads to siloed expertise, unless participants use the workshop as a springboard to learn beyond the boundaries of their immediate problem.</p>
      <p>With the HPC Champions concept, we move towards a more formal, structured approach to upskilling, without the heavy overhead of requiring people to complete full courses.</p>
      <p>Each Champion flavour comes with a template skills graph. When we announce a workshop, we also publish the skills it builds on, which form its prerequisites, together with suggested preparatory courses. We expect attendees to work through this skills graph and identify which skills they already have. For any they don’t, we point them to resources where they can study the topic before the workshop.</p>
      <p class="hc-key">The skills graph is a template, not a rulebook. Participants may find alternative courses or training that cover the required skills, or confirm that they already have them. What matters is that every successful applicant actively reflects on what they know and what they still need to learn before joining the workshop. This is what makes them true HPC Champions.</p>
      <p>Because participants commit to some preparatory study, we get a more consistent audience. The skills graph also tells people what to expect from the workshop, which makes the sessions more productive for everyone. In return for this effort, we provide travel funding.</p>
    </div>
  </details>

  <details class="hc-acc" open>
    <summary>Champions come in different flavours</summary>
    <div class="hc-acc-body">
      <p>For HPC Champions in Performance Analysis, we offer a curated learning pathway that leads participants all the way to a VI-HPS workshop in Durham. Both this website and the HAI-End team will help participants shape the pathway into a personalised journey that fits their individual starting point.</p>
      <p><strong>As a Champion, your travel and accommodation for the workshop are covered.</strong></p>
    </div>
  </details>
</section>

<!-- ================= JOURNEY ================= -->
<section class="hc-section" id="journey">
  <h2>The learning journey</h2>
  <div class="hc-split">
    <aside class="hc-side">
      <p>All material is free to follow and self-study, so join at the point that matches your experience. Completion is not formally assessed, but working through the steps will significantly increase the value you get from the VI-HPS workshop.</p>
      <div class="hc-callout">
        <strong>Make it your own.</strong> The route is a suggestion. Load it in the <a href="{{ site.baseurl }}/training/external-training-board">Learning Pathway Builder</a> to reorder it, add courses and download your version. Mentoring sessions with the HAI-End team will help you plan it.
      </div>
      <a class="hc-btn hc-btn-outline" href="{{ site.baseurl }}/training/external-training-board">Open the pathway builder</a>
    </aside>

  {%- assign catalogue = site.data["external-training"] %}
  {%- assign steps = page.champions_pathway %}
  {%- assign optional_count = steps | where: "kind", "optional" | size %}
  {%- assign step_count = steps.size | minus: optional_count %}
  {%- assign n = 0 %}

  <article class="hc-path">
    <p class="path-stats">{{ step_count }} steps{% if optional_count > 0 %}, {{ optional_count }} optional{% endif %} · start wherever suits your experience</p>
<ol class="path-steps">
{%- for step in steps %}
    {%- assign kind = step.kind | default: "required" %}
    {%- if kind != "optional" %}{% assign n = n | plus: 1 %}{% endif %}
    <li class="path-step{% if kind == 'optional' %} is-optional{% elsif kind == 'final' %} is-final{% endif %}">
    <span class="path-dot">{% if kind == 'optional' %}opt{% else %}{{ n }}{% endif %}</span>
    <div class="path-box">
        {%- if kind == 'optional' %}<div class="path-label">Optional</div>{% endif %}
        <div class="path-topic">{{ step.topic }}</div>
        {%- for u in step.urls %}
        {%- assign course = nil %}
        {%- for row in catalogue %}
            {%- assign row_url = row.url | strip %}
            {%- if row_url == u %}
            {%- assign course = row %}
            {%- break %}
            {%- endif %}
        {%- endfor %}
        {%- if course %}
            {%- assign fmt = course.format | strip %}
            {%- assign meta = course.organisation | strip %}
            {%- if fmt == "Online (self-service)" %}
            {%- assign meta = meta | append: " · On-demand" %}
            {%- else %}
            {%- assign meta = meta | append: " · " | append: fmt %}
            {%- assign dates = course.dates | strip %}
            {%- if dates != "" %}{% assign meta = meta | append: " · " | append: dates %}{% endif %}
            {%- assign loc = course.location | strip %}
            {%- if loc != "" and loc != "Online" %}{% assign meta = meta | append: " · " | append: loc %}{% endif %}
            {%- endif %}
        <div class="path-course">
        <a class="path-link" href="{{ u }}" target="_blank" rel="noopener noreferrer">{{ course.title | strip | escape }}</a>
        <div class="path-sub">{{ meta | escape }}</div>
        </div>
        {%- else %}
        <!-- HPC Champions: {{ u }} not found in _data/external-training.csv -->
        <div class="path-course"><a class="path-link" href="{{ u }}" target="_blank" rel="noopener noreferrer">{{ u }}</a></div>
        {%- endif %}
        {%- endfor %}
        {%- if step.note %}<div class="path-note">{{ step.note }}</div>{% endif %}
    </div>
    </li>
{%- endfor %}
</ol>
  </article>
  </div>
</section>

<!-- ================= INCLUDED ================= -->
<section class="hc-section" id="included">
  <h2>What's included</h2>
  <div class="hc-split hc-split-even">
    <div class="hc-panel">
      <h3>The VI-HPS workshop</h3>
      <p>Three days of hands-on training with leading performance analysis tools, alongside an introduction to the <strong>performance engineering cycle</strong>, a systematic approach to analysing and improving application performance.</p>
      <ul class="hc-chips">
        <li>MAQAO</li><li>Score-P</li><li>Scalasca</li><li>Cube</li><li>Vampir</li>
      </ul>
      <p><strong>Bring your own code.</strong> The workshop ends with significant time to apply the tools to your own software. If you don't have a suitable code, we can supply some.</p>
    </div>
    <div class="hc-panel">
      <h3>Support through the year</h3>
      <p>Alongside the learning journey, we are developing activities to support Champions.</p>
      <ul class="hc-list">
        <li><strong>Online kickoff:</strong> an overview of the learning journey and an introduction to the cohort.</li>
        <li><strong>Support to build your own pathway:</strong> sessions to design a personalised pathway.</li>
        <li><strong>Assessment methodology session:</strong> an introduction to SHAREing's <a href="{{ site.baseurl }}/assessment/">performance assessment</a> approach.</li>
        <li><strong>Early testbed access:</strong> explore novel hardware and tools ahead of the workshop.</li>
        <li><strong>Cohort meet-ups:</strong> regular get-togethers to showcase and discuss your work.</li>
        <li><strong>Workshop social:</strong> an evening get-together in Durham.</li>
      </ul>
      <p class="hc-note">Details will be confirmed to the cohort as plans are finalised.</p>
    </div>
  </div>
</section>

<!-- ================= APPLY ================= -->
<section class="hc-section" id="apply">
  <h2>Apply</h2>
  <div class="hc-split hc-split-even-apply">
    <div>
      <h3 class="hc-h3">Who should apply?</h3>
      <p class="hc-sub">You do not need to be an expert. The learning journey is designed to bring you up to speed.</p>
      <ul class="hc-checks">
        <li>You are a dRTP interested in performance analysis of research software.</li>
        <li>You work with, or are preparing to work with, HPC systems.</li>
        <li>You can attend the VI-HPS workshop in Durham, 17-20 May 2027.</li>
        <li>You want to engage with, and contribute to, a cohort of peers.</li>
      </ul>
    </div>
    <div>
      <h3 class="hc-h3">Key dates</h3>
      <ol class="hc-timeline">
        <li><span>Mon 2 Nov 2026</span><strong>Applications open</strong></li>
        <li><span>Mon 23 Nov 2026, 23:59 UK</span><strong>Applications close</strong></li>
        <li><span>By Mon 14 Dec 2026</span><strong>You hear from us</strong><em>Then join the online kickoff and begin the learning journey.</em></li>
      </ol>
    </div>
  </div>
  <div class="hc-cta">
    <div>
      <h3>Ready to become a Champion?</h3>
      <p>Know a colleague who would benefit? Please share this call. Questions? Visit our <a href="{{ site.baseurl }}/contact/">Contact</a> page.</p>
    </div>
    <a class="hc-btn hc-btn-light" href="">Applications open 2 November</a>
  </div>
</section>

</div>

<style>
/* Scoped to .hc and sized in px (Minimal Mistakes scales the root font size). */
.hc {
    --brand: #940594; --brand-dark: #6f046f; --deep: #421456; --tint: #f7eef7; --tint-2: #efdcef;
    --ink: #243855; --mut: #636d7c; --line: #e5e7eb; --blue: #31577a; --blue-back: #f1f6fb; --blue-line: #b9cde3;
    font-size: 15px; line-height: 1.6; color: var(--ink); margin: 0 0 32px; text-align: left; scroll-behavior: smooth;
}
.hc, .hc * { box-sizing: border-box; }
.hc h1, .hc h2, .hc h3, .hc p, .hc ul, .hc ol, .hc li, .hc dl, .hc dd, .hc dt {
    margin: 0; padding: 0; border: 0; font-family: inherit; text-indent: 0; text-transform: none; letter-spacing: normal;
}
.hc ul, .hc ol { list-style: none; }
.hc p { font-size: 15px; line-height: 1.6; }
.hc a { color: var(--brand); text-decoration: none; }
.hc p a:hover { text-decoration: underline; }
.hc :focus-visible { outline: 2px solid var(--brand); outline-offset: 2px; }
.hc section[id] { scroll-margin-top: 64px; }

/* Hero */
.hc .hc-hero { display: grid; grid-template-columns: minmax(0, 1fr) 260px; gap: 36px; align-items: center; margin: 24px 0 0; padding: 44px 40px; border-radius: 14px; background: var(--deep); color: #fff; }
.hc .hero-kicker { display: inline-block; margin-bottom: 14px; padding: 4px 12px; border-radius: 14px; background: rgba(255,255,255,.14); color: #f1dff7; font-size: 13px; font-weight: 600; }
.hc .hc-hero h1 { margin-bottom: 12px; font-size: 36px; line-height: 1.15; font-weight: 700; color: #fff; }
.hc .hc-hero p { max-width: 600px; color: #e6d3ee; font-size: 17px; line-height: 1.5; }
.hc .hero-actions { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 24px; }
.hc .hero-facts { display: grid; gap: 0; border-left: 1px solid rgba(255,255,255,.2); padding-left: 28px; }
.hc .hero-facts div { padding: 10px 0; }
.hc .hero-facts dt { font-size: 13px; color: #d9c0e6; }
.hc .hero-facts dd { font-size: 17px; font-weight: 700; color: #fff; }

/* Buttons */
.hc .hc-btn { display: inline-flex; align-items: center; justify-content: center; height: 42px; padding: 0 20px; border: 1px solid transparent; border-radius: 8px; font-size: 15px; font-weight: 600; line-height: 1; white-space: nowrap; cursor: pointer; transition: background .15s, border-color .15s; }
.hc .hc-btn-light { background: #fff; color: var(--deep); }
.hc .hc-btn-light:hover { background: var(--tint-2); }
.hc .hc-btn-ghost { border-color: rgba(255,255,255,.45); color: #fff; }
.hc .hc-btn-ghost:hover { background: rgba(255,255,255,.12); border-color: #fff; }
.hc .hc-btn-outline { border-color: var(--brand); background: #fff; color: var(--brand); }
.hc .hc-btn-outline:hover { background: var(--tint-2); }

/* Sticky nav */
.hc .hc-nav { position: flex; top: 0; z-index: 30; display: flex; gap: 6px; margin: 0; padding: 10px 0; background: rgba(255,255,255,.96); border-bottom: 1px solid var(--line); overflow-x: auto; margin-top: 1rem; border-radius: 16px;}
.hc .hc-nav a { padding: 6px 14px; border-radius: 16px; color: var(--mut); font-size: 14px; font-weight: 600; white-space: nowrap; }
.hc .hc-nav a:hover { background: var(--tint); color: var(--brand); }

/* Sections */
.hc .hc-section { margin-top: 56px; }
.hc .hc-section h2 { margin-bottom: 14px; font-size: 26px; line-height: 1.25; font-weight: 700; color: var(--deep); }
.hc .hc-lead {margin-bottom: 20px; font-size: 17px; line-height: 1.55; }
.hc .hc-h3 { margin-bottom: 4px; font-size: 18px; font-weight: 700; color: var(--deep); }
.hc .hc-sub { margin-bottom: 12px; color: var(--mut); }
.hc .hc-note { margin-top: 12px; color: var(--mut); font-size: 14px; font-style: italic; }

/* About: steps + accordions */
.hc .hc-steps { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 16px; margin-bottom: 20px; }
.hc .hc-steps div { padding: 16px 18px; border: 1px solid var(--line); border-radius: 12px; background: #fff; }
.hc .hc-steps span { display: inline-flex; align-items: center; justify-content: center; width: 26px; height: 26px; margin-bottom: 8px; border-radius: 50%; background: var(--tint-2); color: var(--brand-dark); font-size: 13px; font-weight: 700; }
.hc .hc-steps h3 { font-size: 16px; font-weight: 700; color: var(--deep); }
.hc .hc-steps p { color: var(--mut); font-size: 14px; }
.hc .hc-acc { margin-top: 10px; border: 1px solid var(--line); border-radius: 10px; background: #fff; }
.hc .hc-acc summary { padding: 14px 18px; color: var(--deep); font-size: 16px; font-weight: 700; cursor: pointer; list-style: none; }
.hc .hc-acc summary::-webkit-details-marker { display: none; }
.hc .hc-acc summary::after { content: "+"; float: right; color: var(--brand); font-size: 20px; line-height: 1; }
.hc .hc-acc[open] summary::after { content: "−"; }
.hc .hc-acc summary:hover { background: var(--tint); border-radius: 10px; }
.hc .hc-acc-body {  padding: 0.25rem 2rem 1rem 2rem; }
.hc .hc-acc-body p + p { margin-top: 12px; }
.hc .hc-key { padding: 14px 18px; border-left: 4px solid var(--brand); border-radius: 10px; background: var(--tint); color: var(--deep); }

/* Split layouts */
.hc .hc-split { display: grid; grid-template-columns: 320px minmax(0, 1fr); gap: 40px; align-items: start; }
.hc .hc-split-even { grid-template-columns: repeat(1, minmax(0, 1fr)); gap: 24px; }
.hc .hc-split-even-apply { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 24px; }
.hc .hc-side { position: sticky; top: 76px; display: grid; gap: 16px; justify-items: start; }
.hc .hc-callout { padding: 14px 18px; border-left: 4px solid var(--blue); border-radius: 0 8px 8px 0; background: var(--blue-back); font-size: 14px; }
.hc .hc-callout strong { color: var(--blue); }
.hc .hc-panel { padding: 22px; border: 1px solid var(--line); border-radius: 12px; background: #fff; }
.hc .hc-panel h3 { margin-bottom: 8px; font-size: 18px; font-weight: 700; color: var(--deep); }
.hc .hc-panel p + p, .hc .hc-panel .hc-chips + p { margin-top: 12px; }
.hc .hc-chips { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 12px; }
.hc .hc-chips li { padding: 4px 12px; border: 1px solid var(--blue-line); border-radius: 14px; background: var(--blue-back); color: var(--blue); font-size: 13px; font-weight: 600; }
.hc .hc-list { margin-top: 10px; }
.hc .hc-list li { padding: 9px 0; border-top: 1px solid var(--line); font-size: 14px; color: var(--mut); }
.hc .hc-list strong { color: var(--ink); }

/* Apply */
.hc .hc-checks li { position: relative; padding: 9px 0 9px 34px; border-top: 1px solid var(--line); }
.hc .hc-checks li:last-child { border-bottom: 1px solid var(--line); }
.hc .hc-checks li::before { content: "✓"; position: absolute; left: 2px; top: 10px; display: flex; align-items: center; justify-content: center; width: 22px; height: 22px; border-radius: 50%; background: var(--tint-2); color: var(--brand-dark); font-size: 13px; font-weight: 700; }
.hc .hc-timeline { margin-top: 12px; border-left: 2px solid var(--tint-2); }
.hc .hc-timeline li { position: relative; padding: 0 0 18px 22px; }
.hc .hc-timeline li::before { content: ""; position: absolute; left: -7px; top: 4px; width: 12px; height: 12px; border-radius: 50%; background: var(--brand); }
.hc .hc-timeline span { display: block; color: var(--brand); font-size: 13px; font-weight: 700; }
.hc .hc-timeline strong { display: block; color: var(--deep); font-size: 16px; }
.hc .hc-timeline em { display: block; color: var(--mut); font-size: 14px; font-style: normal; }
.hc .hc-cta { display: flex; align-items: center; justify-content: space-between; gap: 20px; flex-wrap: wrap; margin-top: 32px; padding: 26px 30px; border-radius: 14px; background: var(--deep); color: #fff; }
.hc .hc-cta h3 { margin-bottom: 4px; font-size: 21px; font-weight: 700; color: #fff; }
.hc .hc-cta p { max-width: 560px; color: #e6d3ee; }
.hc .hc-cta p a { color: #fff; text-decoration: underline; }

/* Learning pathway */
.hc .hc-path { --b: #31577a; min-width: 0; }
.hc .path-stats { margin-bottom: 14px; color: var(--mut); font-size: 14px; }
.hc .path-step { position: relative; padding: 0 0 14px 38px; }
.hc .path-step::before { content: ""; position: absolute; left: 13px; top: 28px; bottom: 0; border-left: 2px solid var(--tint-2); }
.hc .path-step:last-child { padding-bottom: 0; }
.hc .path-step:last-child::before { display: none; }
.hc .path-dot { position: absolute; left: 0; top: 0; display: flex; align-items: center; justify-content: center; width: 28px; height: 28px; border: 2px solid var(--b); border-radius: 50%; background: #fff; color: var(--b); font-size: 13px; font-weight: 700; }
.hc .path-box { padding: 12px 16px; border: 1px solid var(--blue-line); border-radius: 10px; background: #fff; transition: border-color .15s, background .15s; }
.hc .path-box:hover { border-color: var(--b); background: var(--blue-back); }
.hc .path-topic { margin-bottom: 4px; color: var(--b); font-size: 13px; font-weight: 700; }
.hc .path-link { display: block; color: var(--ink); font-size: 15px; font-weight: 600; line-height: 1.35; }
.hc .path-link:hover { color: var(--brand); text-decoration: underline; }
.hc .path-sub { color: var(--mut); font-size: 13px; }
.hc .path-course + .path-course { margin-top: 8px; padding-top: 8px; border-top: 1px dashed var(--blue-line); }
.hc .path-note { margin-top: 4px; color: #475569; font-size: 13px; font-style: italic; }
.hc .path-label { margin-bottom: 2px; color: var(--mut); font-size: 12px; font-weight: 600; }
.hc .path-step.is-optional .path-box { border-style: dashed; }
.hc .path-step.is-optional .path-dot { border-style: dashed; font-size: 10px; }
.hc .path-step.is-final .path-dot { background: var(--b); color: #fff; }
.hc .path-step.is-final .path-box { border-color: var(--b); background: var(--blue-back); }

/* Responsive */
@media (max-width: 900px) {
    .hc .hc-hero { grid-template-columns: minmax(0, 1fr); gap: 24px; }
    .hc .hero-facts { grid-template-columns: repeat(2, minmax(0, 1fr)); border-left: 0; padding: 18px 0 0; border-top: 1px solid rgba(255,255,255,.2); }
    .hc .hc-split, .hc .hc-split-even, .hc .hc-steps { grid-template-columns: minmax(0, 1fr); }
    .hc .hc-side { position: static; }
}
@media (max-width: 720px) {
    .hc .hc-hero { padding: 28px 20px; }
    .hc .hc-hero h1 { font-size: 28px; }
    .hc .hc-section { margin-top: 44px; }
    .hc .hc-cta { padding: 22px 20px; }
}
@media (prefers-reduced-motion: reduce) { .hc * { transition: none !important; } .hc { scroll-behavior: auto; } }
</style>