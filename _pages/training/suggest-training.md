---
layout: splash
title: "Suggest a Training Course"
permalink: /training/suggest-training
classes: wide
---

<style>

/* =========================================================
   INTRO
========================================================= */

.training-form-intro {
  margin-bottom: 2rem;
}

.training-form-intro h2 {
  margin: 0 0 .45rem;
  color: #2b2b2b;
  font-size: 1.5rem;
}

.training-form-intro > p {
  margin: 0;
  color: #64748b;
  line-height: 1.6;
  font-size: .95rem;
}

.training-form-intro > p a {
  color: #940594;
  font-weight: 600;
}

.intro-info {
  margin-top: 1.25rem;
  padding: 1rem 1.15rem;
  background: #f8f5f8;
  border-left: 3px solid #b906b9;
  border-radius: 6px;
}

.intro-info > strong {
  display: block;
  margin-bottom: .5rem;
  color: #4a354a;
  font-size: .9rem;
}

.intro-info ol {
  margin: 0 0 .9rem;
  padding-left: 1.3rem;
  color: #475569;
  font-size: .87rem;
  line-height: 1.55;
}

.intro-info li {
  padding-left: .2rem;
  margin-bottom: .2rem;
}

.catalogue-note {
  margin: .8rem 0 0;
  padding-top: .8rem;
  border-top: 1px solid #e5dce5;
  color: #64748b;
  font-size: .8rem;
  line-height: 1.5;
}

.catalogue-note strong {
  color: #5d3b5d;
}


/* =========================================================
   PAGE
========================================================= */

.training-form {
  max-width: 1200px;
  margin: 2rem auto 4rem;
}

.training-form-intro {
  margin-bottom: 2rem;
}

.training-form-intro h2 {
  margin: 0 0 .7rem;
  color: #2b2b2b;
  font-size: 1.55rem;
}

.training-form-intro p {
  color: #475569;
  line-height: 1.65;
  margin: .6rem 0;
}

/* =========================================================
   QUICK INFO
========================================================= */

.form-meta {
  display: flex;
  flex-wrap: wrap;
  gap: .6rem;
  margin: 1.2rem 0 2rem;
}

.form-meta-item {
  display: inline-flex;
  align-items: center;
  gap: .4rem;
  padding: .45rem .75rem;
  border-radius: 999px;
  background: #f7f1f7;
  color: #5d3b5d;
  font-size: .85rem;
}

.form-meta-item::before {
  content: "✓";
  font-weight: 700;
  color: #b906b9;
}

/* =========================================================
   PROGRESS
========================================================= */

.form-progress {
  margin-bottom: 2.2rem;
}

.form-progress-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: .5rem;
  font-size: .82rem;
  color: #64748b;
}

.form-progress-label {
  font-weight: 600;
  color: #475569;
}

.form-progress-bar {
  height: 6px;
  background: #eee;
  border-radius: 999px;
  overflow: hidden;
}

.form-progress-fill {
  height: 100%;
  width: 0;
  background: #b906b9;
  border-radius: 999px;
  transition: width .25s ease;
}

/* =========================================================
   FORM SECTIONS
========================================================= */

.form-section {
  margin: 0 0 1.5rem;
  padding: 1.5rem 1.6rem;
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0,0,0,.035);
}

.form-section-title {
  display: flex;
  align-items: center;
  gap: .65rem;
  margin: 0 0 1.35rem;
  padding-bottom: .8rem;
  border-bottom: 1px solid #eee;
  color: #2b2b2b;
  font-size: 1.15rem;
}

.section-number {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
  flex: 0 0 28px;
  border-radius: 50%;
  background: #f7e8f7;
  color: #940594;
  font-size: .82rem;
  font-weight: 700;
}

.section-description {
  margin: -.7rem 0 1.4rem;
  color: #64748b;
  font-size: .9rem;
  line-height: 1.5;
}

/* =========================================================
   FIELDS
========================================================= */

.training-form .field {
  margin-bottom: 1.35rem;
}

.training-form .field:last-child {
  margin-bottom: 0;
}

.training-form label {
  display: block;
  margin-bottom: .45rem;
  font-weight: 600;
  color: #334155;
}

.required {
  color: #b906b9;
}

.optional {
  color: #94a3b8;
  font-size: .8rem;
  font-weight: 400;
}

.training-form input,
.training-form select,
.training-form textarea {
  width: 100%;
  box-sizing: border-box;
  padding: .75rem .85rem;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  background: #fff;
  color: #1e293b;
  font-family: inherit;
  font-size: .98rem;
  transition:
    border-color .15s ease,
    box-shadow .15s ease,
    background .15s ease;
}

.training-form input::placeholder {
  color: #94a3b8;
}

.training-form input:hover,
.training-form select:hover {
  border-color: #a8b2c0;
}

.training-form input:focus,
.training-form select:focus,
.training-form textarea:focus {
  outline: none;
  border-color: #b906b9;
  box-shadow: 0 0 0 3px rgba(185, 6, 185, .11);
}

.training-form textarea {
  min-height: 110px;
  resize: vertical;
}

.help-text {
  display: block;
  margin-top: .4rem;
  color: #64748b;
  font-size: .84rem;
  line-height: 1.45;
}



/* =========================================================
   DATE OPTIONS
========================================================= */

.date-options {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: .15rem;
  border: 1px solid #cbd5e1;
  border-radius: 7px;
  padding: .35rem;
  background: #fff;
}

