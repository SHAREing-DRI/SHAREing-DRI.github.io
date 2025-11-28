---
title: "Performance Assessment Seminar"
icon_alt: Award icon
categories:
  - International
group: events
date: 2025-11-07
layout: event
image: assets/images/logo.png
project-type: Webinar
web-page: https://events.teams.microsoft.com/event/499b0cf2-b2b8-43c8-bf8c-4b59c52f6725@7250d88b-4b68-4529-be44-d59a2d8a6f94
location: Online
summary: This webinar brings together members of SHAREing and external collaborators to present the findings of performance assessments they have been involved in.
---

## Review and recap of Performance Assessment Webinar

On 07/11/25, SHAREing hosted an online seminar dedicated to performance
assessments. The aim of this event was to bring together members of the
community to present and discuss methods or experiences of producing
performance assessments for research software. The speakers consisted of:

* Thomas Flynn - Research Software Engineer at Durham University
* Marta Garcia Gasulla - Established Researcher at Barcelona Supercomputing
  Centre
* Martyn Guest - Director of Advanced Research Computing at Cardiff University
* Simon Burbidge - Research Software Engineer Team Lead for DiRAC High
  Performance Computing Facility

Here we give a brief summary of the talks, and the take away messages from the
discussions.

### Thomas' talk

The first talk focused on work undertaken at Durham University, supported by
the HAI-End and SHAREing projects, looking at the design of a performance
analysis methodology which breaks the analysis into three main categories:

1. Preparation
2. High-level analysis
3. Lower-level analysis

The **preparation** step consists of setup stages such as configuration of the
benchmark, environment, compiler optimisation, and switching off I/O and
pre-existing optimisation, such that the experiments are as reproducible and
performant as possible before the analysis begins.

