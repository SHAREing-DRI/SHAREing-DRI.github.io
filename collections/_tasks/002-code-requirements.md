---
title: "Specification of Assessment Code Requirements"
layout: tasks
image: assets/images/logo.png
summary: Define what codes have to bring along to make them eligible for a code assessment.
---

<!-- I need some pictures and links -->

## Description


CASTEP is one all-time classic in HPC benchmarking and one of the workhorses on UK supercomputers.
The goal of this task is to take CASTEP and to see if we can curate an example run that allows an independent team to
assess the code’s performance. On the long term, we’d expect any team submitting codes to SHAREing to provide us with such
an example run before we start. However, we initially have to create a few
examples ourselves, so people know what to expect. 
The idea here is that we take CASTEP and we distlill from there what minimal requirements of a benchmark have to be.


To submit a code, a user/developer must supply an ‘example’ benchmark of their code, i.e., a job configuration which is:
    1. Small such that the analyst will not wait for hours or days
    2. Indicative of a typical workload
Outcome/acceptance:
    • Create a guideline for submitted benchmarks
Note: this mini-project has a strong overlap with WP 1.1  (Mini-Project 003): Code Performance Assessment . 


Importance: essential
Potential RTP groups for this project:
Description:
We want to run miniprojects, where small teams of RPTs take a submitted code and make it run
through a standardised black-box assessment. For this, code submitters must provide enough
information, so the RTP team can take the code and start working without a hassle. This means,
the submitting group has to provide some “at least” information, which could comprise (but is
not limited to):
1. Readme files with build instructions
2. Self-contained archive or download instructions
3. Containers
4. Invocation scripts
5. One single batch file that builds and executes everything
6. ...
It is the job of this workpackage to identify what kind of (reproducibility) information we expect
external codes to provide. For this, we have to study similar initiatives (cmp SSI, POP, but also
the SC reproducibility badge). The outcome is a document that clearly describes all
requirements. The team working on this miniproject has to work closely with project 001.
Outcome/acceptance:
• Submitted Pull Request to webpage


Obviously, the team taking up this task might want to go beyond the mere prep of benchmarking and actually do some benchmarking and analysis themselves. 
However, the core delivery of this task has to be a documentation of best practices on our webpages.


## Outcomes

- Brief experience report on the SHAREing webpages.
- Recommendation checklist how people can prepare a benchmark before they actually hand it over to someone else for a performance analysis.

The recommendation checklist should be integrated into the [performance assessment workbook](/performance-assessment/guidebook.md) that we curate on SHAREing's webpage as living document.
However, it also should be distilled into a separate checklist that people can download/open on SHAREing's webpage and then work through.
  




