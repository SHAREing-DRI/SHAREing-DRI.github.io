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
  <div class="hero-text">
    <span class="hero-kicker">Call for applications</span>
    <h1>HPC Champions: Performance Analysis</h1>
    <p>Join the first cohort of dRTPs building expertise in performance analysis, with travel and accommodation funding to attend the VI-HPS workshop in Durham.</p>
    <div class="hero-actions">
      <a class="hc-btn hc-btn-light" href="[application link]">Applications will open soon</a>
      <a class="hc-btn hc-btn-ghost" href="#journey">See the learning journey</a>
    </div>
  </div>
  <ul class="hero-facts">
<li><strong>Apply by 23 November</strong><span>2026</span></li>
<li><strong>Your learning pathway</strong><span>Follow our curated route or build your own, with SHAREing support</span></li>
<li><strong>Funded workshop</strong><span>VI-HPS travel &amp; accommodation covered</span></li>
  </ul>
</header>

<p class="hc-deadline">⏰ <strong>Applications</strong> open Monday 2 November 2026 and <strong> close Monday 23 November 2026 at 23:59 (UK time).</strong> Successful applicants will be notified by Monday 14 December 2026.</p>

<!-- ================= ABOUT ================= -->
<section class="hc-section">
  <h2>About HPC Champions</h2>
  <p class="hc-lead">HPC Champions is a SHAREing initiative for digital Research Technical Professionals (dRTPs) who want to build their skills in <strong>performance analysis</strong> of research software on HPC systems. We provide a curated learning pathway that takes you from foundations to the <a href="https://www.vi-hps.org/" target="_blank" rel="noopener noreferrer">VI-HPS</a> workshop in Durham, and the SHAREing team will support you in shaping it into a personalised journey that fits your starting point. As a Champion, your travel and accommodation for the workshop are covered.</p>

  <div class="hc-grid hc-grid-4">
    <div class="hc-card"><div class="hc-icon">🧭</div><h3>A curated pathway</h3><p>A guided route from foundations to the workshop, so you arrive prepared and get the most from it.</p></div>
    <div class="hc-card"><div class="hc-icon">🗺️</div><h3>Made personal</h3><p>Mentoring from the SHAREing team to adapt the pathway to your experience, skipping what you know and adding what you need.</p></div>
    <div class="hc-card"><div class="hc-icon">🎟️</div><h3>Funded workshop</h3><p>Travel and accommodation covered for a hands-on, expert-led performance engineering workshop in Durham.</p></div>
    <div class="hc-card"><div class="hc-icon">🤝</div><h3>A peer community</h3><p>Connect with other dRTPs focused on performance, share your work and widen your view of the performance analysis landscape.</p></div>
  </div>
</section>

<!-- ================= JOURNEY ================= -->
<section class="hc-section" id="journey">
  <h2>The learning journey</h2>
  <p class="hc-lead">All material is free to follow and self-study, so join at the point that matches your experience. Completion is not formally assessed, but working through the steps will significantly increase the value you get from the VI-HPS workshop.</p>

  {%- assign catalogue = site.data["external-training"] %}
  {%- assign steps = page.champions_pathway %}
  {%- assign optional_count = steps | where: "kind", "optional" | size %}
  {%- assign step_count = steps.size | minus: optional_count %}
  {%- assign n = 0 %}

  <article class="hc-path">
    <div class="path-head">
      <div class="path-icon">🚀</div>
      <div>
        <h3 class="path-title">HPC Champions learning pathway</h3>
        <div class="path-audience">For dRTPs building skills in performance analysis</div>
      </div>
    </div>
    <p class="path-desc">A curated route from the command line to the VI-HPS workshop in Durham. Start wherever suits your experience.</p>
    <p class="path-stats">{{ step_count }} steps{% if optional_count > 0 %}, {{ optional_count }} optional{% endif %}</p>
        <!--
    <div class="path-actions">
      <a class="path-btn" href="{{ site.baseurl }}/training/external-training-menu">Open in the catalogue</a>
    </div>-->

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

  <div class="hc-callout">
    <strong>Build your own pathway.</strong> The route above is a suggestion. Everyone starts from a different place, so we encourage you to build a pathway that fits your experience, skipping what you already know and adding what you need. In the <a href="{{ site.baseurl }}/training/external-training-menu">External Training Catalogue</a> you can load this route, reorder it, add optional courses and download your own version. Mentoring sessions with the SHAREing team will be available to help you plan your pathway.
  </div>
