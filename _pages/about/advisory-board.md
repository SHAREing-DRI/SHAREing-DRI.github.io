---
permalink: /about/advisory-board
title: "Advisory Board"
layout: splash
---

<style>



.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);

  height: 40vh;
  background-image: url('/assets/images/home-assessment.png');
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
  margin-top: 6rem;
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
}

.person-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 18px 40px rgba(0,0,0,0.12);
}

.person-card img {
  width: 200px;
  height: 200px;
  object-fit: cover;
  border-radius: 50%;
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
</style>


<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1>       Advisory Board       </h1>
  </div>
</section>


<section class="section-wide">
  <div class="people-grid">

    <div class="person-card">
      <img src="/assets/profilepics/generic.jpg" alt="Profile Picture">
      <h3>Advisory Member</h3>
      <div class="role">Job Title · Institution</div>
        <a href="">Read more</a>
    </div>



    <div class="person-card">
      <img src="/assets/profilepics/generic.jpg" alt="Profile Picture">
      <h3>Advisory Member</h3>
      <div class="role">Job Title · Institution</div>

   
        <a href="">Read more</a>
    </div>
    


    <div class="person-card">
      <img src="/assets/profilepics/generic.jpg" alt="Profile Picture">
      <h3>Advisory Member</h3>
      <div class="role">Job Title · Institution</div>

   
         <a href="">Read more</a>
    </div>
    
    
      </div>  
</section>

