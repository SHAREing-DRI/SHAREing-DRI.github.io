---
title: "Benchmark guidelines (kickstart)"
layout: champions
image: https://images.pexels.com/photos/6077600/pexels-photo-6077600.jpeg
summary: Start a performance assessment overview/guidelines
workpackage: "wp1.2"
date: "05-12-2025"
status: completed
outputs_label: Explore SHAREing's benchmark guidelines
outputs_url: http://127.0.0.1:4000/assets/pdfs/shareing-benchmark-guide.pdf
person:
  name: Thomas Flynn
  role: 
  institution: Durham University
  image: /assets/profilepics/thomas.jpg
---


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

This was a proposed solution answering Task 005: DBenchmark Guideline, behind [WP 1.2](/workpackages/workpackage-1/).


## Description

SHAREing is working toward a generic and simple performance assessment service.
For this, the project has to curate guidelines. The objective of this task is
to kickstart the curation of a benchmarking guide that SHAREing can continue to
iterate and improve. These guidelines describe a proposed set of
characteristics for a benchmark. In brief, this tasks posits that a benchmark
should accurately describe features of research software, whilst also being
configurable for a rigorous analysis.