.date-option {
  display: flex !important;
  align-items: center;
  gap: .55rem;
  padding: .6rem .65rem;
  margin: 0 !important;
  border-radius: 5px;
  cursor: pointer;
  color: #334155;
  font-size: .9rem;
  font-weight: 400 !important;
  transition: background .12s ease;
}

.date-option:hover {
  background: #faf3fa;
}

/* Override the general .training-form input width:100% rule */
.date-option input[type="radio"] {
  width: 17px;
  height: 17px;
  flex: 0 0 17px;
  margin: 0;
  padding: 0;
  accent-color: #b906b9;
}

.date-option:has(input:checked) {
  background: #faf3fa;
}


/* =========================================================
   DATE FIELDS
========================================================= */

.date-fields {
  margin-top: 1rem;
}

.date-fields > label,
.date-range label,
.time-range label {
  display: block;
  margin-bottom: .4rem;
  color: #334155;
  font-size: .88rem;
  font-weight: 600;
}

.date-fields input[type="date"],
.date-fields input[type="time"] {
  width: 100%;
  box-sizing: border-box;
}


/* Two date fields side by side on larger screens */

.date-range {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1rem;
}

/* Optional time range, shown under the date(s) */

.time-range {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1rem;
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px dashed #e2e8f0;
}

.time-range-label {
  grid-column: 1 / -1;
  margin: 0 0 -.2rem;
  color: #64748b;
  font-size: .82rem;
}


/* Validation */

.field.invalid .date-options {
  border-color: #c0392b !important;
}

.field.invalid .date-fields input {
  border-color: #c0392b !important;
}


/* Mobile */

@media (max-width: 600px) {

  .date-options {
    grid-template-columns: 1fr;
  }

  .date-range,
  .time-range {
    grid-template-columns: 1fr;
  }

}


/* =========================================================
   VALIDATION
========================================================= */

.field-error {
  display: none;
  margin-top: .4rem;
  color: #b42318;
  font-size: .84rem;
  font-weight: 500;
}

.field.invalid input,
.field.invalid select,
.field.invalid .tag-picker {
  border-color: #c0392b !important;
}

.field.invalid .field-error {
  display: block;
}

.field.valid input,
.field.valid select {
  border-color: #4b8b57;
}

/* Don't show green validation before the user interacts. */
.field.valid:not(.touched) input,
.field.valid:not(.touched) select {
  border-color: #cbd5e1;
}

/* =========================================================
   ERROR SUMMARY
========================================================= */

#form-error-summary {
  display: none;
  margin-bottom: 1.5rem;
  padding: 1rem 1.2rem;
  background: #fff4f2;
  border: 1px solid #f2c7c2;
  border-left: 4px solid #c0392b;
  border-radius: 7px;
  color: #7a2118;
}

#form-error-summary.show {
  display: block;
}

#form-error-summary strong {
  display: block;
  margin-bottom: .45rem;
}

#form-error-summary ul {
  margin: 0;
  padding-left: 1.2rem;
}

/* =========================================================
   TOPIC PICKER
========================================================= */

.tag-picker {
  border: 1px solid #cbd5e1;
  border-radius: 7px;
  overflow: hidden;
  background: #fff;
  transition: border-color .15s ease, box-shadow .15s ease;
}

.tag-picker:focus-within {
  border-color: #b906b9;
  box-shadow: 0 0 0 3px rgba(185, 6, 185, .11);
}

.tag-search-wrapper {
  position: relative;
  border-bottom: 1px solid #e5e7eb;
}

.tag-search-icon {
  position: absolute;
  left: .85rem;
  top: 50%;
  transform: translateY(-50%);
  pointer-events: none;
  color: #94a3b8;
}

.tag-search {
  border: none !important;
  border-radius: 0 !important;
  padding-left: 2.35rem !important;
  box-shadow: none !important;
}

.tag-groups {
  max-height: 280px;
  overflow-y: auto;
  padding: .55rem;
}

.tag-group {
  padding: .3rem .25rem .65rem;
}

.tag-group.hidden {
  display: none;
}

.tag-group-label {
  padding: .45rem .4rem .3rem;
  color: #64748b;
  font-size: .74rem;
  font-weight: 700;
  letter-spacing: .04em;
  text-transform: uppercase;
}

.tag-options {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: .15rem;
}

.tag-option {
  display: flex !important;
  align-items: center;
  gap: .55rem;
  padding: .48rem .55rem;
  margin: 0 !important;
  border-radius: 5px;
  cursor: pointer;
  color: #334155;
  font-size: .9rem;
  font-weight: 400 !important;
  transition: background .12s ease;
}

.tag-option:hover {
  background: #faf3fa;
}

.tag-option input[type="radio"] {
  width: 17px;
  height: 17px;
  flex: 0 0 17px;
  margin: 0;
  accent-color: #b906b9;
}

.tag-empty-state {
  padding: 1.4rem 1rem;
  color: #64748b;
  font-size: .9rem;
  text-align: center;
}

/* =========================================================
   SELECTED TOPICS
========================================================= */

.selected-tags {
  display: flex;
  flex-wrap: wrap;
  gap: .4rem;
  margin-top: .75rem;
}

.tag-chip {
  display: inline-flex;
  align-items: center;
  gap: .35rem;
  padding: .32rem .4rem .32rem .7rem;
  border-radius: 999px;
  background: #b906b9;
  color: #fff;
  font-size: .82rem;
}

