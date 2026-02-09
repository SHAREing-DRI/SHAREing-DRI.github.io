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
  background-image: url('/assets/images/ciuk2025.JPEG');
    background-position: 50% 50%; 
}

.parallax-overlay {
  background: rgba(104, 36, 109, 0.75);
  color: white;
  padding: 1rem 1rem;
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

.title h1{
 text-align: center;
  font-size: clamp(2.4rem, 5vw, 3rem);
  color: #68246d;
padding: 1.5rem 0.5rem;
}




.industry-hero {
  text-align: center;
  padding: 1rem 1.5rem 4rem;
  animation: fadeUp 0.8s ease-out both;
    margin-top: 0rem !important;
}

.industry-hero h1 {
  font-size: clamp(2.4rem, 5vw, 3rem);
  color: #68246d;
  margin-bottom: 1rem;
    margin-top: 1rem;
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
  text-align: center;
}

.industry-hero p {
  max-width: 900px;
  margin: 0 auto;
  font-size: 1.15rem;
}


.visual-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
  gap: 2rem;
  margin-top: 0rem !important;
}

.visual-card {
  position: relative;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 15px 40px rgba(0,0,0,0.12);
  transition: transform 0.4s ease;

  aspect-ratio: 4 / 3;
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

.flow {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.5rem;
  align-items: start; 
}


.flow-step.active {
  background: rgba(104, 36, 109, 0.08);
  border-top-color: #3f1242;
  box-shadow: 0 18px 45px rgba(104,36,109,0.25);
}


.flow-step.active p {
  color: #2d0f2f;
}

.flow-step.active span {
  color: #3f1242;
}



.flow-step {
  background: white;
  border-radius: 18px;
  padding: 1rem 1.25rem;
  border-top: 4px solid #68246d;
  box-shadow: 0 12px 30px rgba(0,0,0,0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  position: relative;
  margin-bottom:1rem;
}


.flow-step:hover {
  transform: translateY(-4px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
}

.flow-step span {
  font-size: 0.75rem;
  font-weight: 800;
  color: #68246d;
  letter-spacing: 0.08em;
}


.flow-step .extra-info {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease, padding 0.4s ease, opacity 0.4s ease;
  font-size: 0.8rem;
  margin-top: 0;
  color: #333;
  opacity: 0;
  padding: 0;
}


.flow-step.active .extra-info {
  max-height: 400px; 
  opacity: 1;
  padding: 0.5rem 0;
}


.flow-step span::after {
  content: ' ▼';
  font-size: 0.75rem;
  margin-left: 0.5rem;
  transition: transform 0.3s ease;
}

.flow-step.active span::after {
  transform: rotate(-180deg);
}


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
  padding: 2.5rem 3rem;
    margin-bottom:2rem;
  margin-top:2rem;
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
  margin-bottom: 0.8rem;
}


.visual-card-link {
  text-decoration: none;
  color: inherit;
  display: block;
}


.visual-card-link:hover .visual-overlay {
  background: linear-gradient(
    to top,
    rgba(63, 18, 66, 0.9),
    rgba(63, 18, 66, 0.4)
  );
}

.hero-callout {
  display: inline-block;
  max-width: 100%;
  margin: 1rem auto 1rem;
  padding: 0.6rem 1.2rem;

  border-radius: 999px;
  background: rgba(104,36,109,0.1);
  color: #68246d;

  font-weight: 600;
  font-size: 2rem;  text-align: center;

  box-sizing: border-box;
  white-space: normal;
}



@media(max-width: 800px){
  .boundary { grid-template-columns: 1fr; }
  
    .parallax-hero {
    height: 35vh;
    background-attachment: scroll;
      margin-bottom: 3rem;
  }
  
 
  .image-2
  .image-1 {
    background-position: center;
  }
  
    .hero-callout {
    font-size: 0.95rem;
    padding: 0.6rem 1rem;
  }
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


<br>


<section class="section-wide" style="text-align:center;">
  <div class="hero-callout">
    Software performance plays a key role in controlling costs and avoiding unnecessary investment
  </div>
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
  
  <p>
  The result is a clear, evidence-based understanding of what constrains performance today and what
  realistically could be improved in the future, including where improvements would lead to
  measurable cost savings or better return on investment.
</p>

</section>


<br> 


<section class="parallax-hero image-2">

</section>

<section class="title">
  <h1>How it works</h1>
</section>

<section class="section-wide">

  <div class="flow">
  
  
<div class="flow-step">
  <span>STEP 01</span>
  <p>You select a 
  <br>
  relevant software component or workflow. </p>
  <div class="extra-info">
    <p>You identify the software application or code that matters most to your organisation. We work with you to understand its role, how it is currently used, and what performance concerns or constraints you are experiencing, ensuring the assessment focuses on what is most relevant to your business.</p>
  </div>
</div>

<div class="flow-step">
  <span>STEP 02</span>
  <p>We apply SHAREing’s performance assessment methodology.</p>
  <div class="extra-info">
    <p>We apply SHAREing’s structured performance assessment methodology to observe how the software behaves in practice. Rather than examining individual lines of code, we analyse overall resource usage, scalability, and execution behaviour under realistic conditions to build a clear, evidence-based picture of performance.</p>
  </div>
</div>

<div class="flow-step">
  <span>STEP 03</span>
  <p>We identify performance characteristics and bottlenecks.</p>
  <div class="extra-info">
    <p>From this analysis, we identify the key factors that limit performance, such as inefficient use of resources or poor scaling. Bottlenecks are described in terms of their practical impact on runtime, cost, or capacity, helping you understand where constraints arise and why they matter.</p>
  </div>
</div>

<div class="flow-step">
  <span>STEP 04</span>
  <p>You receive a 
  <br>clear report with findings and 
  <br>options.</p>
  <div class="extra-info">
    <p>You receive a clear report summarising current performance, key limitations, and realistic options for improvement. This may include high-level guidance on hardware platforms or tools, but we do not modify or optimise code — the goal is to support informed decision-making, not to perform performance engineering.</p>
  </div>
</div>



  </div>
</section>


<section class="section-wide longform">
  <p>
SHAREing’s performance assessment gives you a clear, independent view of how your software behaves today and what realistically could be improved tomorrow. By identifying performance limitations, bottlenecks, and suitable technology options, we help organisations reduce uncertainty before committing time and resources to major changes. If you are considering scaling, new hardware, or further development, getting in touch is a simple first step towards understanding your options and making confident, evidence-based decisions.
  </p>
</section>


<br> 


<section class="section-wide">

  <div class="visual-grid">

    <a href="/contact/" class="visual-card-link">
      <div class="visual-card">
        <img src="/assets/images/team.jpg" alt="Contact SHAREing">
        <div class="visual-overlay">Talk to us</div>
      </div>
    </a>

    <a href="/assessment/" class="visual-card-link">
      <div class="visual-card">
        <img src="/assets/images/rsecon25.jpg" alt="Performance assessment methodology">
        <div class="visual-overlay">Our performance assessment work</div>
      </div>
    </a>

    <a href="/events/" class="visual-card-link">
      <div class="visual-card">
        <img src="/assets/images/retreat-2-jan.JPEG" alt="SHAREing events">
        <div class="visual-overlay">Upcoming events</div>
      </div>
    </a>

  </div>
</section>


<script>
  const bg = document.querySelector('.parallax-bg');

  window.addEventListener('scroll', () => {
    const scrolled = window.scrollY;
    bg.style.transform = `translateY(${scrolled * 0.2}px)`;
  });
</script>

<script>
  const steps = document.querySelectorAll('.flow-step');

  steps.forEach(step => {
    step.addEventListener('click', () => {
      steps.forEach(s => {
        if (s !== step) s.classList.remove('active');
      });
      step.classList.toggle('active');
    });
  });
</script>


