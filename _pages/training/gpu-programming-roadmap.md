---
permalink: /training/gpu-programming-roadmap
title: "GPU Programming Knowledge Graph"
nodes:
  gpuArch1:
    name: Basic GPU architecture
    description: Before we can start programming GPU accelerators (of any brand), we need an understanding of some basic aspects of the hardware that affect how we need to structure our code and our thinking. Many introductions to GPU programming (for example, in CUDA and HIP) touch on this topic.
  cuda1:
    name: Introduction to CUDA
    description: CUDA is the C-based language developed by NVIDIA for programming their GPU accelerators. Introductory lessons assume no existing knowledge of GPU programming, introduce writing and executing kernels, and managing data transfer between host and device.
    priorKnowledge: [C]
    dependsOn: [gpuArch1]
  hip1:
    name: Introduction to HIP
    description: HIP is the C-based language developed by AMD for programming their GPU accelerators. Introductory lessons assume no existing knowledge of GPU programming, introduce writing and executing kernels, and managing data transfer between host and device.
    priorKnowledge: [C]
    dependsOn: [gpuArch1]
  slp:
    name: GPU programming using standard language methods
    description: Many GPU accelerators allow programming using parallelism constructs available as a standard part of programming languages. While this might not be as performant as using dedicated GPU languages or libraries, the barrier to entry is much lower. Lessons here should cover the basics of any parallel constructs unfamiliar to typical language users, before showing how they extend to running on GPU accelerators.
    priorKnowledge: ["C, Fortran, or Python"]
    dependsOn: [gpuArch1]
  omp:
    name: OpenMP for GPU programming
    description: OpenMP is a programming model for multithreaded parallel programming. Since version 4, it supports offloading to accelerators, including GPUs. Lessons here should assume no prior knowledge of OpenMP, introducing it from scratch but focusing on the aspects necessary for GPU offload.
    priorKnowledge: ["C or Fortran"]
    dependsOn: [gpuArch1]
  kokkos:
    name: Kokkos for performance-portable GPU programming
    description: Kokkos is a performance portable programming interface and library for C++, allowing the same program to target many programming models. This means that the same program can run on CPU and many different types of GPU accelerator, without needing to write specific additional instructions to support the GPU and manage communication with it.
    dependsOn: [gpuArch1]
  sycl:
    name: SYCL for performance-portable GPU programming
    description: |
      SYCL is a performance portable programming interface and library for C++, allowing the same program to target many programming models. This means that the same program can run on CPU and many different types of GPU accelerator, without needing to write specific additional instructions to support the GPU and manage communication with it.

      <i>(Since Intel currently does not have a compute-focused GPU accelerator on the market, and have ended their contract with Codeplay, who developed SYCL support for non-Intel platforms, and since SYCL support is not prioritised by non-Intel GPU accelerator manufacturers, the benefit of developing skills in this direction is currently limited.)</i>
    priorKnowledge: [C++]
    dependsOn: [gpuArch1]
  alpaka:
    name: Alpaka for performance-portable GPU programming
    description: Alpaka is a performance portable programming interface and library for C++, allowing the same program to target many programming models. This means that the same program can run on CPU and many different types of GPU accelerator, without needing to write specific additional instructions to support the GPU and manage communication with it.
    priorKnowledge: [C++]
    dependsOn: [gpuArch1]
  multicuda:
    name: Shared-memory multi-GPU programing with CUDA
    description: When programming for a single GPU accelerator, the only data transfers that need to be considered are from the CPU memory to the accelerator's, and back again. Once a program needs to use multiple accelerators, one must also consider transfers from one accelerator to another. NVIDIA have technologies to make this much faster than transferring via the host; lessons here cover how to use CUDA to utilise this functionality.
    dependsOn: [cuda1]
  mpi:
    name: Multi-node GPU programming
    priorKnowledge: [MPI]
    description: When GPU accelerated applications need to scale beyond a single node, it becomes increasingly challenging to maintain a high level of performance, particularly when data must be transferred from an accelerator on one node to another attached to a different node. Lessons here cover the available technologies to do this performantly, including accelerator-aware MPI, and how this interacts with the underlying libraries such as UCX and OpenFabrics.
    dependsOn: [multicuda, multihip]
    material:
    - name: GPU-aware MPI with ROCm
      url: https://rocm.blogs.amd.com/software-tools-optimization/gpu-aware-mpi/README.html
      description: AMD blog article introducing GPU-aware MPI
  cudaArch:
    name: NVIDIA device architecture
    description: While a basic understanding of the structure of GPU accelerators and the CUDA language allows one to write accelerated code, a more detailed understanding of the underlying hardware enables more targeted optimisations to be made, which can have a significant effect on performance. Lessons in this area talk in more depth about the specifics of how NVIDIA GPU accelerators work internally, and how programs can take advantage of this.
    dependsOn: [cuda1]
  amdArch:
    name: AMD device architecture
    description: While a basic understanding of the structure of GPU accelerators and the HIP language allows one to write accelerated code, a more detailed understanding of the underlying hardware enables more targeted optimisations to be made, which can have a significant effect on performance. Lessons in this area talk in more depth about the specifics of how AMD GPU accelerators work internally, and how programs can take advantage of this.
    dependsOn: [hip1]
    material:
    - name: AMD blogs on the SHAREing website
      url: https://shareing-dri.github.io/blogpost/rocm-blogs/
      description: A number of deep-dive articles on specialised AMD accelerator topics.
  intelArch:
    name: Intel device architecture
    description: While a basic understanding of the structure of GPU accelerators and the SYCL language allows one to write accelerated code, a more detailed understanding of the underlying hardware enables more targeted optimisations to be made, which can have a significant effect on performance. Lessons in this area talk in more depth about the specifics of how Intel GPU accelerators work internally, and how programs can take advantage of this.
    dependsOn: [sycl]
  multihip:
    name: Shared-memory multi-GPU programming with HIP
    leadsTo: [mpi]
    description: When programming for a single GPU accelerator, the only data transfers that need to be considered are from the CPU memory to the accelerator's, and back again. Once a program needs to use multiple accelerators, one must also consider transfers from one accelerator to another. AMD have technologies to make this much faster than transferring via the host; lessons here cover how to use HIP to utilise this functionality.
    dependsOn: [hip1]