.tag-chip button {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 19px;
  height: 19px;
  padding: 0;
  border: none;
  border-radius: 50%;
  background: rgba(255,255,255,.22);
  color: #fff;
  cursor: pointer;
  font-size: .9rem;
  line-height: 1;
}

.tag-chip button:hover {
  background: rgba(255,255,255,.38);
}

.tags-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  margin-top: .55rem;
}

.tags-count {
  color: #64748b;
  font-size: .82rem;
}

.clear-tags {
  display: none;
  padding: 0;
  border: none;
  background: none;
  color: #940594;
  cursor: pointer;
  font-size: .82rem;
}

.clear-tags:hover {
  text-decoration: underline;
}

.clear-tags.show {
  display: inline;
}

/* =========================================================
   AUTOSAVE
========================================================= */

.draft-status {
  display: flex;
  align-items: center;
  gap: .4rem;
  margin-top: 1rem;
  color: #64748b;
  font-size: .82rem;
}

.draft-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #94a3b8;
}

.draft-status.saved .draft-dot {
  background: #4b8b57;
}

.draft-status.saving .draft-dot {
  background: #d9a441;
}

/* =========================================================
   GITHUB HAND-OFF
========================================================= */

.github-note {
  display: flex;
  gap: .9rem;
  margin: 1.5rem 0;
  padding: 1rem 1.1rem;
  background: #f8fafc;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
}

.github-note-icon {
  flex: 0 0 auto;
  font-size: 1.25rem;
}

.github-note strong {
  display: block;
  margin-bottom: .25rem;
  color: #334155;
}

.github-note p {
  margin: 0;
  color: #64748b;
  font-size: .88rem;
  line-height: 1.5;
}

/* =========================================================
   SUBMIT
========================================================= */

.submit-area {
  margin-top: 1.5rem;
}

.training-submit {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: .55rem;
  min-height: 48px;
  padding: .8rem 1.45rem;
  border: none;
  border-radius: 6px;
  background: #b906b9;
  color: #fff;
  font-family: inherit;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition:
    background .15s ease,
    transform .1s ease,
    box-shadow .15s ease;
}

.training-submit:hover {
  background: #940594;
  box-shadow: 0 3px 8px rgba(148,5,148,.2);
}

.training-submit:active {
  transform: translateY(1px);
}

.training-submit:disabled {
  background: #d9a8d9;
  cursor: not-allowed;
  box-shadow: none;
}

.submit-helper {
  margin-top: .55rem;
  color: #64748b;
  font-size: .8rem;
}

/* =========================================================
   SPINNER
========================================================= */

.spinner {
  display: none;
  width: 15px;
  height: 15px;
  border: 2px solid rgba(255,255,255,.4);
  border-top-color: #fff;
  border-radius: 50%;
  animation: spin .7s linear infinite;
}

.training-submit.loading .spinner {
  display: inline-block;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

/* =========================================================
   SUCCESS
========================================================= */

#success-banner {
  display: none;
  margin-top: 1.5rem;
  padding: 1.25rem 1.3rem;
  background: #effaf2;
  border: 1px solid #b8dfc0;
  border-left: 4px solid #2e7d32;
  border-radius: 8px;
  color: #1e5a2a;
}

#success-banner.show {
  display: block;
}

#success-banner strong {
  display: block;
  margin-bottom: .35rem;
}

#success-banner p {
  margin: 0;
  line-height: 1.5;
}

/* =========================================================
   RESPONSIVE
========================================================= */

@media (max-width: 600px) {

  .training-form {
    margin-top: 1rem;
  }

  .form-section {
    padding: 1.15rem;
    border-radius: 8px;
  }

  .tag-options {
    grid-template-columns: 1fr;
  }

  .form-meta {
    gap: .4rem;
  }

  .form-meta-item {
    font-size: .8rem;
  }

  .training-submit {
    width: 100%;
  }

  .submit-helper {
    text-align: center;
  }
}
</style>

<div class="training-form">

 <!-- =======================================================
     INTRO
======================================================== -->

<div class="training-form-intro">

  <h2>Know a useful training course?</h2>

  <p>
    Help us add it to the
    <a href="{{ '/training/external-training-test' | relative_url }}">
      SHAREing External Training Catalogue
    </a>.
    Just fill in the details below - it only takes a minute!
  </p>

  <div class="intro-info">
    <strong>What happens next?</strong>

    <ol>
      <li>Fill in the course details below.</li>
      <li>We'll create a pre-filled GitHub issue for you to review.</li>
      <li>The SHAREing team will review the suggestion and, if appropriate, add it to the catalogue.</li>
    </ol>

    <p class="catalogue-note">
SHAREing support has been used to curate, organise, and present publicly available training opportunities in a searchable format. The courses listed here are provided by third-party organisations and are not funded, delivered, or maintained by SHAREing unless explicitly stated. Course content, availability, schedules, and registration are the responsibility of the individual providers.
    </p>
  </div>

</div>




  <!-- =======================================================
       ERRORS
  ======================================================== -->

  <div id="form-error-summary" role="alert" aria-live="polite">

    <strong>Please check the following:</strong>

    <ul id="form-error-list"></ul>

  </div>


  <!-- =======================================================
       FORM
  ======================================================== -->

  <form id="training-suggestion-form" novalidate>


    <!-- COURSE DETAILS -->

    <section class="form-section">
      <div class="field" data-field="title">


  <label for="course-title">

    <h2 class="form-section-title">
  <span class="section-number">1</span>
  Course title <span class="required">*</span>