The **high-level analysis** then seeks to break software performance into 5
main topics:
1. Core
2. Intra-node
3. Inter-node
4. GPU
5. I/O
with overall performance for each topic represented by a single metric. For
more details of this, please see the draft performance analysis workbook
[here](https://shareing-dri.github.io/assets/pdfs/perf_analysis_workbook_brief.pdf)
hosted on the SHAREing website.

The **lower-level analysis** was briefly mentioned, though it is in a very
early stage of development. The aim, however, of this component of the analysis
is to have binary decision trees for each of the performance topics. The aim of
these binary decision trees is to systematically investigate potential
performance issues by asking questions of particular performance
characteristics as we work down the tree. For each node of the tree the
methodology will suggest relevant performance tools for answering each
performance question.

This work is early in its development, and legitimate questions were raised
about how could this assessment methodology be used to compare different
hardware platforms, as this work seeks to do. More information on this work
will be updated in time on the SHAREing website.

### Marta's talk

The second talk presented the main features of the POP methodology used by the
POP performance assessment service. POP does not only offer this performance
assessment service, it is a consortium of performance tool developers, and
crucially the assessment service feeds back into the development of the tools
and methodology which then feeds back into the assessment service,
and so on.

Once a customer has filled out the application form and has supplied relevant
information, the first part of the service is in discussing which machine the
assessment will be run on, in order to generate the program traces. Crucially
the traces must be run on a system that is relevant to the machine that the
user/developer is typically using. There are two scenarios: one in which the
customer runs the traces and so the POP analyst supports the customer in using
the tracing tools; or, alternatively, the POP analyst collects the traces and
so the customer will be responsible for helping the POP analyst gain access to
the relevant machine. Following the preliminary work of deciding on the machine
and the example job configurations to be analysed, the structured performance
methodology is employed.

#### POP performance methodology

The structure of the current POP methodology is briefly summarised as follows:
* **Obtain traces with setup selected by customer** - this includes documenting
  the necessary steps to build the benchmarks (compilers, libraries, etc.), and
also crucial information on the hardware
* **Identify Structure and Focus of Analysis (FoA)** - the runtime is
  identified as having 3 phases: an initialisation phases, iteration phases and
a finalisation phase. For multiple iterations, we can pick out a subset of
these iterations if they are the same
* **Observe the scalability of FoA**
* **Obtain the efficiency metrics** - the efficiency metrics are often
  calculated as part of a scaling analysis to show how individual metrics
scale. Very low metrics then guide the analysis to what to focus on next
* **Detailed analysis based on outcomes of the efficiency metrics** - Following
  the metrics the analyst then digs into the feature which is highlighted as an
issue. A detailed analysis is carried out for each low efficiency metric
* **Insight on bottlenecks and optimisation suggestions**

With this methodology POP has been successful with performance analysis of
large, scalable research software. POP is a well established performance
assessment service, and has accumulated significant expertise in both
performance tools and analysis methodologies, and SHAREing will certainly
benefit by learning from POP's experienced perspectives on performance
analysis. 

### Martyn's talk

The third talk discussed 'assessing performance', with Martyn presenting
experiences on good benchmarking practices, popular benchmarks/tools, and
approaches and lessons learned on using these benchmarks to compare variations
within a system or comparisons of different systems, with the aim of being
measurable and repeatable.

Points were raised around making benchmarks that are relevant, understandable
and are scalable such that they can cover a spectrum of hardware and
architectures. However, there is a human aspect to benchmarking in that they
must be accepted and embraced by users, researchers and vendors. Finally,
benchmarks are often split into synthetic or application benchmarks, and for
much of SHAREing's work the application benchmarks will likely dominate. 

Similarly, Martyn discussed: how do we distill down performance metrics of our
benchmarks?  We can begin by using some simple benchmarks, e.g.: execution
time, effectiveness such as sustained peak efficiency or energy efficiency
(more relevant now than ever) and memory consumption, and performance measures
such as sustained performance, roofline or even score based metrics as we see
from HPCG score. However, you can also use more detailed metrics such as
FLOPS, hardware bandwidth, latency, interconnect bandwidth, storage bandwidth,
etc.

How do you present this data? Martyn explained his preference for [Kiviat
diagrams](https://en.wikipedia.org/wiki/Radar_chart) and how they can be used
to compare different systems. Each spoke of the diagram represents a different
application and the runtimes are normalised to the most performant. It can be
useful to create Kiviat diagrams to compare the proportion of:
* CPU scalar operations
* CPU vector operations
* CPU memory accesses
or also the proportion of runtime spent in CPU operations vs. MPI.

Finally, Martyn touches on the differences between core-to-core comparisons and
node-to-node. *core to core* comparisons, i.e., jobs with a fixed number of
cores, can be used to compare generation to generation of core performance
though these gains are often now minimal. Whereas *node to node* comparisons
often highlight the performance improvements of increasing core counts on the
node level.

This talk was a really useful overview of Martyn's experience in benchmarking
applications and computer clusters for multi-generational comparisons. These
methods are highly relevant for testing machines, and the insights from this
talk are vital for building reliable, trusted benchmarking and reporting
methods in SHAREing.

### Simon's talk

The fourth and final talk was motivated by the rise of GPUs but the
acknowledgement that DiRAC want to avoid using significant development time in
porting codes to GPU that won't benefit from it. Hence, they are developing a
methodology to see whether a code will benefit from porting by giving research
teams an RSE for 3-months to study the applicability of GPUs to their software.

Simon broke down the structure of the GPU exploratory work as: firstly,
characterising the code, its algorithms and underlying maths, then
determining if its likely to perform well on a GPU and an estimate of the
amount of effort required to perform the refactoring. However, this stage can
also be a useful time to review good software practice and so they also check
if the code is clean and has a management system in place. Appropriate language
tools can also be used to check or validate code structure. Then comes some of
the performance work by checking if basic optimisation is in place. They also
profile the code to show performance bottlenecks and hot spots - i.e., also to
identify code blocks that are actually used in production (to avoid porting
unused code). They can also check to ensure basic vectorisation is in place and
identify some potential low hanging fruit for optimisations. These features are
then noted in a report and archived for future RSEs to work from.

They also make suggestions to improve researchers codes: for portability many
codes may benefit from greater use of libraries or, of relevance to GPU
porting, multi-platform programming languages such as OpenMP, Kokkos, SYCL,
etc. help avoid vendor lock in, and also mixed precision which may open up more
hardware choices if developers can exploit lower precision in their algorithms.
This work can create better software engineering skills in the researchers such
as taking training, using tools and using libraries. 

Simon's talk and the work that DiRAC is undertaking closely aligns with much of
SHAREing's vision, by seeking to make recommendations on performance to
researchers but also with a keen eye on the relevance of certain accelerators
to research software.

### Takeaways
The seminar ended with a set of small group discussions based on the
following questions:
1. Do we as a community want to achieve a single, universal performance
   analysis methodology? Or is there strength in having multiple methodologies?
2. What are the skills necessary for a 'performance analyst'? Do we expect
   these skills to be taken up by researchers and developers? Or should these
skills sit within a performance assessment service?
3. What are good ways of conveying the outputs of a performance assessment? For
   example, is a standardised report best? How else could a performance
assessment outcome look like?
4. The community of HPC users and developers is large, yet engagement with
   performance training and workshops can often be low. How do we better engage
with the wider community of HPC users and developers?

Overall, there was recognition that having multiple performance analysis
methodologies is a good thing, but the problem is potentially in uptake. How do
we get researchers and developers to implement good performance practice in
their software development. Some suggestions included ensuring that projects
have a performance-oriented RSE always working in the team. This could be
feasible for large software projects, but for smaller teams this may be
infeasible.  Other suggestions were about building a viable 'performance
community' to boost engagement. One way to begin building this community was
suggested to compile a glossary of common terms to help researchers and
developers understand the field and build that commonality for the community.

This workshop was beneficial in allowing members of SHAREing, and
the wider audience, to consider how we might conduct performance assessments,
particularly in the UK, but also how we build and maintain a performance
community into research software development.

## Event information

SHAREing is organising an afternoon webinar to present and discuss performance assessments. A core component of SHAREing's vision is to establish a performance assessment service, however, to achieve this aim we must understand what a performance assessment can be.

This webinar brings together members of SHAREing and external collaborators to present the findings of performance assessments they have been involved in. Through this webinar, we hope to gain a better understanding of what a performance assessment should include and how this builds into a service.


[Register for webinar](https://events.teams.microsoft.com/event/499b0cf2-b2b8-43c8-bf8c-4b59c52f6725@7250d88b-4b68-4529-be44-d59a2d8a6f94){: .btn .btn--event .btn--large}

**Agenda**

| Time         | Speaker / Session                                         | Title / Description                                                   |
|---------------|-----------------------------------------------------------|----------------------------------------------------------------------|
| 13:00–13:15   | **Welcome**                                              |                                                                   |
| 13:15–13:35   | **Thomas Flynn** (Durham University)                     | *Towards a methodology driven performance assessment*                |
| 13:35–13:55   | **Marta Garcia-Gasulla** (Barcelona Supercomputing Centre) | *POP turns ten: what have we learned?*                                                                |
| 13:55–14:05   | **Break**                                                |                                                                     |
| 14:05–14:25   | **Martyn Guest** (Cardiff University)                    | *Assessing Performance: Guidelines, Strategies and Lessons Learned*  |
| 14:25–14:45   | **Simon Burbidge** (DiRAC)                               | *HPC - foot hard down on the accelerator or change gear?*                                                                |
| 14:45–15:45   | **Q&A and Discussion**                                   |                                                                |
| 15:45–16:00   | **Wrap up**                                              |                                                                   |


