---
layout: splash
title: "ExaGRyPE Performance Report"
permalink: /reports/exagrype
classes: wide
  
---

# ExaGryPE Performance Report

A test submission for the performance assessment of [ExaGRyPE](https://hpcsoftware.pages.gitlab.lrz.de/Peano/dc/d1a/applications_exahype2_ExaGRyPE.html), available as part of the [Peano repository](https://gitlab.lrz.de/hpcsoftware/Peano.git) under the stable branch `p4`.

## Disclaimers

1. This is not a commentary on code quality, but an indicator of the quality of the current SHAREing testing methodology as of 16-03-2026.
2. This forms only a preliminary assessment of submission suitability and does not guarantee a full-assessment. The pre-assessment will be provided to the submitter with information on how to continue to assessment or rejection.

## Sections completed
- [x] [1: Benchmark setup](#1-benchmark-setup)
- [x] [2: Description of working environment](#2-description-of-working-environment)
- [x] [3: Compiler Setup](#3-compiler-setup)
- [x] [4: Code Complexity](#4-code-complexity)
- [x] [5: I/O](#5-memory-storage-and-io)
- [x] [6: Hardware information](#6-hardware-information)
- [x] [7: Code separation](#7-code-separation)
- [x] [8 Historic optimisations](#8-historic-optimisations)

## 1: Benchmark setup
The main codebase, Peano, that ExaGRyPE is a part of, can be cloned using:
```bash
git clone -b p4 https://gitlab.lrz.de/hpcsoftware/Peano.git
```

The submitter specifies the version on the `p4` branch (which is stable) must be used. The benchmark itself is part of the codebase and can be accessed, setup and run using:
```bash
cd benchmarks/exahype2/ccz4/single-black-hole

export PYTHONPATH=../../../../python:../../../../applications/exahype2/ccz4

python3 performance-studies.py -s fv-6 -et 1e-2 --plot 0.0 \
--cell-size 1.8 --trees 32 --scheduler native --output test

./test
```

The submitter has confirmed that the benchmark should take approximately 10 minutes to run.

### Varying input for scaling performance
The submitter has indicated that the program should scale linearly with the "number of cells" value. The provided example arguments for the benchmark generates 23479 cells in total.  The primary problem size parameter to be varied is the `--cell-size`. In the example provided this is set to `1.8`. The submitter has indicated that this can be changed in multiples of three.  Increasing the size of the parameter, for example to `5.2` leads to a smaller and coarser setup. This value can be read from the console output. For example:
```
27 tree(s): (#0:53/390)(#1:53/390)(#2:105/754)(#3:53/390)(#4:105/754)(#5:261/1534)(#6:105/754)(#7:53/390)(#8:105/754)(#9:53/390)(#10:105/754) (#11:261/1534)(#12:105/754)(#13:261/1534)(#14:20229/3250)(#15:261/1534)(#16:105/754)(#17:261/1534)(#18:105/754)(#19:53/390)(#20:105/754) (#21:53/390)(#22:105/754)(#23:261/1534)(#24:105/754)(#25:53/390)(#26:105/754) total=23479/24622 (local/virtual)
```
The submitter has provided [a link](https://hpcsoftware.pages.gitlab.lrz.de/Peano/d4/d35/benchmarks_exahype2_ccz4_single_black_hole_hpc_assessment.html) to detailed instructions and background information to the benchmark. This includes graphs detailing scaling in terms of load (number of cells and number of trees per rank) and runtime for two types of methodologies ([regular grid](https://hpcsoftware.pages.gitlab.lrz.de/Peano/d4/d35/benchmarks_exahype2_ccz4_single_black_hole_hpc_assessment.html#autotoc_md998) and [adaptive mesh](https://hpcsoftware.pages.gitlab.lrz.de/Peano/d4/d35/benchmarks_exahype2_ccz4_single_black_hole_hpc_assessment.html#autotoc_md1000)). Explanations for each setting are also provided.

## 2: Description of working environment
### Cluster: Hamilton
The submitter has provided the Hamilton cluster at Durham University as a reference hardware. The assessor is based at Durham University and will be using the same system for this pre-assessment. The system uses [SLURM](https://slurm.schedmd.com/overview.html) for job scheduling on compute nodes and [lmod](https://lmod.readthedocs.io/) to manage compute environments such as loading compilers etc. The documentation of the Peano codebase includes instructions for [setting up the working environment on Hamilton](https://hpcsoftware.pages.gitlab.lrz.de/Peano/dc/d26/page_machines_hamilton.html):
```
module purge
module load oneapi/2025.2
export FLAVOUR_NOCONFLICT=1
module load gcc/15.2
module load tbb/2022.0
module load intelmpi/2021.16
export I_MPI_CXX=icpx
module load python/3.13.9
```

Hamilton's hardware information will be provided in a [later section]().

### Tools required for pre-assessment and high-level assessment
1. Pre-assessment:
	- `top` and `time` for high-level wall time execution and memory usage analysis
	- `cat /proc/cpuinfo` and `likwid-topology` for hardware information
	- `maqao` to identify opportunities for compiler optimisation
2. High-level assessment:
	- `likwid-bench` and `likwid-perfctr` for measuring FLOPS
	- `likwid-pin` for thread pinning to measure performance within and across NUMA domains
3. Low-level assessment (may require admin privileges):
	- `vtune` for detailed profiling and hardware metrics (especially for Intel systems and compilers)
	- `valgrind` for detailed memory analysis
## 3: Compiler Setup
The submitter has provided the following instructions to compile Peano/ExaGRyPE:
```bash
libtoolize; aclocal; autoconf; autoheader; cp src/config.h.in .

automake --add-missing

./configure CXX=icpx CC=icx CXXFLAGS="-O3 -std=c++20 -xHost \
-fiopenmp -fsycl -Wno-unknown-attributes -Wno-gcc-compat" \
LDFLAGS="-fiopenmp -fsycl" LIBS="-ltbb" --enable-particles \ 
--enable-exahype --enable-blockstructured --with-multithreading=omp \ 
--enable-loadbalancing --with-mpi=mpicxx

make
```

The [GNU Autotools](https://www.gnu.org/software/automake/manual/html_node/Autotools-Introduction.html) build system (`configure` and `make`) is used for compilation. The submitter has provided specific instructions for configuring the build for ExaGRyPE and the benchmark provided.

The submitter has included the recommended `-xHost` flag to enable hardware-specific optimisations. The `-03` optimisation flag ensures aggressive optimisation while complying with FP standards. The code is compiled for the C++20 standard and using Intel compilers (`icx` and `icpx`). The submitter indicated a preference for the latest Intel compilers. On Hamilton, the latest compilers are a part of the [Intel oneAPI 2025.02](https://www.intel.com/content/www/us/en/developer/articles/technical/oneapi-2025-2-parallelism-unleashed.html) suite.

Based on the environmental setup described [earlier](#cluster-hamilton), the `mpicxx` compiler will be set to use `icpx`. To disable MPI, the `--with-mpi` flag can be removed. Intel's version of OpenMP is used with the `-fiopenmp` flag.

 GPUs are not enabled by default and would have to be enabled with a `--with-gpu` flag. But the submitter has indicated that they prefer the initial analysis to be done without GPUs.

 No reported issues in terms of impact of optimisations on convergence and correctness of results provided by the submitter.

The submitter has indicated further details on compilation flags can be found within [Peano's documentation](https://hpcsoftware.pages.gitlab.lrz.de/Peano/de/dd9/page_installation_home.html).

## 4: Code Complexity
Apart from the variable parameter for the benchmark [discussed earlier](#varying-input-for-scaling-performance) (`--cell-size`), the [linked documentation](https://hpcsoftware.pages.gitlab.lrz.de/Peano/d4/d35/benchmarks_exahype2_ccz4_single_black_hole_hpc_assessment.html) lists other variable parameters that could impact the performance and scaling such as the type of solver used, the load balancing paradigm, task scheduling etc.

The submitter has indicated that they assume that a "one MPI rank per NUMA domain" configuration may be optimal and that there is "no restriction on GPU-MPI association".

## 5: Memory, Storage and I/O
The regions of interest in the output can be identified using (comments directly quoted from submitter):
```
// Calculation starts as the code plots start
AlgorithmicStep [TimeStep]

// The quantity of interest is the actual solve phase which is plotted
// eventually as
time stepping: 85.1353s (avg=17.0271,#measurements=5,max=23.0463(value #0),min=5.28955(value #3)
```

Apart from the essential console output, the submitter has indicated that unnecessary I/O (plots) can be switched off by providing the `--plot 0.0` argument to `performance-studies.py`. The submitter has emphasised that using any other value for `--plot` enables the output. They also noted that that the code neither reads nor writes to large input files. 

No estimate of the memory usage was provided by the submitter.

## 6: Hardware information
The hardware details for Hamilton are [available online](https://www.durham.ac.uk/research/institutes-and-centres/advanced-research-computing/hamilton-supercomputer/systems/). This information is corroborated by running `cat /proc/cpuinfo` and `likwid-topology` on the one of the compute nodes via an interactive session on the test queue: `srun -p test --pty bash`

There are 120 standard compute nodes and 2 high-memory ones:

| Specification       | Per node                                                                                                                                        |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Processors          | 2x [AMD EPYC 7702 64-Core Processor](https://www.amd.com/en/support/downloads/drivers.html/processors/epyc/epyc-7002-series/amd-epyc-7702.html) |
| Clock speed per CPU | 3289.415MHz                                                                                                                                     |
| Sockets             | 2                                                                                                                                               |
| Cores               | 128                                                                                                                                             |
| RAM                 | Standard: 256GB (246GB available to users)<br>High-memory: 2TB                                                                                  |
| Local storage       | 400GB SSD                                                                                                                                       |
Each socket on each compute node is divided into 4 NUMA domains that each have a dedicated memory channel. Each of these NUMA domains are further split into 4 groups, where each has its own 16MB L3 cache (totalling to 256MB in one processor). Each of these groups contains 4 core that each have 512KB of L2 cache and 32KB of L1 cache.
## 7: Code separation

No labelled code sections are provided by the submitter.
## 8: Historic optimisations
No specific historic optimisation information provided by the submitter.

## Additional information from submitter
### Dimensions of assessment
The submitter has indicated that out of the three performance dimensions, the ones relevant to this assessment and benchmark are:
1. Core-level assessment
2. Intra-node assessment
3. GPU/accelerator assessment

## Pre-assessment report
### Compilation issues
The assessor set up the modules on Hamilton as [described earlier](#cluster-hamilton) and confirmed them using `module list`:
```
Currently Loaded Modulefiles:
  1) oneapi/2025.2      3) tbb/2022.0         5) python/3.13.9
  2) gcc/15.2           4) intelmpi/2021.16
```
The assessor then cloned and built Peano following [the compilation instructions](#3-compiler-setup). The code was compiled on the login node. The `-j 16` flag was used with `make` to speed-up compilation and did not produce any errors.

The assessor then followed the instructions to [compile the benchmark](#1-benchmark-setup) on the login node. The default version of Python on Hamilton had some missing libraries resulting in an error when attempting to compile the benchmark. The assessor found the list of required libraries within the [Peano documentation](https://hpcsoftware.pages.gitlab.lrz.de/Peano/df/dbc/tutorials_exahype2_applications_exagrype_faq.html#autotoc_md723): `jinja2`, `ast_comment` and `vtk` and installed them in a virtual environment. This allowed for the compilation to go ahead. However, an additional parameter of `-j 16` needed to be provided to `performance-studies.py` to keep the compilation from taking over an entire node. In the assessor's experience however, regardless of the number of thread used with `-j`, the compilation got stuck for several minutes and exited after reporting termination "by signal 9". This was reported on both the login node and on the compute node via `srun -N 1 --pty bash` with the latter indicating an "out-of-memory" error.

### Final comments
The assessor unfortunately was unable to complete the pre-assessment due to the compilation issues reported above and so cannot proceed any further. The issues have been reported to the submitter who will liaise with the assessment team to solve the bottleneck after which the assessor will repeat the pre-assessment.