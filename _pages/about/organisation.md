---
permalink: /about/organisation
title: "SHAREing Organisation"
layout: splash
---

<style>
.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);

  height: 40vh;
  background-image: url('/assets/images/sc-booth.jpg');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  display: flex;
  align-items: center;
  justify-content: center;
  background-position: 80% 40%; 
}


.parallax-overlay {
  background: linear-gradient(
    to top,
    rgba(104, 36, 109, 0.85),
    rgba(104, 36, 109, 0.45)
  );
  color: white;
  width: 100vw;
  height: 40vh;
  text-align: center;
  border-radius: 12px;
}


.parallax-overlay h1 {
  font-size: 2.8rem;
  margin-top: 8rem;
}

.parallax-overlay p {
  font-size: 1.3rem;
  margin-top: 1rem;
  text-align: justify;
}


.section {
  max-width: 1100px;
  margin: 4rem auto;
  padding: 0 1.5rem;
}

.section h2 {
  text-align: centre;
  font-size: 2.2rem;
  margin-bottom: 1rem;
}

.section h3 {
  font-size: 1.6rem;
  margin-top: 2.5rem;
}

.lead {
  text-align: centre;
  font-size: 1.1rem;
  max-width: 1400px;
  margin: 0 auto 2rem;
  color: #555;
}

.wp-grid {
 display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.6rem;           
  margin-top: 1rem;
}


.wp-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 1.4rem;
  box-shadow: 0 12px 35px rgba(0,0,0,0.08);
  border-top: 6px solid #68246d;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.wp-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 22px 50px rgba(0,0,0,0.12);
}

.wp-card h4 {
  color: #68246d;
  margin-bottom: 1.2rem;
  font-size: 0.8rem;
  text-align: center;
}

.wp-card a {
  display: block;
  padding: 0.7rem 1rem;
  margin-bottom: 0.6rem;
  background: #f6f1f7;
  border-radius: 10px;
  font-size: 0.6rem;
  text-decoration: none;
  color: #333;
  transition: background 0.2s ease, transform 0.2s ease;
}

.wp-card a:hover {
  background: #e9d9ec;
  transform: translateX(4px);
  color: #000;
}


.organigram-image {
  display: block;
  max-width: 600px;
  margin: 3rem auto;
}


.cta-wrapper {
  text-align: center;
  margin: 3rem 0;
}

.cta {
  display: inline-block;
  padding: 0.9rem 2.6rem;
  background: #0e2841;
  color: #ffffff !important;
  border-radius: 999px;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.2s ease, transform 0.2s ease;
}

.cta:hover {
  background: #68246d;
  transform: translateY(-2px);
}


@media (max-width: 1024px) {
  .wp-grid {
    grid-template-columns: repeat(2, 1fr);
    padding: 0 2rem;
  }
}

@media (max-width: 640px) {
  .wp-grid {
    grid-template-columns: 1fr;
    padding: 0 1.5rem;
  }
}


</style>


<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1>       SHAREing's Organisation       </h1>
  </div>
</section>


<section class="section">
  <h2>How SHAREing works</h2>
  <p class="lead">
    SHAREing is organised around a set of thematic Work Packages that provide a
  structured yet flexible framework for delivering the project’s objectives.
  Through community-driven working groups, strategic goals are translated into
  concrete activities, outputs, and services that directly support the research
  and technical professional communities.
  </p>

  <img src="/assets/cartoons/org-3.png"
       alt="SHAREing organisational structure"/>
</section>