</section>


<!-- ================= WORKSHOP ================= -->
<section class="hc-section">
  <h2>The VI-HPS workshop</h2>
  <p class="hc-lead">Three days of hands-on training with leading performance analysis tools, alongside an introduction to the <strong>performance engineering cycle</strong>, a systematic approach to analysing and improving application performance.</p>

  <div class="hc-grid hc-grid-3">
    <div class="hc-card hc-card-blue"><h3>MAQAO</h3><p>Code analysis and optimisation tooling.</p></div>
    <div class="hc-card hc-card-blue"><h3>Score-P, Scalasca &amp; Cube</h3><p>Instrumentation, measurement and analysis of parallel applications.</p></div>
    <div class="hc-card hc-card-blue"><h3>Vampir</h3><p>Visual exploration of performance traces.</p></div>
  </div>

  <div class="hc-callout">
    <strong>Bring your own code.</strong> The workshop ends with significant time to apply the tools to your own software. If you don't have a suitable code, we can supply some.
  </div>
</section>

<!-- ================= COHORT ================= -->
<section class="hc-section">
  <h2>What to expect from the cohort</h2>
  <p class="hc-lead">Alongside the learning journey, we are developing activities to support Champions through the year.</p>

  <div class="hc-grid hc-grid-3">
  <div class="hc-card"><div class="hc-icon">💻</div><h3>Online kickoff</h3><p>An overview of the learning journey and an introduction to the cohort.</p></div>
    <div class="hc-card hc-card-wide hc-card-accent"><div class="hc-icon">🗺️</div><h3>Support to build your own pathway</h3><p>Everyone starts from a different place. Mentoring sessions with the SHAREing team will be available to help you design a personalised learning pathway based on your starting point and goals.</p></div>
    <div class="hc-card"><div class="hc-icon">📐</div><h3>Assessment methodology session</h3><p>An introduction to SHAREing's <a href="{{ site.baseurl }}/assessment/">performance assessment</a> approach, ahead of the more tool-focused workshop.</p></div>
    <div class="hc-card"><div class="hc-icon">🧪</div><h3>Early testbed access</h3><p>Explore novel hardware and tools ahead of the workshop.</p></div>
    <div class="hc-card"><div class="hc-icon">🎤</div><h3>Cohort meet-ups</h3><p>Regular get-togethers through the year to showcase and discuss your work.</p></div>
    <div class="hc-card"><div class="hc-icon">🍻</div><h3>Workshop social</h3><p>An evening get-together in Durham during the workshop.</p></div>
  </div>
  <p class="hc-note"><em>Details will be confirmed to the cohort as plans are finalised.</em></p>
</section>

<!-- ================= WHO ================= -->
<section class="hc-section">
  <h2>Who should apply?</h2>
  <p class="hc-lead">You do not need to be an expert. The learning journey is designed to bring you up to speed.</p>

  <ul class="hc-checks">
    <li>You are a dRTP interested in performance analysis and optimisation of research software.</li>
    <li>You work with, or are preparing to work with, HPC systems.</li>
    <li>You can attend the VI-HPS workshop in Durham, 17-20 May 2027.</li>
    <li>You want to engage with, and contribute to, a cohort of peers.</li>
  </ul>
</section>

<!-- ================= HOW TO APPLY ================= -->
<section class="hc-section">
  <h2>How to apply</h2>

  <div class="hc-grid hc-grid-3">
    <div class="hc-card hc-card-num"><span class="num">1</span><h3>Apply</h3><p>Complete the application form by <strong>23 November</strong>.</p></div>
    <div class="hc-card hc-card-num"><span class="num">2</span><h3>Hear from us</h3><p>The SHAREing team reviews applications and notifies applicants by <strong>14 December</strong>.</p></div>
    <div class="hc-card hc-card-num"><span class="num">3</span><h3>Get started</h3><p>Join the online kickoff event and begin the learning journey.</p></div>
  </div>

  <div class="hc-cta">
    <div>
      <h3>Ready to become a Champion?</h3>
      <p>Applications close <strong>23 November</strong>.</p>
    </div>
    <a class="hc-btn hc-btn-light" href="[application link]">Applications will open soon</a>
  </div>
