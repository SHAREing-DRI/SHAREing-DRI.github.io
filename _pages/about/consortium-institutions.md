---
permalink: /about/consortium-institutions
title: "Institutions"
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




.institutions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}


.section-wide {
  max-width: 1800px;
  margin: 4rem auto;
  padding: 0 1.5rem;
}


.institution-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 2rem;
  box-shadow: 0 12px 35px rgba(0,0,0,0.08);
  border-top: 6px solid #68246d;
  display: flex;
  flex-direction: column;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}



.institution-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 22px 50px rgba(0,0,0,0.12);
}

.institution-card img {
  max-height: 80px;
  object-fit: contain;
  margin-bottom: 1.5rem;
}


.institution-card h3 {
  font-size: 1.2rem;
  color: #68246d;
  margin-bottom: 0.8rem;
}

.institution-card p {
  font-size: 0.6rem;
  color: #555;
  line-height: 1.5;
  flex-grow: 1;
}

.institution-card a {
  margin-top: 1.2rem;
  align-self: flex-start;
  padding: 0.5rem 1.4rem;
  background: #f6f1f7;
  border-radius: 999px;
  font-size: 0.85rem;
  text-decoration: none;
  color: #333;
  transition: background 0.2s ease;
}

.institution-card a:hover {
  background: #e9d9ec;
}


.institution-card a.text-link {
  padding: 0;               
  margin: 0;                
  background: none;         
  border-radius: 0;         
  text-decoration: underline; 
  color: #68246d;          
  font-weight: 500;
  transition: color 0.2s ease;
  font-size: 0.6rem;
}

.institution-card a.text-link:hover {
  color: #0e2841;          
  text-decoration: underline;
}



@media (min-width: 1600px) {
  .institutions-grid {
    gap: 1.6rem;
  }
}


.full-width {
  width: 100vw;
  margin-left: calc(50% - 50vw);
}


.lead-institution img {
  max-height: none;
  width: 100%;
  height: 320px;           
  object-fit: cover;
  border-radius: 14px;
  margin-bottom: 0rem;
  object-position: 50% 20%;
}



</style>


<section class="parallax-hero">
  <div class="parallax-overlay">
    <h1>       Consortium Institutions       </h1>
  </div>
</section>


<section class="section">
  <h2>Lead Institution</h2>

  <div class="institution-card lead-institution" style="max-width: 800px; margin: 2rem auto;">
    <img src="/assets/images/Durham.jpg" alt="Durham University">
    <h3>Durham University</h3>
    <p>
      SHAREing is hosted at Durham University, with office space shared
      with the Institute for Data Science (IDAS) and Advanced Research
      Computing (ARC).
    </p>
    <p style="font-size: 0.9rem; color: #666;">
      Institute for Data Science<br>
      Upper Montjoy Hub, Upper Mountjoy Campus<br>
      Stockton Rd, Durham DH1 3LE
    </p>
  </div>
</section>


