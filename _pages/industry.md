---
layout: splash
permalink: /industry/
title: ""
search: false
---

<style>

.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);

  height: 50vh;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  display: flex;
  align-items: center;
  justify-content: center;

}

.image-1 {
  background-image: url('/assets/images/performance-assessment-1.jpg');
    background-position: 50% 180%; 
}


.image-2 {
  background-image: url('/assets/images/ciuk25.HEIC');
    background-position: 50% 100%; 
}

.parallax-overlay {
  background: rgba(104, 36, 109, 0.75);
  color: white;
  padding: 3rem 4rem;
  text-align: center;
  border-radius: 12px;
}

.parallax-overlay h1 {
  font-size: 2.8rem;
}

.parallax-overlay p {
  font-size: 1.3rem;
  margin-top: 1rem;
}





/* ---------- HERO ---------- */
.industry-hero {
  text-align: center;
  padding: 5rem 1.5rem 4rem;
  animation: fadeUp 0.8s ease-out both;
    margin-top: 0rem !important;
}

.industry-hero h1 {
  font-size: clamp(2.4rem, 5vw, 3rem);
  color: #68246d;
  margin-bottom: 1rem;
}

.hero-badge {
  display: inline-block;
  padding: 0.4rem 1rem;
  border-radius: 999px;
  background: rgba(104,36,109,0.1);
  color: #68246d;
  font-weight: 700;
  font-size: 1.5rem;
  margin-bottom: 1.2rem;
  margin-top: 1rem !important;
}

.industry-hero p {
  max-width: 900px;
  margin: 0 auto;
  font-size: 1.15rem;
}

/* ---------- VISUAL GRID ---------- */
.visual-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.visual-card {
  position: relative;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 15px 40px rgba(0,0,0,0.12);
  transition: transform 0.4s ease;
}

.visual-card:hover {
  transform: translateY(-8px);
}

.visual-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.visual-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(104,36,109,0.85), transparent);
  padding: 1.5rem;
  color: white;
  display: flex;
  align-items: flex-end;
  font-weight: 700;
}

/* ---------- FLOW ---------- */
.flow {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px,1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.flow-step {
  background: white;
  border-radius: 18px;
  padding: 2rem;
  border-top: 4px solid #68246d;
  box-shadow: 0 12px 30px rgba(0,0,0,0.08);
  transition: transform 0.3s ease;
}

.flow-step:hover {
  transform: translateY(-6px);
}

.flow-step span {
  font-size: 0.75rem;
  font-weight: 800;
  color: #68246d;
  letter-spacing: 0.08em;
}

/* ---------- BOUNDARY ---------- */
.boundary {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  margin-top: 3rem;
}

.boundary div {
  background: #fff;
  border-radius: 18px;
  padding: 2rem;
  box-shadow: 0 10px 28px rgba(0,0,0,0.07);
}

.boundary h3 {
  color: #68246d;
}

.longform {
  max-width: 2000px;
  margin: 4rem auto;
  padding: 2.5rem 3rem;
  background: rgba(255,255,255,0.9);
  border-radius: 20px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.08);
}

.longform h4 {
  color: #68246d;
  margin-bottom: 1.5rem;
}

.longform p {
  font-size: 0.98rem;
  line-height: 1.75;
  margin-bottom: 1.2rem;
}


@media(max-width: 800px){
  .boundary { grid-template-columns: 1fr; }
}


</style>

<section class="industry-hero">
  <span class="hero-badge">For small & medium-sized enterprises</span>
  <h1>Performance assessment for industry</h1>
  <p>
    We help organisations understand how their existing software performs,
    where limitations arise, and what realistic options exist to move forward.
  </p>
</section>

<section class="parallax-hero image-1">
</section>

<section class="section-wide longform">
  <h4>Understanding software performance in practice</h4>

  <p>
    In many organisations, software performance is only examined when problems become visible:
    when runtimes increase, costs rise, or systems fail to scale as expected. By that point,
    decisions are often made under pressure and with limited insight into the true causes of
    inefficiency.
  </p>

  <p>
    SHAREing’s performance assessment service is designed to provide clarity before such issues
    become critical. Rather than focusing on individual lines of code, we look at the behaviour
    of software as a whole: how it uses computing resources, how different components interact,
    and where time and capacity are actually being spent during execution.
  </p>

  <p>
    This approach allows us to identify performance bottlenecks and limitations in a way that is
    independent of specific implementation choices. The result is a clear, evidence-based
    understanding of what constrains performance today and what realistically could be improved
    in the future.
  </p>

  <p>
    Our assessments are particularly valuable for organisations considering changes such as
    scaling workloads, moving to new hardware platforms, adopting accelerators, or investing in
    further software development. By providing a neutral assessment of current performance,
    SHAREing enables informed decision-making without committing organisations to specific
    technologies or optimisation strategies.
  </p>
</section>


<br> 


<section class="parallax-hero image-2">

</section>



<section class="section-wide">

  <div class="flow">
    <div class="flow-step">
      <span>STEP 01</span>
      <p>You select a relevant software component or workflow.</p>
    </div>

    <div class="flow-step">
      <span>STEP 02</span>
      <p>We apply SHAREing’s performance assessment methodology.</p>
    </div>

    <div class="flow-step">
      <span>STEP 03</span>
      <p>We identify performance characteristics and bottlenecks.</p>
    </div>

    <div class="flow-step">
      <span>STEP 04</span>
      <p>You receive a clear report with findings and options.</p>
    </div>
  </div>
</section>

<section class="section-wide">

  <div class="visual-grid">
    <div class="visual-card">
      <img src="/assets/images/hpc-ai.jpg" alt="">
      <div class="visual-overlay">Computational software & simulations</div>
    </div>

    <div class="visual-card">
      <img src="/assets/images/performance-assessment-1.jpg" alt="">
      <div class="visual-overlay">Performance behaviour & bottlenecks</div>
    </div>

    <div class="visual-card">
      <img src="/assets/images/hpc-foundations-knowledge-graph.png" alt="">
      <div class="visual-overlay">Scalability, cost & turnaround time</div>
    </div>
  </div>
</section>

<section class="section-wide">
  <h4>Clear scope</h4>

  <div class="boundary">
    <div>
      <h3>What we provide</h3>
      <p>
        Independent analysis, structured reporting, and high-level
        recommendations on hardware, platforms, and tools.
      </p>
    </div>

    <div>
      <h3>What we do not provide</h3>
      <p>
        We do not modify, refactor, or optimise code, and we do not carry
        out performance engineering.
      </p>
    </div>
  </div>
</section>

<div class="social-buttons">
  <a href="/contact/" class="btn btn--primary btn--large">
    Talk to us
  </a>
</div>


<script>
  const bg = document.querySelector('.parallax-bg');

  window.addEventListener('scroll', () => {
    const scrolled = window.scrollY;
    bg.style.transform = `translateY(${scrolled * 0.2}px)`;
  });
</script>


