---
permalink: /network/
title: "SHAREing's network"
layout: splash
---

<style>



.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);

  height: 40vh;
  background-image: url('/assets/images/team-sc.jpg');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  display: flex;
  align-items: center;
  justify-content: center;
  background-position: 60% 50%; 
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


.people-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.8rem;
  margin-top: 3rem;
}

.person-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 1.6rem;
  box-shadow: 0 10px 28px rgba(0,0,0,0.07);
  border-top: 4px solid #68246d;
  text-align: center;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  
   display: flex;
  flex-direction: column;
  height: 100%;
}

.person-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 18px 40px rgba(0,0,0,0.12);
}

.person-card img {
  width: 200px;
  height: 200px;
  object-fit: contain;   
  background: #f7f7f7;   
  border-radius: 50%;
  padding: 12px;        
  margin-bottom: 1rem;
}

.person-card h3 {
  font-size: 1.05rem;
  margin-bottom: 0.2rem;
  color: #68246d;
}

.person-card .role {
  font-size: 0.8rem;
  color: #666;
  margin-bottom: 0.6rem;
}

.person-card details {
  font-size: 0.75rem;
  color: #555;
  text-align: left;
  margin-top: 0.8rem;
}

.person-card summary {
  cursor: pointer;
  font-weight: 800;
  list-style: none;
   text-align: center;
    font-size: 1.05rem;
  color: #68246d;
}

.person-card a {
  cursor: pointer;
  font-weight: 800;
  list-style: none;
   text-align: center;
    font-size: 1.05rem;
  color: #68246d;
}

.person-card summary::-webkit-details-marker {
  display: none;
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
  font-size: 0.7rem;
  transition: background 0.2s ease, transform 0.2s ease;
    margin-top: auto;
}

.about-button:hover {
  background: #4e1a53;
  transform: scale(1.05);
}



</style>


<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1>       Network      </h1>
  </div>
</section>


<section class="section-wide">
  <div class="people-grid">

    <div class="person-card">
      <img src="https://www.cake.ac.uk/assets/images/cake-logo/CAKE_logo1.png" alt="CAKE">
      <h3>CAKE</h3>
      <div class="role">SHAREing relies on the DRI's Computational Abilities Knowledge Exchange (CAKE) project to coordinate and streamline its knowledge exchange and dissemination activities.</div>
      <a href="https://cake-dri.github.io/" class="about-button">Find out <br> more</a></div>

  

 <div class="person-card">
      <img src="/assets/images/logo.png" alt="supporters">
      <h3>SHAREing's supporters</h3>
      <div class="role">SHAREing relies on a wide range of supporters to deliver its work.</div>
     <a href="/network/supporters" class="about-button">Visit supporters</a></div>
    
    
   
    
    
      <div class="person-card">
      <img src="https://erlangenhub.ox.ac.uk/wp-content/uploads/2025/04/cropped-Erlangen-AI-Hub-logo1-RGB-1-scaled-1-2048x242.png" alt="Erlangen AI Hub">
      <h3>Erlangen AI Hub</h3>
      <div class="role">We cooperate with members of the Erlangen AI Hub to link SHAREing's work to foundational mathematics research.</div>
      <a href="https://erlangenhub.ox.ac.uk/" class="about-button">Visit Erlangen AI Hub</a></div>
    

      <div class="person-card">
      <img src="https://www.exageo.org/wp-content/uploads/2024/11/exageo-logo-main.png" alt="Erlangen AI Hub">
      <h3>ExaGeo</h3>
      <div class="role">We are proud to cooperate with members of the ExaGeo consortium.</div>
      <a href="https://www.exageo.org/" class="about-button">Visit <br> ExaGeo</a></div>
    
  </div>
</section>

