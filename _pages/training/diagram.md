---
permalink: /training/diagram2
---


<div class="roadmap">

  <!-- STEP 1 -->
  <div class="step">
    <div class="roadmap-card workshop">
      <div class="card-badge workshop">Upcoming Workshop</div>
      <h3>🖥️ Intro to Hamilton</h3>
      <a href="/events/fortran-workshop" class="card-button workshop">Register</a>
    </div>
  </div>

  <div class="connector"></div>

  <!-- STEP 2 -->
  <div class="step">
    <div class="roadmap-card material">
      <div class="card-badge material">Existing Material</div>
      <h3>📚 Foundations of HPC</h3>
      <a href="/training/foundations-hpc" class="card-button material">View Material</a>
    </div>
  </div>

  <div class="connector"></div>

  <!-- STEP 3 -->
  <div class="step">
    <div class="roadmap-card progress">
      <div class="card-badge progress">In Development</div>
      <h3>📊 Monitoring</h3>
      <span class="card-button disabled">Coming Soon</span>
    </div>
  </div>

  <div class="connector"></div>

  <!-- BRANCH 1 -->
  <div class="step branch">

    <div class="roadmap-card progress">
      <div class="card-badge progress">In Development</div>
      <h3>💻 C++</h3>
      <span class="card-button disabled">Coming Soon</span>
    </div>

    <div class="roadmap-card external">
      <div class="card-badge external">External material</div>
      <h3>🧮 Fortran</h3>
       <a href="/events/fortran-workshop" class="card-button">Check this course</a>
    </div>

  </div>

  <div class="connector"></div>

  <!-- BRANCH 2 -->
  <div class="step branch">

    <div class="roadmap-card workshop">
      <div class="card-badge workshop">Upcoming Workshop</div>
      <h3>🚀 CUDA</h3>
      <a href="/events/fortran-workshop" class="card-button">Register</a>
    </div>

    <div class="roadmap-card workshop">
      <div class="card-badge workshop">Upcoming Workshop</div>
      <h3>⚡ OpenMP</h3>
      <a href="/events/fortran-workshop" class="card-button">Register</a>
    </div>

  </div>

</div>

<style>

/* =========================
   MAIN LAYOUT
========================= */

.roadmap {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 1rem;

  display: flex;
  flex-direction: column;
  align-items: center;
}

/* =========================
   STEPS
========================= */

.step {
  width: 100%;
  display: flex;
  justify-content: center;
}

.step.branch {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

/* =========================
   CONNECTOR (CLEAN + PROFESSIONAL)
========================= */

.connector {
  width: 2px;
  height: 20px;
  background: #1c2d43;
  margin: 1rem;
}

/* =========================
   CARDS
========================= */

.roadmap-card {
  background: #ffffff;

  border: 1px solid #e5e7eb;
  border-left: 5px solid #94a3b8;

  border-radius: 14px;

  padding: 1rem;

  min-height: 110px;
  width: 100%;

  display: flex;
  flex-direction: column;
  justify-content: center;

  text-align: center;

  box-shadow: 0 1px 2px rgba(0,0,0,0.04);

  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.roadmap-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.08);
}

/* =========================
   TYPOGRAPHY
========================= */

.roadmap-card h3 {
  font-size: 1rem;
  margin: 0.25rem 0 0.75rem;
  font-weight: 600;
  color: #0f172a;
}

/* =========================
   BADGES
========================= */

.card-badge {
  display: inline-flex;
  align-self: center;

  font-size: 0.72rem;
  font-weight: 600;

  padding: 0.25rem 0.6rem;
  border-radius: 999px;

  margin-bottom: 0.75rem;
}

.card-badge.material {
  background: #DCFCE7;
  color: #166534;
}

.card-badge.workshop {
  background: #DBEAFE;
  color: #1D4ED8;
}

.card-badge.progress {
  background: #FED7AA;
  color: #C2410C;
}

.card-badge.external {
  background: #d6b6da;
  color: #67136d;
}

/* =========================
   STATUS ACCENTS
========================= */

.roadmap-card.material {
  border-left-color: #22c55e;
}

.roadmap-card.workshop {
  border-left-color: #2563eb;
}

.roadmap-card.progress {
  border-left-color: #f97316;
}

.roadmap-card.external {
  border-left-color: #67136d;
}


/* =========================
   BUTTONS
========================= */

.card-button {
  margin-top: auto;

  display: inline-flex;
  justify-content: center;

  padding: 0.5rem 1rem;
  border-radius: 999px;

  font-weight: 600;
  font-size: 0.85rem;

  text-decoration: none;

  background: #0f2a3a;
  color: white;

  transition: background 0.15s ease;
}
.card-button.disabled {
  background: #CBD5E1;
  color: #475569;
  cursor: default;
  pointer-events: none;
}
.card-button:not(.disabled):hover {
  opacity: 0.9;
}
.roadmap-card.material .card-button:hover {
  background: #22c55e;  transition: background 0.15s ease; color: white;
}
.roadmap-card.workshop .card-button:hover {
  background: #2563eb;  transition: background 0.15s ease; color: white;
}
.roadmap-card.progress .card-button:hover {
  background: #f97316;  transition: background 0.15s ease; color: white;
}

.roadmap-card.external .card-button:hover {
  background:  #67136d;  transition: background 0.15s ease; color: white;
}



/* =========================
   RESPONSIVE
========================= */

@media (max-width: 700px) {
  .step.branch {
    grid-template-columns: 1fr;
  }
}

</style>
