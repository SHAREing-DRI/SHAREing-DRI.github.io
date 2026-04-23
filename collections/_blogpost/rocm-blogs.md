---
layout: blog
permalink: /blogpost/rocm-blogs/
title: "ROCm Blogs: Guides for HPC & AI Practitioners"
category: External
subtitle: "A collection of technical articles covering profiling and optimisation on AMD GPUs"
author: "Thomas Gibson"
author_image: "/assets/profilepics/ThomasGibson.png"
date: 2026-04-22
social_links:
  - title: LinkedIn
    url: "https://www.linkedin.com/company/shareing/"
  - title: Bluesky
    url: "https://bsky.app/profile/shareing.bsky.social"
  - title: Email
    url: "mailto:shareing@durham.ac.uk"
---

<p>
The <a href="https://rocm.blogs.amd.com/">AMD ROCm Blogs</a> site hosts a growing number of technical articles written by various teams at AMD with experience in
optimising software for AMD GPUs. Many of these articles are directly relevant for scientific software developers,
computational scientists, and research software engineers interested in kernel optimisation, profiling methodologies, GPU hardware architecture,
and programming models on AMD platforms.
</p>

<p>
This page brings together several articles from across the ROCm Blogs catalogue. Whether you are porting an application to AMD hardware,
learning to profile with ROCm tools, or exploring the performance capabilities of your application, this is a good place to start.
</p>

<h2>Optimisation</h2>

<p>
These articles address the practical work of making HPC codes run well on AMD GPUs: memory-bandwidth analysis, stencil tuning,
communication libraries, process placement, and sparse linear algebra. Several are multi-part series that build progressively from a
baseline implementation to more advanced tuning strategies.
</p>

<h3>Finite difference method -- Laplacian (4-part series)</h3>

<p>A HIP implementation of a finite-difference Laplacian stencil, progressing through roofline analysis, loop tiling, register pressure management, and cross-architecture scaling.</p>

<ol>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part1/README.html">Laplacian part 1</a>: baseline HIP kernel and roofline-style analysis</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part2/README.html">Laplacian part 2</a>: loop tiling and reordered read patterns</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part3/README.html">Laplacian part 3</a>: register pressure, launch bounds, non-temporal stores</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/finite-difference/laplacian-part4/README.html">Laplacian part 4</a>: scaling across hardware, cache limits, grid and subdomain strategies</li>
</ol>

<h3>Seismic stencil codes (3-part series)</h3>

<p>Performance optimisation of seismic stencil codes on AMD GPUs, from a baseline GPU implementation through to advanced tuning and performance results.</p>

<ol>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/seismic-stencils/part-1/README.html">Seismic stencil codes - part 1</a>: introduction and baseline GPU implementation</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/seismic-stencils/part-2/README.html">Seismic stencil codes - part 2</a>: optimisation strategies and memory access patterns</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/seismic-stencils/part-3/README.html">Seismic stencil codes - part 3</a>: advanced tuning and performance results</li>
</ol>

<h3>Affinity, placement, and order (2-part series)</h3>

<p>Process affinity, NUMA topology, and binding strategies for HPC workloads, including a case study on the Frontier supercomputer.</p>

<ol>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/affinity/part-1/README.html">Affinity part 1</a>: NUMA concepts, process placement and ordering strategies, and a Frontier node case study</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/affinity/part-2/README.html">Affinity part 2</a>: topology discovery tools, verifying affinity, and binding techniques for MPI, OpenMP, and hybrid applications</li>
</ol>

<h3>Standalone articles</h3>

<ul>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/spmv/part-1/README.html">Sparse matrix vector multiplication - part 1</a>: SpMV implementation and performance considerations on AMD hardware</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/mi300x-rccl-xgmi/README.html">Understanding RCCL bandwidth and xGMI performance on AMD Instinct MI300X</a>: inter-GPU communication bandwidth and collective performance on MI300X</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/register-pressure/README.html">Register pressure in AMD CDNA2 GPUs</a>: understanding and managing register allocation and occupancy on CDNA2 architecture</li>
</ul>


<h2>Profiling and tooling</h2>

<p>
These articles cover the AMD profiling ecosystem, portability toolchains, and compilers: the software infrastructure that supports development and performance analysis on AMD GPUs.
</p>

<h3>Performance profiling on AMD GPUs (3-part series)</h3>

<p>A structured guide to profiling on AMD hardware, moving from conceptual foundations through basic tool usage to advanced analysis techniques.</p>

<ol>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/profiling-guide/intro/README.html">Part 1: Foundations</a>: profiling concepts and introduction</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/profiling-guide/novice/README.html">Part 2: Basic usage</a>: first steps with ROCm profiling tools</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/profiling-guide/advanced/README.html">Part 3: Advanced usage</a>: multi-device profiling and optimisation workflows</li>
</ol>

<h3>Standalone articles</h3>

<ul>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/profilers/README.html">Introduction to profiling tools for AMD hardware</a>: an overview of the ROCm profiling and tracing tool landscape</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/rocprofiler-sdk/README.html">Introducing ROCprofiler SDK</a>: the latest toolkit for performance profiling on AMD GPUs</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/hipify/README.html">Application portability with HIP</a>: porting CUDA applications to HIP for AMD hardware</li>
  <li><a href="https://rocm.blogs.amd.com/ecosystems-and-partners/fortran-journey/README.html">Introducing AMD's next-gen Fortran compiler</a>: LLVM Flang-based compiler with OpenMP GPU offload and HIP interop</li>
</ul>


<h2>GPU architecture and programming models</h2>

<p>
These articles cover AMD GPU architecture from matrix cores and memory hierarchies to ISA-level detail, alongside practical
programming guides for HIP, OpenMP offloading, and C++ parallel algorithms.
</p>

<h3>Standalone articles</h3>

<ul>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/matrix-cores/README.html">AMD matrix cores</a>: an introduction to matrix core hardware and programming on AMD GPUs</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/mi200-memory-space/README.html">AMD Instinct MI200 GPU memory space overview</a>: memory hierarchy and address spaces on MI200</li>
  <li><a href="https://rocm.blogs.amd.com/high-performance-computing/jacobi/README.html">Jacobi solver with HIP and OpenMP offloading</a>: implementing a classic iterative solver on AMD GPUs using two programming models</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/hipstdpar/README.html">C++17 parallel algorithms and HIPSTDPAR</a>: running standard C++ parallel algorithms on AMD GPUs via HIPSTDPAR</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/amdgcn-isa/README.html">Reading AMD GPU ISA</a>: a practical guide to reading and interpreting AMD GCN/CDNA instruction set output</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/mi300a-programming/README.html">MI300A -- Exploring the APU advantage</a>: programming and performance considerations for the MI300A accelerated processing unit</li>
  <li><a href="https://rocm.blogs.amd.com/software-tools-optimization/gpu-aware-mpi/README.html">GPU-aware MPI with ROCm</a>: GPU-aware MPI programming model and direct device-buffer communication on AMD GPUs</li>
</ul>


<h2>About these blogs</h2>

<p>
The <a href="https://rocm.blogs.amd.com/">ROCm Blogs</a> site is maintained by AMD and publishes technical content spanning high-performance computing,
artificial intelligence, and GPU software development. The articles presented on this page were produced by AMD's HPC and AI Application Enablement teams.
For the full catalogue, visit <a href="https://rocm.blogs.amd.com/">rocm.blogs.amd.com</a>.
</p>

---