</section>

<!-- ================= SPREAD / CONTACT ================= -->
<section class="hc-section hc-two">
  <div>
    <h2>Help us spread the word</h2>
    <p>Know a colleague who would benefit? Please share this call through your networks!</p>
  </div>
  <div>
    <h2>Questions?</h2>
    <p>Get in touch via our <a href="{{ site.baseurl }}/contact/">Contact</a> page.</p>
  </div>
</section>

</div>

<style>
/* Scoped to .hc and sized in px, matching the External Training Catalogue
   (Minimal Mistakes scales the root font size). */
.hc {
    --brand: #940594; --brand-dark: #6f046f; --deep: #421456;
    --tint: #f7eef7; --tint-2: #efdcef;
    --ink: #243855; --mut: #636d7c; --line: #e5e7eb; --soft: #f3f4f6;
    --blue: #31577a; --blue-back: #f1f6fb; --blue-line: #b9cde3;
    font-size: 15px; line-height: 1.55; color: var(--ink);
    margin: 0 0 32px; text-align: left;
}
.hc, .hc * { box-sizing: border-box; }
.hc h1, .hc h2, .hc h3, .hc p, .hc ul, .hc ol, .hc li {
    margin: 0; padding: 0; border: 0; font-family: inherit; text-indent: 0; text-transform: none; letter-spacing: normal;
}
.hc ul, .hc ol { list-style: none; }
.hc p { font-size: 15px; line-height: 1.55; }
.hc a { color: var(--brand); text-decoration: none; }
.hc p a:hover { text-decoration: underline; }
.hc :focus-visible { outline: 2px solid var(--brand); outline-offset: 2px; }
.hc html { scroll-behavior: smooth; }

