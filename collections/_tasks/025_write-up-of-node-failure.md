---
title: "Analysis of HPC node failure rates, with application to maintaining systems out of warranty"
layout: champions
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: https://images.pexels.com/photos/7858300/pexels-photo-7858300.jpeg
summary: Based on captured data over the years, including systems where dynamic power on/off is used.
workpackage: "wp2.3"
status: progress
person:
  name: Paul Walker
  role: HPC Senior Manager
  institution: Durham University
  image: /assets/profilepics/generic.jpg
---


## Fit to programme


This was a proposed solution answering Task 025: Write up of node failure rates, behind [WP 2.3](/workpackages/workpackage-2/).


## Summary

I work as an RTP supporting the Cosma HPC system, which will form the basis of this investigation. By mining Slurm accounting databases and cross-referencing with our internal fault and repair logs, I will analyse node failure rates as a function of hardware age, component type, and usage patterns. Cosma spans multiple hardware generations and includes both CPU-only and GPU-accelerated nodes, providing a useful range of data within a single facility.
The analysis will capture both overall and post-repair failure rates, and will explore additional factors such as cooling type, typical workload, and node complexity. The methods used will be fully documented to ensure reproducibility.
The key output will be an online report published on the SHAREing website with an associated DOI, providing valuable data to Resource Allocation Committees and funders planning refresh cycles. As a stretch goal, I would look to engage with RTP teams at other HPC facilities to gather comparable data, either as an extension of this project or as a natural follow-on."

## Outputs

We can provide data of mean time between failure of particular types of high-performance computing hardware under various workloads, to look at common points of weakness in the infrastructure. These can be published in a report visible online or to download. 