</h2>
  </label>

        <input
          type="text"
          id="course-title"
          name="title"
          autocomplete="off"
          placeholder="e.g. Introduction to CUDA C/C++"
          required
        >

        <span class="field-error">
          Please enter a course title.
        </span>

      </div>


      <div class="field" data-field="organisation">

<label for="course-title">
<h2 class="form-section-title">
  <span class="section-number">2</span>
  Organisation<span class="required">*</span>
</h2>
</label>

        <input
          type="text"
          id="organisation"
          name="organisation"
          autocomplete="organization"
          placeholder="e.g. NHR@FAU"
          required
        >

        <span class="help-text">
          The university, organisation or training provider running the course.
        </span>

        <span class="field-error">
          Please enter the organisation running the course.
        </span>

      </div>

    </section>


    <!-- FORMAT & TOPICS -->

    <section class="form-section">
     <div class="field" data-field="format">

<label for="course-title">
<h2 class="form-section-title">
  <span class="section-number">3</span>
  Format<span class="required">*</span>
</h2>
</label>

        <select id="format" name="format" required>

          <option value="">Select a format...</option>

          <option value="Online (self-service)">
            Online (self-service)
          </option>

          <option value="Scheduled (online)">
            Scheduled (online)
          </option>

          <option value="Scheduled (hybrid)">
            Scheduled (hybrid)
          </option>

          <option value="Scheduled (in-person)">
            Scheduled (in-person)
          </option>

          <option value="Other">
            Other
          </option>

        </select>

        <span class="field-error">
          Please choose a format.
        </span>

      </div>


      <div class="field" data-field="tags">

<label for="course-title">
<h2 class="form-section-title">
  <span class="section-number">4</span>
  Main Topic<span class="required">*</span>
</h2>
</label>

        <div class="help-text" style="margin-top:-.2rem;margin-bottom:.6rem;">
          Select a topic
        </div>


        <div
          class="tag-picker"
          role="group"
          aria-labelledby="tags-label"
        >

          <div class="tag-search-wrapper">

            <span class="tag-search-icon" aria-hidden="true">⌕</span>

            <input
              type="text"
              id="tags-search"
              class="tag-search"
              placeholder="Search topics..."
              autocomplete="off"
              aria-label="Search topics"
            >

          </div>


          <div class="tag-groups" id="tag-groups">

            {% for group in site.data["training-topics"] %}

              <div class="tag-group">

                <div class="tag-group-label">
                  {{ group[0] }}
                </div>

                <div class="tag-options">

                  {% for topic in group[1] %}

                    <label class="tag-option">

                      <input
                        type="radio"
                        name="tags"
                        value="{{ topic }}"
                      >

                      <span>{{ topic }}</span>

                    </label>

                  {% endfor %}

                </div>

              </div>

            {% endfor %}


            <div
              class="tag-empty-state"
              id="tag-empty-state"
              style="display:none;"
            >
              No topics match your search.
            </div>

          </div>

        </div>


        <div class="selected-tags" id="selected-tags"></div>


<div class="tags-footer">

  <span class="tags-count" id="tags-count" aria-live="polite">
    No topic selected
  </span>

  <button type="button" class="clear-tags" id="clear-tags">
    Clear
  </button>

</div>


        <span class="field-error">
         Please select a topic.
        </span>

      </div>

    </section>


    <!-- SCHEDULE -->

    <section class="form-section">



<div class="field" data-field="dates">

  <h2 class="form-section-title">
    <span class="section-number">5</span>
    Dates<span class="required">*</span>
  </h2>

  <div class="date-options">

    <label class="date-option">
      <input type="radio" name="date-type" value="self-paced">
      <span>Self-paced (always available)</span>
    </label>

    <label class="date-option">
      <input type="radio" name="date-type" value="one-day">
      <span>One day course</span>
    </label>

    <label class="date-option">
      <input type="radio" name="date-type" value="several-days">
      <span>Several days</span>
    </label>

    <label class="date-option">
      <input type="radio" name="date-type" value="tbd">
      <span>Date yet to be determined</span>
    </label>

  </div>

  <div
    class="date-fields"
    id="one-day-fields"
    style="display: none;"
  >
    <label for="course-date">Course date</label>

    <input
      type="date"
      id="course-date"
      name="course-date"
    >

    <div class="time-range">

      <div class="time-range-label">
        Time (optional)
      </div>

      <div>
        <label for="one-day-start-time">Start time</label>
        <input type="time" id="one-day-start-time" name="one-day-start-time">
      </div>

      <div>
        <label for="one-day-end-time">End time</label>
        <input type="time" id="one-day-end-time" name="one-day-end-time">
      </div>

    </div>

  </div>

  <div
    class="date-fields"
    id="several-days-fields"
    style="display: none;"
  >
    <div class="date-range">

      <div>
        <label for="start-date">Begin date</label>

        <input
          type="date"
          id="start-date"
          name="start-date"
        >
      </div>

      <div>
        <label for="end-date">Final date</label>

        <input
          type="date"
          id="end-date"
          name="end-date"
        >
      </div>

    </div>

    <div class="time-range">

      <div class="time-range-label">
        Time (optional, if the same each day)
      </div>

      <div>
        <label for="several-days-start-time">Start time</label>
        <input type="time" id="several-days-start-time" name="several-days-start-time">
      </div>

      <div>
        <label for="several-days-end-time">End time</label>
        <input type="time" id="several-days-end-time" name="several-days-end-time">
      </div>

    </div>

  </div>


  <span class="help-text">
    Choose the option that best describes when the training is available.
    Times are optional and only used for scheduled courses.
  </span>

  <span class="field-error">
    Please select a date option and provide the required date(s).
  </span>

