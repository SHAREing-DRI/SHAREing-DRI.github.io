---
layout: splash
title: "Performance Assessment"
permalink: /assessment/
classes: wide

---
<style>

.assessment-header {
  text-align: center;
  margin: 1.5rem 0 2rem 0;
}

.assessment-header h1 {
  font-size: 2.1rem;
  margin-bottom: 0.3rem;
}

.assessment-header p {
  color: #555;
  font-size: 1.1rem;
  max-width: 780px;
  margin: 0 auto;
}

.full-width-btn-container {
  max-width: 1100px;
  margin: 0 auto 1.5rem auto;
}

.full-width-btn {
  display: block;
  width: 100%;
  text-align: center;
  font-size: 1.2rem;
  font-weight: 600;
  padding: 1rem 1.4rem;
  border-radius: 8px;
  background: #CDA3CD;
  color: white !important;
  text-decoration: none;
  transition: background 0.25s ease, color 0.25s ease;
}

.full-width-btn:hover {
  background: #0E2841; !important;
  color: #ffffff !important;
}

.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);

  height: 50vh;
  background-image: url('/assets/images/sc-booth.jpg');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  display: flex;
  align-items: center;
  justify-content: center;
  background-position: 50% 180%; 
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

.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  margin: 3rem auto;
}

.about-card {
  background: #ffffff;
  padding: 2rem 1.5rem;
  border-top: 4px solid #68246d;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 10px 18px rgba(0,0,0,0.05);
  display:flex;
  flex-direction: column;
}

.about-card img {
  height: 140px;        
  width: auto;          
  object-fit: contain;  
  flex-shrink: 0;       
  margin-bottom: 1rem;
}
.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 2rem;
  margin: 3rem 0;
}

.about-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 10px 25px rgba(0,0,0,0.08);
  text-align: center;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.about-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.12);
}

.about-card img {
  height: 180px;
  margin-bottom: 1rem;
}

.about-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.6rem 1.4rem;
  background: #68246D;
  color: white !important;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: background 0.2s ease, transform 0.2s ease;
    margin-top: auto;
}

.about-button:hover {
  background: #4e1a53;
  transform: scale(1.05);
}


</style>

<div class="assessment-header">
  <h1>Performance Assessment</h1>
  <p>
    A core part of SHAREing's vision is performance analysis, with the aim of
    building a performance assessment service. This page hosts materials and
    resources on performance methodologies and tools for Research Technical
    Professionals (RTPs) to begin producing performance assessments.
</p>
</div>
<div class="full-width-btn-container">
  <a class="full-width-btn" href="/assessment/submission">
    📊 Submit your code for assessment here
  </a>
</div>

<section class="about-grid">

  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Guidebook">
    <h3>Performance assessment guidebook</h3>
    <p>A draft guidebook on how to begin a performance assessment</p>
    <a href="/performance-assessment/guidebook" class="about-button">Explore</a>
  </div>

  <div class="about-card">
    <img src="/assets/images/squarelogo-greytext-orangebody-greymoons.png" alt="Jupyter notebook">
    <h3>High-level assessment notebook</h3>
    <p>A Jupyter notebook to perform a high-level performance assessment</p>
    <a href="/performance-assessment/notebook" class="about-button">Learn more</a>
  </div>

  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Guidebook">
    <h3>Benchmark guidelines</h3>
    <p>A draft guidebook for designing and writing benchmarks</p>
    <a href="/tasks/005_benchmark-guidelines" class="about-button">View</a>
  </div>
</section>