<section class="section-wide">
  <h2>Consortium members</h2>

  <div class="institutions-grid">

    

    <div class="institution-card">
      <img src="/assets/logos/CoSeC-STFC.png" alt="CoSeC">
      <h3>CoSeC</h3>
      <p>
        The Computational Science Centre for Research Communities (CoSeC) enables and supports collaborative computational research communities that are funded across UKRI. It has a mission to deliver research software as an infrastructure in order to enable world-class UK Research and Innovation. The communities are designed using multiple structures, including Collaborative Computational Projects (CCPs) and High-End Computing (HEC) Consortia. The Centre is run by UKRI STFC Scientific Computing and is made up of a core Programme Office plus a large team of Research Technical Professionals organised into domain-specific technical teams. <br><br>

  <a href="https://www.cosec.ac.uk/" class="text-link" target="_blank" rel="noopener">
    STFC Scientific Computing
  </a>
   is an international centre of excellence for advanced computing expertise and digital research infrastructure. The department provides the vital skills and tools required for modern research and innovation through our depth of expertise and knowledge, combined with our global network of partners and internationally renowned facilities.
      </p>
      <a href="https://www.cosec.ac.uk/">Visit CoSeC</a>
    </div>

    <div class="institution-card">
      <img src="/assets/logos/DurhamUniversity.png" alt="Durham University">
      <h3>Durham University</h3>
      <p>
        Durham University is a collegiate public research university in Durham, England, founded by an Act of Parliament in 1832 and incorporated by royal charter in 1837. While being the third-oldest university in England, the Department of Computer Science is one of Durham’s newest academic departments, having split from the School of Engineering and Computer Science in 2017. It currently hosts research groups in computer vision, AI, high-performance and scientific computing, digital humanities, computer science education, and networks. Durham houses multiple supercomputers, most notably the supercomputer serving the eight most research-intensive universities in the North of England, and the DiRAC tier-1 machine <br><br>

        Involved divisions in Durham are the Institute for Data Science (lead) and the Department of Computer Science, the directorate for Advanced Reserach Computing (ARC) and the Department of Physics’ Institute for Computational Cosmology.
      </p>
      <a href="https://www.durham.ac.uk/research/institutes-and-centres/data-science">
        Visit Durham
      </a>
    </div>
    
    
     	<div class="institution-card">
      <img src="/assets/logos/QMUL-no-background.png" alt="CoSeC">
      <h3>Queen Mary University of London</h3>
      <p> 
        Queen Mary University of London (QMUL) is an established university in London’s vibrant East End committed to high-quality research. High-Performace Computing underpins the activity of two Research Centres at QMUL: The Centre for Geometry, Analysis and Gravitation in the School of Mathematical Sciences, and the Centre for Fundamental Physics in the School of Physical and Chemical Sciences. Queen Mary University of London hosts and runs Apocrita, a heterogeneous HPC cluster comprising around 350 nodes and 12,500 compute cores.
      </p>
      <a href="https://www.qmul.ac.uk/">Visit Queen Mary London</a>
    </div>
    
    
    
      <div class="institution-card">
      <img src="/assets/logos/SwanseaUniversity.svg" alt="CoSeC">
      <h3>Swansea University</h3> 
      <p>
        Swansea University is a research-intensive university in Swansea, Wales, founded by royal charter in 1920 as a constituent college of the University of Wales, and becoming independent in 2007. The Swansea Academy of Advanced Computing (SA2C), founded in 2017, bridges Digital Services and the academic Faculties to deliver high-performance computing services to researchers across Wales. This has included hosting the Swansea hub of the Supercomputing Wales facility, and hosting the AccelerateAI facility.
      </p>
      <a href="https://www.swansea.ac.uk/">Visit Swansea</a>
    </div>
    
    
          <div class="institution-card">
      <img src="/assets/logos/UoM1.png" alt="CoSeC">
      <h3>The University of Manchester</h3>
      <p>
        The University of Manchester is a public research university located in Manchester, UK and its roots trace back to 1824. As a research-intensive institution, it is a member of the Russell Group, the N8 Research Partnership, and the US-based Universities Research Association. Recognised as one of the UK’s red brick universities, it has a long-standing tradition of academic excellence, innovation and research. The School of Engineering at the University of Manchester is a centre of excellence in innovation, research, and interdisciplinary collaboration. Through the Modelling and Simulation Centre (MaSC), the School harnesses advanced computational techniques to tackle complex engineering challenges.
      </p>
      <a href="https://www.manchester.ac.uk/">Visit Manchester</a>
    </div>
    
    
      <div class="institution-card">
      <img src="/assets/logos/sheffield.jpg" alt="CoSeC">
      <h3>Sheffield University</h3>
      <p>
        
      </p>
      <a href="https://sheffield.ac.uk/">Visit Sheffield</a>
    </div>
    
    
  <div class="institution-card">
      <img src="/assets/logos/Cardiff-Logo.png" alt="Cardiff University">
      <h3>Cardiff University</h3>
      <p>
      
      </p>
      <a href="https://www.cardiff.ac.uk/">Visit Cardiff</a>
    </div>
    
    
    

  </div>
</section>