<section class="section">
  <h2>Working Groups and Subgroups</h2>
  <p class="lead">
     Each Work Package brings together a set of focused subgroups that address specific
  thematic areas. These subgroups identify community needs, <strong> define and prioritise tasks </strong> , and coordinate activities that contribute directly to the overall aims
  of SHAREing.
  </p>

  <div class="wp-grid">
    <div class="wp-card">
      <h4>WP1 <br> Performance Assessment</h4>
      <a href="/workpackages/workpackage-1/">WP1.1 - Performance assessment</a>
      <a href="/workpackages/workpackage-1/">WP1.2 - Assessment methodology</a>
      <a href="/workpackages/workpackage-1/">WP1.3 - Testbeds</a>
    </div>

    <div class="wp-card">
      <h4>WP2 <br> Technical Training</h4>
      <a href="/workpackages/workpackage-2/">WP2.3 - Develop e-learning content</a>
      <a href="/workpackages/workpackage-2/">WP2.4 - Organise training events</a>
    </div>

    <div class="wp-card">
      <h4>WP3 <br> Professional Skills Training</h4>
      <a href="/workpackages/workpackage-3/">WP3.3 - Develop e-learning content</a>
      <a href="/workpackages/workpackage-3/">WP3.4 - Organise training events</a>
    </div>
  </div>
<br>
  <p>
     Working groups are open to the wider community. Regular subgroup webinars are
  announced and published on the SHAREing website, providing an open space to share expertise, and propose new tasks aligned with the project’s direction.
  </p>

  <div class="cta-wrapper">
    <a href="/events/" class="cta">Join the monthly webinars</a>
  </div>
</section>


<section class="section">
  <h2>Consortium approvals</h2>
  <p>
     Tasks that receive consortium approval are formally published and made available
  for funding through the relevant Work Package pages.
  </p>

     <div class="cta-wrapper">
    <a href="/task-map/" class="cta">Check out current Open Tasks</a>
  </div>

</section>


<section class="section">
  <h2>Open Tasks and Aplications</h2>

  <p>
  Once approved and published, <strong> digital Research Technical Professionals (dRTPs) from consortium institutions </strong> may apply to carry out these tasks.
  
  
  
  <div class="cta-wrapper">
    <a href="/about/institutions" class="cta">
      Consortium member institutions
    </a>
  </div>
  
  
These tasks typically run for one to three months and may be funded for up to 100% full-time equivalent (FTE). In practice, many proposals span three months at a reduced workload, allowing teams to balance the task alongside other. Successful applications will include:
  </p>

  <ul>
    <li>an estimate of the anticipated costs,</li>
    <li>a clearly defined timeframe,</li>
    <li>a justification demonstrating the feasibility of the proposed work, and</li>
    <li>a precise description of the expected deliverables.</li>
  </ul>
  <p>
    Following this review process, SHAREing may formally commission the task by
    notifying the proposing team to proceed.
  </p>
  
  </section>
  <section class="section">
  <h2>Tasks Wrap-up</h2>

 
  <p>
    Once commissioned, dRTP teams carry out the agreed work and contribute directly
    to SHAREing’s overall objectives. 
    <br>
    <br>
    Outputs may take various forms, including technical or strategic reports,
    training materials, the organisation of events or surveys, case studies, or
    services delivered to the wider community. Upon submission of the agreed deliverables —
    accompanied by updates to the SHAREing website — the administrative
    office initiates the payment process.
      <br>
    <br>
    The relevant working group is then asked
    to assess whether the addressed task has been sufficiently covered and should
    be removed from the active task list. In this way, completed work informs the
    continuous refinement and definition of future tasks.
  </p>


  
</section>

<section class="section">
  <h2>Propose your Own Tasks </h2>

  <p>
 dRTPs may also propose new tasks. Proposals are reviewed within the relevant Work
    Package and, if approved, become Open Tasks. Proposers have priority to lead the
    task, with detailed planning and costings completed at the formal bid stage.
  </p>
  
   <div class="cta-wrapper">
    <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=i9hQcmhLKUW-RNWaLYpvlBhRpzyeDrFBkd8HIFx_xpdUQUs0QUFRQkhDNU83T1JMUkFFSlJHWjNXMy4u" class="cta">Propose your Own Task</a>
  </div>
  
  </section>

