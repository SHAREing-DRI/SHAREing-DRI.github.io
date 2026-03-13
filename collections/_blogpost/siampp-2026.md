---
layout: blog
# Unique URL for this post
permalink: /blogpost/siampp26/
# Main title of the post
title: "SIAM PP26"
# E.g., Retreat, Workshop, Update
category: Conference
# Optional but recommended
subtitle: "An RSE at an academic scientific computing conference"
# Full name of the author
author: "Thomas Flynn"
author_image: /assets/profilepics/thomas.jpg
# Main post image
hero_image: /assets/eventphotos/siampp26_poster.jpg
# Date of the post, please use the format: YYYY/MM/DD
date: 2026-03-13
social_links:
  - title: LinkedIn
    url: "https://www.linkedin.com/company/shareing/"
  - title: Bluesky
    url: "https://bsky.app/profile/shareing.bsky.social"
  - title: Email
    url: "mailto:shareing@durham.ac.uk"
---

Last week I was fortunate enough to attend the **Society of Industrial and Applied Mathematics (SIAM) Conference on Parallel Processing for Scientific Computing (PP26)** hosted by the Zuse Institute Berlin and Free University of Berlin. During this conference I presented a poster on SHAREing with a focus on the methodologies being built into the developing performance assessment service. 

I also presented some of the training materials that have been created through the HAI-End project, including the [HPC Concepts Course](https://shareing-dri.github.io/hpc-concepts-course/). These themes were well received by representatives from several compute centres, in particular there appears to be a common trend in running specialised HPC training courses to audiences from a variety of research domains. This, to me, demonstrated the need for creating digestible training materials to bridge the gap between experts in scientific computing and domain-specific researchers. 

I was also able to attend multiple talk sessions and here I'd like to summarise some of my thoughts as a Research Software Engineer (RSE) at an ostensibly academic conference.

## Accelerators

Accelerated hardware was a major theme throughout many talk sessions that I attended. I feel these talks can roughly be split into two main categories:
1. Discussions on the process of porting codes
2. How new accelerated hardware informs algorithms

I will briefly touch on these two themes, and why I believe these are relevant to the SHAREing project but also more broadly the role of the digital Research Technical Professional (dRTP).

## Porting cores

Multiple talks were presented as software development talks in that they discussed an existing research codebase. Many of the talks would give details on the research domains and algorithms used, whilst motivating the need for acceleration. However, the specific discussions of code porting often seemed to show common trends. For example, there may be performance gains to be had from transformations of data structures when running on a GPU rather than the original CPU code. Though to explore this we should hope to apply a scientific methodology of experimentation. Nevertheless, it often seems as though these code modifications are based on convention and inherited knowledge within development groups.

Beyond modifications to the code structure there were similar discussions on which programming model developers choose, e.g., OpenMP or native programming languages such as CUDA and HIP. Furthermore, there were sessions showing the rise of the Julia programming language and its support both for GPUs and more exotic hardware. Some groups have strong justifications for choosing languages and programming models, although I am not sure this is always true. Therefore, it may make sense to give guidance about why some porting models may be more advised. OpenMP may give greater portability but may be more restrictive in some interfacing with the device.

I think this is highly relevant to some of the themes of SHAREing: code porting is happening everywhere but is often being done without a supporting methodology, running the risk of significant development time for poorer than predicted performance gains.

## Hardware informed algorithmic developments

In several sessions that I attended another theme was apparent, that of algorithms which are influenced by current hardware trends. Many massively-parallel hardware platforms, from GPUs to more dedicated Machine Learning (ML) hardware chips are increasing the lower precision compute rate, whilst gains in double precision on data center GPUs plateau or even decrease with newer generations. This has implications on the algorithms we can implement on our hardware.

Multiple sessions were focused on the use of mixed precision. For example, some talks focused on type emulation, i.e., using lower precision registers and arithmetic units on hardware to emulate higher precision variables. If we are to use hardware that contains fewer and fewer double precision registers, then can we build type emulation into our algorithms and potentially experience performance gains. Other algorithms consisted of using lower precision operations to produce double precision outputs particularly in matrix operations.

These talks did not, however, just focus on type emulation. There were also talks on implementing greater amount of mixed precision into existing software including an interesting discussion of the RAPTOR tool which can be used to profile codes and study regions where lower precision may benefit a code. Hardware trends clearly indicate a proliferation of lower precision compute, and so being to exploit these trends in our software could lead to performance gains. In ML this lower precision is not a major concern though in simulation codes we often require high precision and so the community will not receive these performance gains for free. Likewise, granting dRTPs and researchers access to novel hardware for this development is key.

## Final thoughts

Within the Digital Research Infrastructure (DRI) community we are seeing a variety of DRI facing conferences including the DRI Retreat, RSECon and a myriad of smaller workshops and events curated by individual DRI projects. However, I think there is real benefit in dRTPS attending academic conferences, particularly conferences such as SIAM PP which report on the latest research in numerical methods and parallel algorithms. I think there can be significant benefits to research communities if some dRTPs can act as the bridge between these computational research conferences and the domain specific researchers they work with, i.e., being exposed to the latest research in these methods and translating them into their research software.

I link [here](/assets/pdfs/siam_pp26_poster.pdf) to a copy of my SIAM PP26 poster.

---
