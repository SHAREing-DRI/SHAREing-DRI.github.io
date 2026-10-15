---
title: "Parallel Benchmark Games: A Community Challenge for Portable Research Software - Task 063"
layout: tasks
image: assets/images/logo.png
workpackage: "wp1.2"
status: open
---

## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 1.2](/workpackages/workpackage-2/).

The task number is 063.


## Summary

Modern research software increasingly depends on both CPUs and accelerators such as GPUs, yet researchers often lack clear and independent information about how software libraries perform across different hardware platforms. This makes it difficult to choose technologies, optimise applications and ensure that research software remains portable as computing systems evolve. 

This task will establish an open, community-driven benchmarking framework for parallel algorithms that broadly map onto those found in the C++ Standard Library and numeric libraries commonly used in research software. The benchmark suite will support contributions from a wide range of programming models and ecosystems. Potential examples include C++ libraries such as SYCL, Thrust, Kokkos and stdpar/execution policies, as well as comparable functionality provided by frameworks such as NumPy, PyTorch and the Fortran stdlib. Benchmarks should be executed across CPUs and GPUs from multiple hardware vendors, creating a transparent and reproducible picture of portability, functionality and performance. 

Beyond collecting results, the task will introduce a collaborative "benchmark games" model, where community members can contribute new benchmarks, improve benchmarking infrastructure and submit optimisations that increase the performance of existing implementations. This creates an open environment that encourages innovation, highlights best practices and helps identify opportunities for improving software portability and efficiency across platforms. 

The resulting benchmark suite, tooling and performance data will provide a valuable resource for the wider community. Researchers, software developers and infrastructure providers will be able to make evidence-based decisions about which libraries and programming models are best suited to their needs, while library developers gain actionable feedback on how their software performs across different architectures. By fostering collaboration and providing vendor-neutral performance insights, the project will help support more sustainable, portable and future-proof research software. 

## Methodology

This task will establish a community-driven benchmarking framework for evaluating the performance, portability and usability of parallel algorithm libraries across modern research computing platforms. The focus will be on algorithm implementations that broadly align with the C++ Standard Library (STL), providing a common and widely understood basis for comparison across different programming models, languages and software ecosystems. The STL has been selected because it represents a generic collection of fundamental algorithms and data-processing operations that are applicable across many scientific domains. The benchmark suite is not strictly limited to the C++ Standard Library, however. It may also incorporate standardised linear algebra routines, or additional algorithms that are important across a range of scientific computing workloads – FFT's are another set of algorithms that come to mind as an example.  

A key objective is the development of a standardised benchmarking methodology. Benchmark workloads, input datasets, execution environments and reporting requirements will be defined to ensure results are reproducible, comparable and transparent. Benchmark submissions should include profiling information and metadata describing hardware, software versions, compiler settings and execution parameters, allowing meaningful comparisons across platforms, vendors and programming models. 

To ensure fairness and consistency, benchmarking should initially be performed on a representative set of standardised CPU and GPU platforms. However, the framework should also enable community members to contribute results from additional hardware platforms that may not already be represented. Where appropriate, contributors may apply to benchmark systems available through their own organisations or on National Compute Resources (NCRs) to which they have access. This approach will allow the project to capture a broader view of the research computing landscape while maintaining a consistent methodology for comparison. 

An important component of the project is a community "benchmark games" model. Researchers, developers and software communities will be invited to contribute benchmark implementations, improve benchmark infrastructure, extend hardware coverage and submit optimised versions of existing algorithms. This collaborative approach encourages knowledge sharing, highlights best practices and creates a mechanism for identifying performance opportunities across software stacks and hardware platforms. The resulting benchmark data will help answer not only which libraries support particular architectures, but also how efficiently they perform across different vendors, systems and programming environments. 

Outputs should include openly available benchmark definitions, automation tooling, performance results, profiling data and supporting documentation. Results should be presented in a way that enables users to understand performance, portability, hardware support and ease of adoption across a range of architectures. 

To avoid the task becoming inflated, it should focus on the development of the benchmarking infrastructure, methodology and community engagement rather than creating new algorithm libraries. By leveraging existing software ecosystems and encouraging community participation, the project can deliver a sustainable and valuable resource for the community while providing evidence-based guidance on the performance and portability of software across current and future research computing platforms.

## Outcomes

The task should produce a publicly accessible benchmarking ecosystem that enables the community to contribute new benchmarks, hardware results and performance improvements over time. All outputs must be openly available, and applicants should clearly describe how they will ensure long-term public access, maintenance and discoverability. 

As a minimum, the task should deliver: 

- A public version-controlled repository (e.g. GitHub or equivalent) that serves as the authoritative source for the task. 

- A standardised and documented benchmark suite covering a representative set of STL-inspired algorithms and related scientific computing algorithms, including BLAS-like linear algebra operations where applicable. 

- Benchmarking infrastructure, scripts and documentation that enable users to install, configure and execute benchmarks on supported systems with minimal effort. 

- A reproducible methodology for collecting benchmark results, including guidance on profiling, metadata capture and reporting requirements. 

- Publicly accessible benchmark results covering a representative range of CPU and GPU architectures, vendors and software ecosystems. 

- Documentation describing supported libraries, hardware platforms, software environments and benchmarking procedures. 

- Community contribution guidelines covering the submission of new benchmarks, additional hardware results, optimised implementations and benchmarking infrastructure improvements. 

The repository should contain both the benchmark definitions and the associated results. This may be achieved either through a single repository or through linked repositories/submodules where appropriate. The goal is to provide a single discoverable location where users can find the benchmark suite, execute benchmarks themselves and compare the published results. 

To maximise value to the wider community, the benchmarking framework should be designed to support continuous expansion. New benchmark results should be easy to add as additional libraries, algorithms, hardware platforms and National Compute Resources (NCRs) become available. Contributors should be able to submit results from systems that were not part of the initial evaluation, subject to the agreed benchmarking methodology and reporting standards. 

Benchmark results should additionally be published in a human-readable form. At a minimum, summary reports and key findings should be made available through the SHAREing website and the git repository itself. 

This approach ensures that the outputs are not static, but a sustainable and evolving community resource for evaluating performance, portability and software support across the UK research computing landscape. 

 