---

<style>
a.back-link {
  font-style: italic;
  color: gray;
}
</style>

## Context

Developing performant accelerated software requires
learning a wide range of skills,
many of which build on each other.
In this graph,
we outline the building blocks of skills and knowledge needed,
and what their dependencies are,
so that you can plan your learning journey.

This diagram is a work-in-progress;
we welcome suggestions on skills missing from it,
and how they connect.

<a id="diagram">
<pre class="mermaid">
    graph LR
    {% for node in page.nodes %}
    {{ node[0] }}["`{{ node[1].name }}`"]
    {% endfor %}
    {% for node in page.nodes %}
    {% for parent in node[1].dependsOn %}
    {{ parent }} --> {{ node[0] }}
    {% endfor %}
    {% endfor %}
    {% for node in page.nodes %}
    click {{ node[0] }} "#{{ node[0] }}"
    {% endfor %}
</pre>

{% for node in page.nodes %}
<h2 id="{{ node[0] }}">{{ node[1].name }}</h2>

{{ node[1].description }}

{% if node[1].dependsOn %}
<p>Builds on:
<ul>
{% for dependency in node[1].dependsOn %}
<li><a href="#{{ dependency }}">{{ page.nodes[dependency].name }}</a></li>
{% endfor %}
</ul></p>
{% endif %}

{% if node[1].priorKnowledge %}
<p>Assumed prior (non-accelerator) knowledge:
<ul>
{% for knowledge in node[1].priorKnowledge %}
<li>{{ knowledge }}</li>
{% endfor %}
</ul></p>
{% endif %}

{% if node[1].material %}
<p>Relevant training includes:</p>
<ul>
{% for material in node[1].material %}
<li><a href="{{ material.url }}">{{ material.name }}</a>{% if material.description %}: {{ material.description }}{% endif %}</li>
{% endfor %}
</ul>
{% endif %}

<p><a href="#diagram" class="back-link">Back to the roadmap</a></p>
{% endfor %}


<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true, htmlLabels: false , securityLevel: 'loose' });
</script>
