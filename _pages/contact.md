---
layout: splash
permalink: /contact/
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
  background-image: url('/assets/images/group.jpg');
    background-position: 150% 20%; 
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


.contact-hero {
  display: flex;
  flex-direction: column;
  align-items: center;  
  text-align: center;    
  z-index: 1;
}


.contact-badge {
   justify-content: center;
  margin-bottom: 1.2rem;
  padding: 0.45rem 1.2rem;
  border-radius: 999px;
  background: rgba(104,36,109,0.12);
  color: #68246d;
  font-weight: 700;
  letter-spacing: 0.03em;
}


.contact-intro {
  max-width: 1100px;
  margin: 2rem auto 3rem;
  background: white;
  border-radius: 22px;
  padding: 2.5rem 3rem;
  box-shadow: 0 20px 50px rgba(0,0,0,0.08);
}

.contact-intro h4 {
  color: #68246d;
  margin-bottom: 1rem;
}

.contact-intro p {
  font-size: 1rem;
  line-height: 1.7;
}


.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
  gap: 1.8rem;
  max-width: 1400px;
  margin: 0 auto;
}


.contact-card {
  background: #FAF3FB;
  border-radius: 20px;
  padding: 1.8rem 1.9rem;
  border-top: 5px solid #68246d;
  box-shadow: 0 14px 35px rgba(0,0,0,0.08);
  cursor: pointer;
  transition: transform 0.35s ease, box-shadow 0.35s ease;
    display: block;
  text-decoration: none;
  color: inherit;
}

.contact-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 45px rgba(0,0,0,0.35);
}



.contact-card span {
  font-size: 0.75rem;
  font-weight: 800;
  letter-spacing: 0.08em;
  color: #68246d;
  display: block;
  margin-bottom: 0.6rem;
}

.contact-card h3 {
  font-size: 1.05rem;
  margin-bottom: 0.6rem;
  color: #2d0f2f;
}

.contact-card p {
  font-size: 0.9rem;
}

.contact-extra {
  margin-top: 0.8rem;
  opacity: 1;
}



.contact-extra a {
  color: #68246d;
  font-weight: 600;
  text-decoration: none;
  border-bottom: 1px solid rgba(104,36,109,0.35);
}

.contact-extra a:hover {
  color: #3f1242;
  border-bottom-color: #3f1242;
}


.contact-footer {
  max-width: 1100px;
  margin: 3rem auto 0;
  background: rgba(255,255,255,0.9);
  padding: 2.2rem 3rem;
  border-radius: 22px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.08);
}

.contact-footer p {
  font-size: 0.95rem;
  line-height: 1.7;
}

.section-wide {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
  gap: 1.8rem;
}

@media (max-width: 768px) {


  .parallax-hero {
    height: 35vh;
    background-attachment: scroll; /* FIX mobile issues */
      margin-bottom: 3rem;
  }
  
 

  .image-1 {
    background-position: center;
  }
  
     .contact-badge {
    display: inline-block;
    margin-top: 1rem;
    margin-bottom: 1.5rem;
  }

  .contact-hero h1 {
    font-size: 2rem;
  }

  .contact-hero p {
    font-size: 1rem;
    padding: 0 1rem;
  }


  .contact-hero br {
    display: none;
  }

  .contact-grid {
    grid-template-columns: 1fr;
    gap: 1.2rem;
  }


  .contact-card {
    padding: 1.4rem 1.4rem;
  }

  .contact-card h3 {
    font-size: 1.1rem;
  }

  .contact-card p {
    font-size: 0.95rem;
  }


  .contact-card:hover {
    transform: none;
    box-shadow: 0 14px 35px rgba(0,0,0,0.12);
  }


  .contact-intro {
    margin: 2rem 1rem;
    padding: 2rem 1.6rem;
  }
}

</style>


<section class="parallax-hero image-1">
</section>

<br>

<section class="contact-hero">
  <span class="contact-badge">Get in touch</span>

  <h1>Contact SHAREing</h1>
  <p>
    Whether you are exploring a performance assessment, have a specific question,
    or are interested in collaboration, we would be pleased to hear from you.
  </p>
</section>



<section class="section-wide">
  <div class="contact-grid">

   <a href="mailto:shareing@durham.ac.uk" class="contact-card">
  <span>EMAIL</span>
  <h3>General enquiries</h3>
  <p>Questions, discussions, and initial contact.</p>
  <div class="contact-extra">
    <p>
      <strong>Email:</strong><br>
      shareing@durham.ac.uk
    </p>
  </div>
</a>


<a href="https://www.linkedin.com/company/shareing/"
   target="_blank"
   rel="noopener"
   class="contact-card">

  <span>LINKEDIN</span>
  <h3>Professional updates</h3>
  <p>News, events, and announcements.</p>
  <div class="contact-extra">
    <p>SHAREing on LinkedIn</p>
  </div>
</a>


<a href="https://bsky.app/profile/shareing.bsky.social"
   target="_blank"
   rel="noopener"
   class="contact-card">

  <span>BLUESKY</span>
  <h3>Community engagement</h3>
  <p>Informal updates and discussion.</p>
  <div class="contact-extra">
    <p>@shareing.bsky.social</p>
  </div>
</a>




  </div>
  
</section>


<section class="contact-intro">
  <h4>Start a conversation</h4>
  <p>
    We work with organisations at different stages — from early exploration of
    software performance challenges to concrete decisions about scaling, hardware,
    or further development. An initial conversation is often the most effective
    way to understand whether a performance assessment would be valuable in your context.
  </p>
</section>





