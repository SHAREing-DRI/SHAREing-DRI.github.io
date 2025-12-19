---
title: "Benchmark guidelines (kickstart) - Task 005"
layout: tasks
image: assets/images/logo.png
summary: Start a performance assessment overview/guidelines
workpackage: "wp1.2"
date: "05-12-2025"
status: completed
---

<style>

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

</style>

<div class="full-width-btn-container">
  <a class="full-width-btn" href="/assets/pdfs/shareing-benchmark-guide.pdf">
    🔎 Explore SHAREing's benchmark guidelines
  </a>
</div>

Through of combination of: discussions with researchers, the [SHAREing
performance assessment seminar](/events/202511-performance-webinar/) and a
review of benchmarking literature, this task has collated a proposed set of
guidelines for researchers and developers to design their own benchmark. We
here list a condensed set of recommendations. We believe that a benchmark
should:
1. capture several components of the mathematical or algorithmic features of
   the software
2. be representative of a typical job run, e.g., including realistic I/O calls
3. be configurable by the performance analyst, i.e., the example job should be
   easily scalable and should allow for features such as I/O to be switched off
or on
4. include documentation which explains how to build and run the benchmark,
   including details on compilers, libraries, etc. and their versions
5. not be too small, as this will behave more like a synthetic benchmark. It is
   likely easier for a performance analyst to reduce the size of the benchmark,
than increase it in any meaningful way.
For the full document discussing these guidelines further, please see the
document linked below.

## Outcomes

**This is a first iteration of the SHAREing benchmarking guidelines,
suggestions are highly encouraged!**

- [Document outlining the proposed SHAREing benchmark guidelines][report]
  - Attachment: [SHAREing proposed benchmark guidelines LaTeX][template-latex]

[report]: </assets/pdfs/shareing-benchmark-guide.pdf>
[template-latex]: </assets/pdfs/benchmark-guide-latex.zip>

## Fit to programme

This task has been identified by the working groups as part of the agenda
behind [WP 1.2](/about/workinggroups).

The task number is 005.

## Description

SHAREing is working toward a generic and simple performance assessment service.
For this, the project has to curate guidelines. The objective of this task is
to kickstart the curation of a benchmarking guide that SHAREing can continue to
iterate and improve. These guidelines describe a proposed set of
characteristics for a benchmark. In brief, this tasks posits that a benchmark
should accurately describe features of research software, whilst also being
configurable for a rigorous analysis.