</div>


      <div class="field" data-field="location">

<label for="course-title">
<h2 class="form-section-title">
  <span class="section-number">6</span>
  Location<span class="required">*</span>
</h2>
</label>


        <input
          type="text"
          id="location"
          name="location"
          placeholder="e.g. Online or Durham, UK"
          required
        >

        <span class="field-error">
          Please enter a location.
        </span>

      </div>

    </section>


    <!-- LINK -->

    <section class="form-section">



      <div class="field" data-field="url">

<label for="course-title">
<h2 class="form-section-title">
  <span class="section-number">6</span>
  Course URL<span class="required">*</span>
</h2>
</label>

        <input
          type="url"
          id="course-url"
          name="url"
          inputmode="url"
          placeholder="https://example.org/course"
          required
        >

        <span class="help-text">
          Please provide a public webpage with information about the course.
        </span>

        <span class="field-error">
          Please enter a valid URL starting with http:// or https://.
        </span>

      </div>

    </section>


    <!-- GITHUB EXPLANATION -->

    <div class="github-note">

      <div class="github-note-icon" aria-hidden="true">
        ↗
      </div>

      <div>

        <strong>What happens when you click the button?</strong>

        <p>
          Your information will be copied into a pre-filled GitHub issue.
          You can review everything there before clicking <strong>Create</strong>
        </p>

      </div>

    </div>


    <!-- SUBMIT -->

    <div class="submit-area">

      <button
        type="submit"
        class="training-submit"
        id="submit-button"
      >

        <span class="spinner" aria-hidden="true"></span>

        <span id="submit-button-label">
          Continue to GitHub →
        </span>

      </button>

      <div class="submit-helper">
        You can review and edit the suggestion on GitHub before submitting it.
      </div>

    </div>


    <!-- AUTOSAVE STATUS -->

    <div
      class="draft-status saved"
      id="draft-status"
      aria-live="polite"
    >

      <span class="draft-dot"></span>

      <span id="draft-status-text">
        Your draft is saved automatically
      </span>

    </div>

  </form>


  <!-- =======================================================
       SUCCESS
  ======================================================== -->

  <div id="success-banner">

    <strong>✓ Your GitHub submission is ready</strong>

    <p>
      A new GitHub tab has been opened with your suggestion.
      Review the information and click <strong>Create</strong> to finish
      submitting it.
    </p>

  </div>

</div>