/* ---------- Hero ---------- */
.hc .hc-hero {
    display: flex; align-items: center; justify-content: space-between; gap: 32px; flex-wrap: wrap;
    margin: 24px 0 16px; padding: 40px 36px; border-radius: 14px;
    background: var(--deep); color: #fff;
    background-image: radial-gradient(circle at 90% 10%, rgba(148,5,148,.55), transparent 55%);
}
.hc .hero-text { flex: 1 1 440px; max-width: 700px; }
.hc .hero-kicker {
    display: inline-block; margin-bottom: 12px; padding: 4px 12px; border-radius: 14px;
    background: rgba(255,255,255,.14); color: #f1dff7; font-size: 12px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase;
}
.hc .hc-hero h1 { font-size: 34px; line-height: 1.15; font-weight: 700; color: #fff; margin-bottom: 12px; }
.hc .hc-hero p { color: #e6d3ee; font-size: 17px; line-height: 1.5; }
.hc .hero-actions { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 22px; }
.hc .hero-facts { display: flex; flex-direction: column; gap: 14px; min-width: 210px; }
.hc .hero-facts li { padding: 14px 18px; border: 1px solid rgba(255,255,255,.18); border-radius: 12px; background: rgba(255,255,255,.08); }
.hc .hero-facts strong { display: block; font-size: 22px; line-height: 1.2; font-weight: 700; color: #fff; }
.hc .hero-facts span { display: block; font-size: 14px; color: #d9c0e6; }

/* ---------- Buttons ---------- */
.hc .hc-btn {
    display: inline-flex; align-items: center; justify-content: center;
    height: 42px; padding: 0 20px; border: 1px solid transparent; border-radius: 8px;
    font-size: 15px; font-weight: 600; line-height: 1; white-space: nowrap; cursor: pointer;
    transition: background .15s, border-color .15s, color .15s;
}
.hc .hc-btn-light { background: #fff; color: var(--deep); }
.hc .hc-btn-light:hover { background: var(--tint-2); }
.hc .hc-btn-ghost { background: transparent; border-color: rgba(255,255,255,.45); color: #fff; }
.hc .hc-btn-ghost:hover { background: rgba(255,255,255,.12); border-color: #fff; }

.hc .hc-deadline {
    margin: 0 0 8px; padding: 12px 16px; border-left: 4px solid var(--brand); border-radius: 6px;
    background: var(--tint); color: var(--deep); font-size: 15px;
}

/* ---------- Sections ---------- */
.hc .hc-section { margin-top: 44px; }
.hc .hc-section h2 {
    display: block; margin-bottom: 14px; padding-bottom: 10px;
    border-bottom: 2px solid var(--tint-2);
    font-size: 24px; line-height: 1.25; font-weight: 700; color: var(--deep);
}
.hc .hc-lead { max-width: 1500px; margin-bottom: 14px; font-size: 16px; color: var(--ink); }
.hc .hc-section > p + p { margin-top: 10px; }
.hc .hc-note { margin-top: 18px; color: var(--mut); font-size: 14px; }

/* ---------- Cards ---------- */
.hc .hc-grid { display: grid; gap: 16px; margin-top: 22px; }
.hc .hc-grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
.hc .hc-grid-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }
.hc .hc-card {
    padding: 20px; border: 1px solid var(--line); border-radius: 12px; background: #fff;
    transition: border-color .15s, box-shadow .15s, transform .15s;
}
.hc .hc-card:hover { border-color: #d8b5dc; box-shadow: 0 6px 18px rgba(66,20,86,.08); transform: translateY(-2px); }
.hc .hc-icon {
    display: flex; align-items: center; justify-content: center;
    width: 42px; height: 42px; margin-bottom: 12px; border-radius: 10px; background: var(--tint); font-size: 21px;
}
.hc .hc-card h3 { margin-bottom: 6px; font-size: 17px; line-height: 1.3; font-weight: 700; color: var(--deep); }
.hc .hc-card p { color: var(--mut); font-size: 14px; }
.hc .hc-card-blue { border-color: var(--blue-line); background: var(--blue-back); }
.hc .hc-card-blue h3 { color: var(--blue); }
.hc .hc-card-blue:hover { border-color: var(--blue); box-shadow: 0 6px 18px rgba(49,87,122,.12); }
.hc .hc-card-num { position: relative; padding-top: 26px; }
.hc .hc-card-num .num {
    position: absolute; top: -16px; left: 18px; display: flex; align-items: center; justify-content: center;
    width: 32px; height: 32px; border-radius: 50%; background: var(--brand); color: #fff; font-size: 15px; font-weight: 700;
}


/* ---------- Callout / checks / CTA ---------- */
.hc .hc-callout {
    margin-top: 22px; padding: 16px 20px; border-left: 4px solid var(--blue); border-radius: 8px;
    background: var(--blue-back); color: var(--ink);
}
.hc .hc-callout strong { color: var(--blue); }
.hc .hc-checks { max-width: 820px; margin-left: auto; margin-right: auto;}
.hc .hc-checks li {
    position: relative; margin-bottom: 10px; padding: 12px 16px 12px 46px;
    border: 1px solid var(--line); border-radius: 10px; background: #fff;
   
}
.hc .hc-checks li::before {
    content: "✓"; position: absolute; left: 14px; top: 11px; display: flex; align-items: center; justify-content: center;
    width: 22px; height: 22px; border-radius: 50%; background: var(--brand); color: #fff; font-size: 13px; font-weight: 700;
}
.hc .hc-cta {
    display: flex; align-items: center; justify-content: space-between; gap: 20px; flex-wrap: wrap;
    margin-top: 28px; padding: 26px 30px; border-radius: 14px; background: var(--deep); color: #fff;
    background-image: radial-gradient(circle at 95% 0%, rgba(148,5,148,.55), transparent 55%);
}
.hc .hc-cta h3 { margin-bottom: 4px; font-size: 21px; line-height: 1.25; font-weight: 700; color: #fff; }
.hc .hc-cta p { color: #e6d3ee; }
.hc .hc-two { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 32px; }
.hc .hc-two h2 { font-size: 20px; }


.hc .step-card h3 a { color: inherit; }
.hc .step-card h3 a:hover { color: var(--brand); text-decoration: underline; }
.hc .step-provider { margin-top: 4px; color: var(--brand); font-size: 12px; font-weight: 600; }
.hc .step-links { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px; }
.hc .step-links a {
    padding: 4px 12px; border: 1px solid var(--blue-line); border-radius: 14px;
    background: var(--blue-back); color: var(--blue); font-size: 13px; font-weight: 600;
}
.hc .step-links a:hover { border-color: var(--blue); text-decoration: none; }

/* ---------- Learning pathway card (matches catalogue curated pathways) ---------- */
.hc .hc-path { --b-back: #f1f6fb; --b-line: #31577a; --b-dark: #31577a; --b-dark-hover: #24415c;
    display: flex; flex-direction: column; gap: 10px; margin: 22px auto 0; padding: 18px;
    border: none; border-radius: 12px; background:none ; max-width: 500px; }
.hc .path-head { display: flex; align-items: center; gap: 12px; }
.hc .path-icon { display: flex; flex: 0 0 40px; align-items: center; justify-content: center; width: 40px; height: 40px;
    border: 1px solid var(--b-dark); border-radius: 10px; background: #fff; font-size: 20px; }
.hc .path-title { font-size: 17px; line-height: 1.3; font-weight: 700; color: var(--b-line); }
.hc .path-audience { margin-top: 2px; color: var(--mut); font-size: 13px; }
.hc .path-desc { color: var(--ink); font-size: 14px; }
.hc .path-stats { color: var(--mut); font-size: 13px; }
.hc .path-actions { display: flex; flex-wrap: wrap; gap: 8px; }
.hc .path-btn { display: inline-flex; align-items: center; justify-content: center; height: 38px; padding: 0 14px;
    border: 1px solid var(--b-dark); border-radius: 8px; background: var(--b-dark); color: #fff;
    font-size: 14px; font-weight: 600; line-height: 1; text-decoration: none; transition: background .15s; }
.hc .path-btn:hover { background: var(--b-dark-hover); text-decoration: none; }

.hc .path-steps { max-width: 560px; margin: 8px auto 0; padding-top: 14px;; }
.hc .path-step { position: relative; padding: 0 0 14px 34px; }
.hc .path-step::before { content: ""; position: absolute; left: 11px; top: 26px; bottom: 0; border-left: 2px solid var(--tint-2); }
.hc .path-step:last-child { padding-bottom: 0; }
.hc .path-step:last-child::before { display: none; }
.hc .path-dot { position: absolute; left: 0; top: 0; display: flex; align-items: center; justify-content: center;
    width: 24px; height: 24px; border: 2px solid var(--b-dark); border-radius: 50%; background: #fff;
    color: var(--b-dark); font-size: 12px; font-weight: 700; }
.hc .path-box { padding: 10px 12px; border: 1px solid var(--b-line); border-radius: 8px; background: var(--b-back); }
.hc .path-topic { margin-bottom: 4px; color: var(--b-line); font-size: 12px; font-weight: 700; letter-spacing: .02em; }
.hc .path-link { display: block; color: var(--ink); font-size: 14px; font-weight: 600; line-height: 1.35; }
.hc .path-link:hover { color: var(--brand); text-decoration: underline; }
.hc .path-sub { color: var(--mut); font-size: 13px; }
.hc .path-course + .path-course { margin-top: 8px; padding-top: 8px; border-top: 1px dashed #b9cde3; }
.hc .path-note { margin-top: 4px; color: #475569; font-size: 13px; font-style: italic; }
.hc .path-label { margin-bottom: 2px; color: var(--mut); font-size: 12px; font-weight: 600; }

.hc .path-step.is-optional .path-box { border-style: dashed; background: #fff; }
.hc .path-step.is-optional .path-dot { border-style: dashed; font-size: 10px; }
.hc .path-step.is-final .path-dot { background: var(--b-dark); color: #fff; }
/* ---------- Responsive ---------- */
@media (max-width: 1000px) {
    .hc .hc-grid-4 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
@media (max-width: 720px) {
    .hc .hc-hero { padding: 26px 20px; }
    .hc .hc-hero h1 { font-size: 27px; }
    .hc .hero-facts { flex-direction: row; flex-wrap: wrap; min-width: 0; width: 100%; }
    .hc .hero-facts li { flex: 1 1 140px; }
    .hc .hc-grid-3, .hc .hc-grid-4, .hc .hc-two { grid-template-columns: minmax(0, 1fr); }
    .hc .hc-cta { padding: 22px 20px; }
}
@media (prefers-reduced-motion: reduce) { .hc * { transition: none !important; } }
</style>