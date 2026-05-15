---
title: "Celeritas assessment"
layout: champions
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: https://images.pexels.com/photos/29652322/pexels-photo-29652322.jpeg
summary: Study Celeritas an notably focus on its single-precision potential and GPU suitability
wp: 1.1
workpackage: "wp1.1"
status: completed
outputs_label: View report
outputs_url: https://shareing-dri.github.io/assets/documents/SHAREing-mini-project-003--celeritas-code-assessment.html
person:
  name: Davide Costanzo
  institution: University of Sheffield
  image: /assets/profilepics/davide.png
---
## Outcomes

This project has now finished. The outcomes can be found in [this report](https://shareing-dri.github.io/assets/documents/SHAREing-mini-project-003--celeritas-code-assessment.html).


## Fit to programme

This was a proposed solution answering Task 003: Code Performance Assessment, behind [WP 1.1](/workpackages/workpackage-1/).


## Description

A GPU implantation of interactions is being developed by the Celeritas team, based at the
Oak Ridge laboratory in the US in collaboration with colleagues at Warwick Universities. A
recent review conducted at CERN demonstrated a good physics performance of this
implementation and an initial integration with the ATLAS experiment software.
The goal of this mini-project is to use the existing Celeritas code implementation to 

1. assess the performance of the code, via the use of profilers to identify potential bottleneck, 
2. assess the impact of the use of single vs double precision floating points, 
3. assess the ability to run code on AMD GPUs compared to the original CUDA implementation.



