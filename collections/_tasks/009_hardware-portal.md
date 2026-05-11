---
title: "HPC testbed and production system information service"
layout: champions
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: https://images.pexels.com/photos/1375261/pexels-photo-1375261.jpeg
summary: Design and delivery of a portal where HPC testbeds can be catalogued.
workpackage: "wp1.3"
status: progress
person:
  name: Ed Bennett
  institution: Swansea University
  image: /assets/profilepics/Bennett.jpg
---

## Fit to programme

This was a proposed solution answering Task 009: Hardware Portal, behind [WP 1.3](/about/workinggroups).



## Summary

We will create a basic set of tools built on standard software hosting platforms (e.g. GitHub) that will use stored data about HPC testbeds and production systems to generate and host a site providing a uniform set of information about them to interested potential users. It will provide a light-touch, uniform methodology for HPC system managers to contribute and update information about their systems and policies, and a light-touch review process allowing this activity to be sustained past the funded period of SHAREing. 

## Outcomes

A basic static site structure will be created with Jekyll. This will be generated after each information update by a Continuous Integration workflow. Initially this will use GitHub Actions and GitHub Pages, but where possible the tools and workflows will be written flexibly such that they may be rapidly ported and deployed to another host (e.g. GitLab Pages, Codeberg, StaticHost.eu) should this become necessary or desirable. 

Individual systems (or partitions of systems) will be submitted as single Markdown files, with a structured information block at the top containing the required information. Jekyll templates will automatically translate this to a summary table showing all systems, broken down by scope (test bed or production system), linking to a more detailed information page on each system. 

For an initial minimal viable product, the small set of variables discussed in the call will be collected and tabulated; this will be expanded based on the output of mini-project 001 as the latter progresses. 

The use of Markdown will allow system managers to provide more free-form information on their systems, accessible on the detailed information page. 