<script>
(function () {

  const DRAFT_KEY = "shareing-training-suggestion-draft";

  const MONTH_NAMES = [
    "January", "February", "March", "April",
    "May", "June", "July", "August",
    "September", "October", "November", "December"
  ];

  const form =
    document.getElementById("training-suggestion-form");

  const submitButton =
    document.getElementById("submit-button");

  const submitLabel =
    document.getElementById("submit-button-label");

  const successBanner =
    document.getElementById("success-banner");

  const errorSummary =
    document.getElementById("form-error-summary");

  const errorList =
    document.getElementById("form-error-list");

  const progressFill =
    document.getElementById("progress-fill");

  const progressCount =
    document.getElementById("progress-count");

  const progressLabel =
    document.getElementById("progress-label");

  const draftStatus =
    document.getElementById("draft-status");

  const draftStatusText =
    document.getElementById("draft-status-text");


  /* =========================================================
     COURSE DETAILS
  ========================================================= */

  const titleInput =
    document.getElementById("course-title");

  const organisationInput =
    document.getElementById("organisation");

  const formatSelect =
    document.getElementById("format");


  /* =========================================================
     DATES
  ========================================================= */

  const dateTypeInputs = Array.from(
    document.querySelectorAll(
      'input[name="date-type"]'
    )
  );

  const oneDayFields =
    document.getElementById("one-day-fields");

  const severalDaysFields =
    document.getElementById("several-days-fields");

  const courseDateInput =
    document.getElementById("course-date");

  const startDateInput =
    document.getElementById("start-date");

  const endDateInput =
    document.getElementById("end-date");

  const oneDayStartTime =
    document.getElementById("one-day-start-time");

  const oneDayEndTime =
    document.getElementById("one-day-end-time");

  const severalDaysStartTime =
    document.getElementById("several-days-start-time");

  const severalDaysEndTime =
    document.getElementById("several-days-end-time");


  /* =========================================================
     LOCATION & URL
  ========================================================= */

  const locationInput =
    document.getElementById("location");

  const urlInput =
    document.getElementById("course-url");


  /* =========================================================
     TOPICS
  ========================================================= */

  const tagSearch =
    document.getElementById("tags-search");

  const tagEmptyState =
    document.getElementById("tag-empty-state");

  const tagInputs = Array.from(
    document.querySelectorAll(
      '.tag-option input[type="radio"]'
    )
  );

  const selectedTagsContainer =
    document.getElementById("selected-tags");

  const tagsCountLabel =
    document.getElementById("tags-count");

  const clearTagsButton =
    document.getElementById("clear-tags");

  /* =========================================================
     TAGS
  ========================================================= */

  function getSelectedTags() {

    return tagInputs
      .filter(cb => cb.checked)
      .map(cb => cb.value);

  }


  function renderSelectedTags() {

    const selected = getSelectedTags();

    selectedTagsContainer.innerHTML = "";

    selected.forEach(value => {

      const chip = document.createElement("span");
      chip.className = "tag-chip";

      const text = document.createElement("span");
      text.textContent = value;

      const removeButton =
        document.createElement("button");

      removeButton.type = "button";
      removeButton.textContent = "×";
      removeButton.setAttribute(
        "aria-label",
        `Remove ${value}`
      );

      removeButton.addEventListener("click", () => {

        const checkbox =
          tagInputs.find(cb => cb.value === value);

        if (checkbox) {
          checkbox.checked = false;
          renderSelectedTags();
          saveDraft();
          clearFieldError("tags");
          updateProgress();
        }

      });

      chip.appendChild(text);
      chip.appendChild(removeButton);

      selectedTagsContainer.appendChild(chip);

    });


    if (selected.length === 0) {
      tagsCountLabel.textContent = "No topic selected";
      clearTagsButton.classList.remove("show");
    } else {
      tagsCountLabel.textContent = "1 topic selected";
      clearTagsButton.classList.add("show");
    }

  }


  if (clearTagsButton) {

    clearTagsButton.addEventListener("click", () => {

      tagInputs.forEach(cb => {
        cb.checked = false;
      });

      renderSelectedTags();
      saveDraft();
      clearFieldError("tags");
      updateProgress();

    });

  }


  tagInputs.forEach(cb => {

    cb.addEventListener("change", () => {

      renderSelectedTags();
      saveDraft();
      updateProgress();

      if (getSelectedTags().length > 0) {
        clearFieldError("tags");
      }

    });

  });


  /* =========================================================
     TAG SEARCH
  ========================================================= */

  function filterTags() {

    const term =
      tagSearch.value.trim().toLowerCase();

    let anyVisible = false;

    document.querySelectorAll(".tag-group")
      .forEach(group => {

        let groupHasVisible = false;

        group.querySelectorAll(".tag-option")
          .forEach(option => {

            const text =
              option.querySelector("span")
                .textContent
                .toLowerCase();

            const matches =
              !term || text.includes(term);

            option.classList.toggle(
              "hidden",
              !matches
            );

            if (matches) {
              groupHasVisible = true;
              anyVisible = true;
            }

          });

        group.classList.toggle(
          "hidden",
          !groupHasVisible
        );

      });

    tagEmptyState.style.display =
      anyVisible ? "none" : "block";

  }


  tagSearch.addEventListener(
    "input",
    filterTags
  );


  /* =========================================================
     DATES
  ========================================================= */

  function getSelectedDateType() {

    const selected =
      dateTypeInputs.find(
        input => input.checked
      );

    return selected
      ? selected.value
      : "";

  }


  /* Parse a YYYY-MM-DD string (from <input type="date">)
     without timezone shifting. */

  function parseISODate(value) {

    if (!value) return null;

    const [y, m, d] = value.split("-").map(Number);

    if (!y || !m || !d) return null;

    return { year: y, month: m, day: d };

  }


  function formatFullDate(parts) {
    return `${parts.day} ${MONTH_NAMES[parts.month - 1]} ${parts.year}`;
  }


  function formatTimeSuffix(startTime, endTime) {

    if (startTime && endTime) {
      return ` ${startTime} - ${endTime}`;
    }

    return "";

  }


  function formatDateRange(startParts, endParts) {

    if (
      startParts.year === endParts.year &&
      startParts.month === endParts.month
    ) {

      return (
        `${startParts.day}-${endParts.day} ` +
        `${MONTH_NAMES[startParts.month - 1]} ${startParts.year}`
      );

    }

    if (startParts.year === endParts.year) {

      return (
        `${startParts.day} ${MONTH_NAMES[startParts.month - 1]} - ` +
        `${endParts.day} ${MONTH_NAMES[endParts.month - 1]} ${startParts.year}`
      );

    }

    return (
      `${formatFullDate(startParts)} - ${formatFullDate(endParts)}`
    );

  }


  function getDateValue() {

    const dateType =
      getSelectedDateType();

    if (dateType === "self-paced") {
      return "Self-paced (always available)";
    }

    if (dateType === "tbd") {
      return "Date yet to be determined";
    }

    if (dateType === "one-day") {

      const parts =
        parseISODate(courseDateInput.value);

      if (!parts) return "";

      return (
        formatFullDate(parts) +
        formatTimeSuffix(
          oneDayStartTime.value,
          oneDayEndTime.value
        )
      );

    }

    if (dateType === "several-days") {

      const startParts =
        parseISODate(startDateInput.value);

      const endParts =
        parseISODate(endDateInput.value);

      if (!startParts || !endParts) return "";

      return (
        formatDateRange(startParts, endParts) +
        formatTimeSuffix(
          severalDaysStartTime.value,
          severalDaysEndTime.value
        )
      );

    }

    return "";

  }


  function updateDateFields() {

    const selectedType =
      getSelectedDateType();


    /* Hide both date sections */

    oneDayFields.style.display = "none";
    severalDaysFields.style.display = "none";


    /* Show the relevant date section */

    if (selectedType === "one-day") {

      oneDayFields.style.display = "block";

    }

    if (selectedType === "several-days") {

      severalDaysFields.style.display = "block";

    }


    /* Required fields */

    courseDateInput.required =
      selectedType === "one-day";

    startDateInput.required =
      selectedType === "several-days";

    endDateInput.required =
      selectedType === "several-days";


    /* Prevent end date being before start date */

    if (startDateInput.value) {

      endDateInput.min =
        startDateInput.value;

    } else {

      endDateInput.removeAttribute("min");

    }

  }


  /* Date option changes */

  dateTypeInputs.forEach(input => {

    input.addEventListener(
      "change",
      () => {

        updateDateFields();

        clearFieldError("dates");

        saveDraft();
        updateProgress();

      }
    );

  });


  /* Date / time changes */

  [
    courseDateInput,
    oneDayStartTime,
    oneDayEndTime,
    severalDaysStartTime,
    severalDaysEndTime
  ].forEach(input => {

    input.addEventListener(
      "change",
      () => {

        clearFieldError("dates");

        saveDraft();
        updateProgress();

      }
    );

  });


  startDateInput.addEventListener(
    "change",
    () => {

      updateDateFields();

      clearFieldError("dates");

      saveDraft();
      updateProgress();

    }
  );


  endDateInput.addEventListener(
    "change",
    () => {

      clearFieldError("dates");

      saveDraft();
      updateProgress();

    }
  );


  /* Initialise */

  updateDateFields();

  /* =========================================================
     VALIDATION
  ========================================================= */

  function setFieldError(fieldName, hasError) {

    const wrapper =
      document.querySelector(
        `.field[data-field="${fieldName}"]`
      );

    if (!wrapper) return;

    wrapper.classList.toggle(
      "invalid",
      hasError
    );

    wrapper.classList.toggle(
      "valid",
      !hasError
    );

    wrapper.classList.add("touched");

  }


  function clearFieldError(fieldName) {
    setFieldError(fieldName, false);
  }


  function isValidUrl(value) {

    try {

      const parsed = new URL(value);

      return (
        parsed.protocol === "http:" ||
        parsed.protocol === "https:"
      );

    } catch (e) {

      return false;

    }

  }


  function validateForm() {

    const errors = [];

    const dateType = getSelectedDateType();

    const endBeforeStart =
      dateType === "several-days" &&
      startDateInput.value &&
      endDateInput.value &&
      endDateInput.value < startDateInput.value;

    const checks = [

      {
        field: "title",
        valid:
          titleInput.value.trim().length > 0,
        message:
          "Course title is required."
      },

      {
        field: "organisation",
        valid:
          organisationInput.value.trim().length > 0,
        message:
          "Organisation is required."
      },

      {
        field: "format",
        valid:
          formatSelect.value.trim().length > 0,
        message:
          "Please choose a format."
      },

      {
        field: "tags",
        valid:
          getSelectedTags().length > 0,
        message:
          "Please select at least one topic."
      },

      {
        field: "dates",
        valid:
          dateType.length > 0 &&
          getDateValue().length > 0 &&
          !endBeforeStart,
        message:
          endBeforeStart
            ? "The end date must be after the start date."
            : "Please select a date option and provide the required date(s)."
      },

      {
        field: "location",
        valid:
          locationInput.value.trim().length > 0,
        message:
          "Location is required."
      },

      {
        field: "url",
        valid:
          isValidUrl(urlInput.value.trim()),
        message:
          "Please enter a valid course URL starting with http:// or https://."
      }

    ];


    checks.forEach(check => {

      setFieldError(
        check.field,
        !check.valid
      );

      if (!check.valid) {
        errors.push(check.message);
      }

    });


    return errors;

  }


  /* =========================================================
     INLINE VALIDATION
  ========================================================= */

  const textInputs = [
    titleInput,
    organisationInput,
    locationInput,
    urlInput
  ];


  textInputs.forEach(input => {

    input.addEventListener("blur", () => {

      const fieldName =
        input === titleInput
          ? "title"
          : input === organisationInput
          ? "organisation"
          : input === locationInput
          ? "location"
          : "url";


      const value = input.value.trim();

      if (!value) {

        setFieldError(
          fieldName,
          true
        );

        return;

      }


      if (
        fieldName === "url" &&
        !isValidUrl(value)
      ) {

        setFieldError(
          fieldName,
          true
        );

        return;

      }


      clearFieldError(fieldName);

    });

  });


  formatSelect.addEventListener(
    "change",
    () => {

      formatSelect
        .closest(".field")
        .classList.add("touched");

      if (formatSelect.value) {
        clearFieldError("format");
      }

      saveDraft();
      updateProgress();

    }
  );


  /* =========================================================
     PROGRESS
  ========================================================= */

  function updateProgress() {

    const completed = [

      titleInput.value.trim().length > 0,

      organisationInput.value.trim().length > 0,

      formatSelect.value.trim().length > 0,

      getSelectedTags().length > 0,

      getDateValue().length > 0,

      locationInput.value.trim().length > 0,

      isValidUrl(urlInput.value.trim())

    ].filter(Boolean).length;


    const total = 7;

    const percentage =
      (completed / total) * 100;

    if (progressFill) {
      progressFill.style.width =
        `${percentage}%`;
    }

    if (progressCount) {
      progressCount.textContent =
        `${completed} of ${total} completed`;
    }


    if (!progressLabel) return;

    if (completed < 2) {

      progressLabel.textContent =
        "Course details";

    } else if (completed < 4) {

      progressLabel.textContent =
        "Format & topics";

    } else if (completed < 6) {

      progressLabel.textContent =
        "Schedule & location";

    } else if (completed < 7) {

      progressLabel.textContent =
        "Almost there";

    } else {

      progressLabel.textContent =
        "Ready to submit ✓";

    }

  }


  textInputs.forEach(input => {

    input.addEventListener(
      "input",
      () => {

        saveDraft();
        updateProgress();

      }
    );

  });


  /* =========================================================
     AUTOSAVE
  ========================================================= */

  let saveTimeout = null;


  function setDraftStatus(state, text) {

    draftStatus.classList.remove(
      "saved",
      "saving"
    );

    if (state) {
      draftStatus.classList.add(state);
    }

    draftStatusText.textContent = text;

  }


  function saveDraft() {

    clearTimeout(saveTimeout);

    setDraftStatus(
      "saving",
      "Saving draft..."
    );


    saveTimeout = setTimeout(() => {

      const draft = {

        title: titleInput.value,

        organisation:
          organisationInput.value,

        format:
          formatSelect.value,

        dateType:
          getSelectedDateType(),

        courseDate:
          courseDateInput.value,

        startDate:
          startDateInput.value,

        endDate:
          endDateInput.value,

        oneDayStartTime:
          oneDayStartTime.value,

        oneDayEndTime:
          oneDayEndTime.value,

        severalDaysStartTime:
          severalDaysStartTime.value,

        severalDaysEndTime:
          severalDaysEndTime.value,

        location:
          locationInput.value,

        url:
          urlInput.value,

        tags:
          getSelectedTags()

      };


      try {

        localStorage.setItem(
          DRAFT_KEY,
          JSON.stringify(draft)
        );

        setDraftStatus(
          "saved",
          "Draft saved automatically"
        );

      } catch (e) {

        setDraftStatus(
          "",
          "Draft saving is unavailable in this browser"
        );

      }

    }, 400);

  }


  function loadDraft() {

    let draft;

    try {

      const raw =
        localStorage.getItem(DRAFT_KEY);

      if (!raw) return;

      draft = JSON.parse(raw);

    } catch (e) {

      return;

    }


    if (!draft) return;


    titleInput.value =
      draft.title || "";

    organisationInput.value =
      draft.organisation || "";

    formatSelect.value =
      draft.format || "";


    dateTypeInputs.forEach(input => {

      input.checked =
        input.value === draft.dateType;

    });

    courseDateInput.value =
      draft.courseDate || "";

    startDateInput.value =
      draft.startDate || "";

    endDateInput.value =
      draft.endDate || "";

    oneDayStartTime.value =
      draft.oneDayStartTime || "";

    oneDayEndTime.value =
      draft.oneDayEndTime || "";

    severalDaysStartTime.value =
      draft.severalDaysStartTime || "";

    severalDaysEndTime.value =
      draft.severalDaysEndTime || "";

    updateDateFields();


    locationInput.value =
      draft.location || "";

    urlInput.value =
      draft.url || "";


    (draft.tags || []).forEach(value => {

      const radio =
        tagInputs.find(
          input => input.value === value
        );

      if (radio) {
        radio.checked = true;
      }

    });


    renderSelectedTags();
    updateProgress();


    setDraftStatus(
      "saved",
      "Your previous draft has been restored"
    );

  }


  function clearDraft() {

    try {

      localStorage.removeItem(
        DRAFT_KEY
      );

    } catch (e) {
      // Ignore storage errors.
    }

  }


  /* =========================================================
     SUBMIT
  ========================================================= */

  form.addEventListener(
    "submit",
    function (event) {

      event.preventDefault();


      const errors =
        validateForm();


      if (errors.length > 0) {

        errorList.innerHTML =
          errors
            .map(
              msg => `<li>${msg}</li>`
            )
            .join("");


        errorSummary.classList.add(
          "show"
        );


        errorSummary.scrollIntoView({
          behavior: "smooth",
          block: "start"
        });


        const firstInvalid =
          document.querySelector(
            ".field.invalid input, " +
            ".field.invalid select"
          );


        if (firstInvalid) {
          firstInvalid.focus();
        }


        return;

      }


      errorSummary.classList.remove(
        "show"
      );


      submitButton.classList.add(
        "loading"
      );

      submitButton.disabled = true;

      submitLabel.textContent =
        "Opening GitHub...";


      const title =
        titleInput.value.trim();

      const organisation =
        organisationInput.value.trim();

      const format =
        formatSelect.value.trim();

      const tags =
        getSelectedTags().join(", ");

      const dates =
        getDateValue();

      const location =
        locationInput.value.trim();

      const url =
        urlInput.value.trim();


      const issueTitle =
        `[Training suggestion] ${title}`;


      const issueBody =
`## Training course suggestion

### Course information

**Course title:** ${title}

**Organisation:** ${organisation}

**Format:** ${format}

**Topics / tags:** ${tags}

**Dates:** ${dates}

**Location:** ${location}

**Course URL:** ${url}

---

Thank you for suggesting a training course for the SHAREing External Training Catalogue!`;


      const githubUrl =
        "https://github.com/SHAREing-DRI/SHAREing-DRI.github.io/issues/new" +
        "?title=" +
        encodeURIComponent(issueTitle) +
        "&body=" +
        encodeURIComponent(issueBody) +
        "&labels=training-suggestion";


      setTimeout(() => {

        window.open(
          githubUrl,
          "_blank",
          "noopener"
        );


        submitButton.classList.remove(
          "loading"
        );

        submitButton.disabled = false;

        submitLabel.textContent =
          "Continue to GitHub →";


        successBanner.classList.add(
          "show"
        );


        successBanner.scrollIntoView({
          behavior: "smooth",
          block: "nearest"
        });


        clearDraft();


        setDraftStatus(
          "saved",
          "Submission prepared"
        );


      }, 300);

    }
  );


  /* =========================================================
     INITIALISE
  ========================================================= */

  loadDraft();
  renderSelectedTags();
  updateProgress();

})();
</script>