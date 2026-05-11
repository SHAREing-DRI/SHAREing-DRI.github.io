---
title: "Example Preparation and Benchmarking of Community Codes using CASTEP"
layout: champions
date: 2025-10-01
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: https://images.pexels.com/photos/7723368/pexels-photo-7723368.jpeg
summary: Study behaviour and efficiency of community code's GPU port 
workpackage: "wp1.1"
status: progress
person:
  name: Oscar van Vuren
  role: 
  institution: Cardiff University
  image: /assets/profilepics/generic.jpg

---


## Fit to programme

This was a proposed solution answering Task 019: Community GPU codes: Castep, behind [WP 2.3](/workpackages/workpackage-2/).


## Summary

Benchmarking and testing of academic codes is a challenging task, due to the number and scale of available software packages and compilation/hardware environments. This work will develop best practice for preparing a code for performance evaluation, ensuring optimal, reproducible and rigorous analysis of software packages. We will use the CASTEP electronic structure code to develop an example of such best practice. This practice will be fully documented to ensure portability to other community academic codes, allowing compute resource managers and academics to get optimal performance from a given code running on the specific hardware available to them. 

## Outcomes

We intend to produce a high- quality example of how community electronic structure codes should be prepared for performance evaluation. This will take the form of a published checklist of critical elements such as a full build script, key optimisation flags and a representative test case for community codes to use as a template.  Additionally, we will write this checklist into a detailed section in the performance assessment workbook to aid in SHAREing’s goal of making performance assessments simple and accessible.

A worked example, including a detailed workflow, of the preparation required for community codes, using CASTEP, will be made fully available via code hosting services such as GitHub. This worked example will align with the checklist, acting as a demonstration case for software preparation.

Build and execution scripts for exemplar CASTEP runs will be provided for all the compilation environments available to the team, via the testbeds identified. These will include functional builds for all architectures and combinations of compilers and libraries, and, where possible, optimal build flags for these systems. Additionally, performance data will be gathered during this process and delivered to SHAREing for comparison with the black-box performance assessment. This data, and the build scripts through which it was generated, will be made available to the wider HPC community through GitHub.
  

