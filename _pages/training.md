---
layout: splash
title: "Training & Upskilling"
permalink: /training/
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
  border-top: 4px solid #68246d;
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
  <h1>Training & Upskilling</h1>
  <p>
    A core part of SHAREing's vision is the creation of training materials and upskilling events targeted to Research Technical Professionals (RTPs).
</p>
</div>


<section class="about-grid">


  <div class="about-card">
    <img src="/assets/events-banner/correctness.png" alt="Guidebook">
    <h3>Correctness and Debugging Workshop</h3>
    <p>A report on our recent Correctness and Debugging Workshop Series </p>
    <a href="/events/202511-correctness-workshop" class="about-button">See the Report</a>
  </div>
  

  <div class="about-card">
    <img src="/assets/images/hpc_knowledge_graph.png" alt="Guidebook">
    <h3>HPC Concepts</h3>
    <p>Some basic revision material that’s worth revisiting before any assessment or benchmarking exercises. Made for newcomers without a background in HPC.</p>
    <a href="/training/hpc-foundations" class="about-button">HPC Concepts Material</a>
  </div>

</section>
