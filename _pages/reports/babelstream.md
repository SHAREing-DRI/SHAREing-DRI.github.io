---
layout: splash
title: "Performance Assessment"
permalink: /reports/babelstream/
classes: wide
  
---


# BabelStream Performance Report

We list here below an early performance report of **BabelStream**, a modern
version of the STREAM benchmark which includes a multitude of programming
models, and sits within the UKRI Living Benchmarks project. We have built this
report on BabelStream because it is a user-friendly, synethetic benchmark and
so is a good case study for beginning to test SHAREing's performance
methodologies.

We use the UKRI Living Benchmarks repository of BabelStream as the reference
repository, linked
[here](https://github.com/ukri-bench/benchmark-s-babelstream), and focus on the
**OpenMP (CPU)** implementation.

## Pre-assessment

We here document the workflow needed for the analyst to ready BabelStream for
analysis. This assessment uses the Hamilton HPC cluster at Durham University.

### Benchmark preparation

We clone the code from BabelStream's repository 

```bash
git clone https://github.com/UoB-HPC/BabelStream.git .
```

and use Version 5.0 as the reference code, as recommended by the Living
Benchmark's documentation

```bash
cd BabelStream
git checkout v5.0
```

### Working environment

On the Hamilton cluster we require just a C++ compiler

```bash
module load  gcc
```

We run all benchmarks on the `multi` partition which gives exclusive access to
whole nodes.

### Compiler setup

We build the executable with

```bash
mkdir build
cd build
cmake -DMODEL=omp ../
make
```

We use the 'out-of-the-box' optimisations for now to see how BabelStream
performs as standard. However, we can also use MAQAO to check whether we are
using the maximum compiler optimisations available from the hardware.
Therefore, checking the
`BabelStream/build/CMakeFiles/omp-stream.dir/flags.make` file, the used
compiler flags are: `-DNDEBUG -O3 -march=native -fopenmp -std=c++11`.

### Benchmark complexity

BabelStream is a modern port of the STREAM benchmark so the benchmark scales
linearly with number of one-dimensional array elements. Out of the box the
benchmark is set up with $2^{27}$ elements.

### I/O

The I/O of BabelStream is incredibly minimal. There are no input files and the
only output is written to standard output showing some information on the
benchmark outcomes (e.g., measured memory bandwidths, etc.). Therefore, we
neglect I/O from our analysis.

### Machine details

A node on Hamilton is summarised below:

```bash
--------------------------------------------------------------------------------
CPU name:    AMD EPYC 7702 64-Core Processor                
CPU type:    AMD K17 (Zen2) architecture
CPU stepping:    0
********************************************************************************
Hardware Thread Topology
********************************************************************************
Sockets:        2
Cores per socket:    64
Threads per core:    1
--------------------------------------------------------------------------------
```

Across a node there are 8 NUMA domains (grouped in 16 cores). Each core has an
individual L1 and L2 cache, whereas the L3 cache is shared between 4 cores.

### Labelling of code parts

The benchmark is very simple in its construction as it is just a wrapper for
five compute kernels which are individually just singlarly nested for loops.
One difference between BabelStream and STREAM is that BabelStream contains a
'Dot' kernel which contains a reduction operation.

### Existing optimisations

This is not known, but the simple nature of BabelStream implies that this is
not a concern.

### Running

To run BabelStream, we simply use the command

```bash
./omp-stream
```

and we can set the number of cores through the `OMP_NUM_THREADS` environment
variable or through the SLURM resource statements in a job script.

## High-level assessment metrics

Below we present results on the high-level performance metrics for BabelStream.
As we only study the OpenMP (CPU) version of BabelStream our analysis is
restricted to just two of the five SHAREing performance metrics: **core**,
**intra-node**. Whilst we could measure **I/O** performance, BabelStream has
negligible I/O and so this would not give any meaningful information on
performance.

### Core

The table below contains the **core** metric which is the proportion of maximum
peak FLOPS achieved by the benchmark. We measure the maximum peak FLOPS using
`likwid-bench` and then measure the peak FLOPS achieved by BabelStream using
`likwid-perfctr`.

<div align="center">
  <img src="/assets/report-figs/babelstream/core-table.svg" alt="Core performance metric" width="900">
</div>

BabelStream is known to be a memory-bound benchmark used to test the memory
bandwidth of hardware, and so it is perhaps not surprising that the compute
rate is relative poor here.

### Intra-node

To investigate intra-node performance, we performance a strong scaling analysis
of BabelStream and use runtime as our only observable. Below is the parallel
efficiency computed here as the parallel speedup divided by the number of
cores. Observing just purely the runtime of BabelStream shows a rapid decrease
in the parallel efficiency. This is likely due to the relatively *small*
problem size of BabelStream. The yellow and red vertical dashed lines show the
core counts in which the parallel efficiency first drops below 80% and 60%,
respectively.

<div align="center">
  <img width="750" alt="Intra-node performance metric" src="/assets/report-figs/babelstream/intra-par-eff.svg">
</div>

Below are the runtimes for the BabelStream strong scaling. These strong scaling
results were found by using `likwid-pin` and so we fill up the cores in order.
Hence we see features in the low core counts. For example, beyond 16 cores
there is a steady decrease in runtime and on this hardware we know that we have
then filled up the first NUMA domain. Below 16 cores we see slightly
unpredictable runtime behaviour and so it could be worth digging into details
of Hamilton's configuration to potentially explain this behaviour.

<div align="center">
  <img width="750" alt="Intra-node performance metric" src="/assets/report-figs/babelstream/intra-times.svg">
</div>

The table below contains the **intra-node** metric. This metric is
characterised by the ratios between the total available core count and the core
counts at which the parallel efficiency drops below 60% and 80%. 

<div align="center">
  <img width="900" alt="Intra-node performance metric" src="/assets/report-figs/babelstream/intra-table.svg">
</div>

The system used for this assessment, Hamilton, has 128 cores per node, and so
as the parallel efficiency results show above, BabelStream's parallel
efficiency drops below 80% and 60% for two and three cores, respectively.
Hence, these metrics are heavily penalising because of the high number of
available cores. 

### Summary

Below we summarise our two metrics in the form of a Kiviat diagram. We can
see that both **core** and **intra-node** performance are poor here. Our core
performance metric takes into account only single-core compute rate, and as
BabelStream is a highly memory-bound benchmark this is perhaps not surprising.
However, a more detailed analysis of the core performance issue is necessary.

Likewise, the strong scaling results are poor. This could in part be due to
analysing a problem size which is 'too small', but again should be analysed in
further detail at the intra-node level. Performance issues can rarely be
decoupled, so it may be that these core and intra-node performance issues are
inter-dependent.

<div align="center">
  <img width="900" alt="Summary kiviat" src="/assets/report-figs/babelstream/summary.svg">
</div>

This is an early performance assessment of BabelStream and so is not a complete
performance report. As SHAREing's performance methodology develops, this
performance report will likely be modified and extended.
