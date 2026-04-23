---
title: "Create “Introduction to Accelerated Computing” episode for existing training courses on software performance - Task 037"
layout: tasks
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: assets/images/logo.png
summary: 
workpackage: "wp2.3"
status: open
---


## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 2.3](/workpackages/workpackage-2/).

The task number is 037.

<!-- I need some pictures and links -->

## Description
There are several existing training courses that introduce researchers and dRTPs to the basics of performance profiling and optimisation. (E.g., this Carpentries Incubator course: https://carpentries-incubator.github.io/pando-python/index.html) Adding a short, self-contained episode on accelerated computing to these courses would help get a foot in the door with a much wider audience, who might see a dedicated training course on accelerators as too technical or specialised.

The focus of this episode should be on picking the low-hanging fruit—e.g., drop-in replacements for commonly used scientific Python packages that benefit from accelerators to deliver significant performance boost with minimal code changes. Changes that require significant rewrites are beyond the scope of this task.

The episode should contain a brief explanation of how accelerators work, to help learners understand what types of tasks they excel at (and which ones do not benefit). It should also feature several toy examples of these types of tasks, illustrating the code changes needed to benefit from acceleration and the resulting performance improvements.

## Outputs and deliverables

Submitted outputs should:
* contain a brief explanation of how accelerators work (including figures/illustrations as appropriate)
* contain several toy examples demonstrating how accelerators offer performance improvements with minor code changes[1]
* contain 1–2 toy examples demonstrating types of tasks where accelerators do not offer benefits
* take about 15–30 min to teach, to fit into existing courses
* include instructor notes, where necessary
* include a list of required third-party packages and setup instructions, where necessary
* ensure examples run on multiple operating systems (should include Linux, macOS and WSL; optionally also regular Windows)

All outputs must be published under an appropriate license allowing it to be included in other courses. (E.g., CC-BY for learning materials and MIT for sample code, as used by the Carpentries.)

They may be published as a PR on the Carpentries Incubator course (https://github.com/carpentries-incubator/pando-python/) or as a stand-alone repo with the rendered version available on the SHAREing website.

[1] See e.g. https://carpentries-incubator.github.io/pando-python/optimisation-data-structures-algorithms.html#exercise-unique-collection for a similar toy example illustrating the performance benefit of selecting the right data structure.

