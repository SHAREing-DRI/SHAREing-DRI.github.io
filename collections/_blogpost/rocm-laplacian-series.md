---
layout: blog
permalink: /blogpost/rocm-laplacian-series/
title: "Optimising a finite difference Laplacian kernel on AMD GPUs"
category: External
subtitle: "Four-part series for optimising a Laplacian kernel on AMD GPUs"
author: "AMD HPC Application Enablement Team"
author_image: ""
hero_image: ""
date: 2026-03-20
social_links:
  - title: LinkedIn
    url: "https://www.linkedin.com/company/shareing/"
  - title: Bluesky
    url: "https://bsky.app/profile/shareing.bsky.social"
  - title: Email
    url: "mailto:shareing@durham.ac.uk"
---

This page lists a **four-part series** on the AMD ROCm Blogs site. It walks through a HIP implementation of a finite-difference Laplacian stencil and
introduces memory-bandwidth analysis, loop tiling, access reordering, launch bounds, and tuning across different GPU architectures.

The articles below are hosted by AMD.

## Finite difference method - Laplacian four-part series

1. [Finite difference method – Laplacian part 1](https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part1/README.html) — baseline HIP kernel, roofline-style analysis, profiling with `rocprof`
2. [Finite difference method – Laplacian part 2](https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part2/README.html) — loop tiling and reordered read patterns
3. [Finite difference method – Laplacian part 3](https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part3/README.html) — register pressure, launch bounds, non-temporal stores
4. [Finite difference method – Laplacian part 4](https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part4/README.html) — scaling across hardware, cache limits, grid and subdomain strategies

---
