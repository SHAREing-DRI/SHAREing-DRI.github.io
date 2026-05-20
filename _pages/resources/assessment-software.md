---
layout: splash
title: "Assessment Software"
permalink: /resources/assessment-software
classes: wide
---

# Performance Assessment Software Requirements

In order to perform a high-level assessment, we require different pieces of software for each rubric.
For several of the rubrics, there are several options of software that could be used.
As we continue to develop lower-level assessments, further pieces of software will be required.

This list is intended to provide a resource which can be handed to the platforms team for your HPC system to justify which software you are asking to be installed.

## High-Level Assessment

### Core
1. LIKWID
    - [website](https://hpc.fau.de/research/tools/likwid/), [github](https://github.com/RRZE-HPC/likwid), [wiki](https://github.com/RRZE-HPC/likwid/wiki)
    - Calculates FLOPS rate of the CPU core

### GPU
1. NVIDIA - Nsight Compute
    - [website](https://developer.nvidia.com/nsight-compute)
2. AMD - rocprofiler v3
    - [documentation](https://rocm.docs.amd.com/projects/rocprofiler/en/latest/index.html), [github](https://github.com/ROCm/rocm-systems/tree/develop/projects/rocprofiler), [rocprofv3 how-to](https://rocm.docs.amd.com/projects/rocprofiler-sdk/en/latest/how-to/using-rocprofv3.html)

### IO
1. darshan
    - [website](https://www.mcs.anl.gov/research/projects/darshan/), [github](https://github.com/darshan-hpc/darshan), [documentation](https://darshan.readthedocs.io/en/stable/)

### Intra-node and Inter-node
At high-level, these are scaling analyses done by comparing the time taken with different resource allocations and (for inter-node) different problem sizes.
The methodology therefore requires only the Unix `time` utility.

