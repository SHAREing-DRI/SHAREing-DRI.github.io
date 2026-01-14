---
layout: splash
title: "About SHAREing"
permalink: /about-overview/
classes: wide

---
<style>
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
  box-shadow: 0 35px 55px rgba(0,0,0,0.3);
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


@media (max-width: 1200px) {
  .about-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 800px) {
  .about-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 500px) {
  .about-grid {
    grid-template-columns: 1fr;
    padding: 0 1.25rem; 
    gap: 1.5rem;
  }
}
</style>

<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1> About SHAREing</h1>
  </div>
</section>

<section>
  <h2>About SHAREing</h2>
  <p>
    SHAREing is a UK-wide initiative focused on performance analysis, optimisation,
    and sustainable computing practices across research institutions.
  </p>
</section>

<section class="about-grid">

  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Vision">
    <h3>Vision and Approach</h3>
    <p>Learn about SHAREing’s mission and long-term strategy</p>
    <a href="/about/vision-shareing" class="about-button">Explore</a>
  </div>

  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Consortium Partners">
    <h3>Institutions</h3>
    <p>All the partner institutions involved in SHAREing through their co-leads (CoL)</p>
    <a href="/about/consortium-institutions" class="about-button">View</a>
  </div>

  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Core Team">
    <h3>Core Team</h3>
    <p>Meet the people behind SHAREing</p>
    <a href="/about-overview/team-consortium" class="about-button">Meet</a>
  </div>

</section>

<section class="about-grid">


  <div class="about-card">
    <img src="/assets/images/logo.png" alt="Organisation">
    <h3>Organisation</h3>
    <p>How SHAREing is structured and how to get involved</p>
    <a href="/about/organisation" class="about-button">Visit</a>
  </div>
  
  
    <div class="about-card">
    <img src="/assets/images/logo.png" alt="Organisation">
    <h3>Flexible funds</h3>
    <p>Please check our flexible funds guidance notes</p>
    <a href="/about/flexible-funds" class="about-button">Guidance</a>
  </div>
  
      <div class="about-card">
    <img src="/assets/images/logo.png" alt="Organisation">
    <h3>Advisory Board</h3>
    <p>Meet the members of our Advisory Board</p>
    <a href="/about/advisory-board" class="about-button">View</a>
  </div>
  

</section>





<section>
  <h2>Contact</h2>
  <p>
    For enquiries or collaboration, please contact the core team
    or your local partner institution.
  </p>
</section>


