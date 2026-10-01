---
title: "Performance Modelling for Offloading - Task 048"
layout: tasks
image: assets/images/logo.png
workpackage: "wp1.2"
status: open
---

## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 1.2](/workpackages/workpackage-1/).

The task number is 048.


## Summary

Can we predict performance of GPU offloading or next generation CPUs for an existing code? The current assessment methodology focuses on analysing codes on specific, available hardware. However, one aspect of supporting code acceleration is to ask whether we can predict or model how a code’s performance may vary between CPU and GPU, to assess the gains of porting, or even between generations of these chips. Some level of modelling between different cluster sizes is offered by Extra-P, though this is more in the domain of scaling modelling. Instead, there is potential to explore whether we are able to make predictions, potentially at the kernel level, between chips.

## Methodology

The exploratory nature of this work means that some level of literature review is necessary. Potentially also reaching out to tool developers that sit more on the research end of things might be most useful (e.g., VI-HPS and POP). For some level of risk management: if it can shown that work of directly modelling between CPU and GPU, or different generations of hardware, seems infeasible, then kernel level performance modelling as a topic also appears to be highly relevant to understand available performance models to understand instruction-level performance patterns. For example, exploring tools like KernCraft and building this into the guidebook is also valuable.

## Outcomes

Any outcomes from this, be it on tools or methodology, should be added into the SHAREing guidebook. For example, materials on how to model the performance of compute kernels, or whole benchmarks, on how they can perform on difference architectures, particularly for predicting potential speedups for porting.