---
title: "Specification of Assessment Code Requirements"
layout: tasks
image: assets/images/logo.png
date: 2025-10-01
 # set date to completed if done
summary: Define what codes have to bring along to make them eligible for a code assessment.
---


## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 1.1](/about/workinggroups).

<!-- I need some pictures and links -->


## Description

SHAREing wants to enable RTP groups to build up a performance assessment service:
Groups can submit their codes and get a high-level overview back, from which we can identify next development steps, the best systems to run their code, or start an in-depth code analysis.

To submit a code, a user/developer must supply an ‘example’ benchmark of their code, i.e., a job configuration which is:

1. Small such that the analyst will not wait for hours or days.
2. Indicative of a typical workload.
3. Has to come along with all the descriptions such that RTPs can work on the code independently.

A submission has to enable a small team of RPTs or individuals to take a submitted code and make it run
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
the SC reproducibility badge) and distill it into a list of checkboxes. Obviously, a project tackling
this tasks might apply the guidelines immediately to some of their codes. 

## Outcomes

- Recommendation checklist how people can prepare a benchmark before they actually hand it over to someone else for a performance analysis.
- Some example setups (optional).

The recommendation checklist should be integrated into the [performance assessment workbook](/performance-assessment/guidebook.md) that we curate on SHAREing's webpage as living document.
However, it also should be distilled into a separate checklist that people can download/open on SHAREing's webpage and then work through.
  




