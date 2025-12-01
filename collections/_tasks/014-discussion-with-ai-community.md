---
title: "Discussion with AI community on barrier to adopting large shared resources - Task 014"
layout: tasks
image: assets/images/logo.png
summary: Case study and in-depth analysis how the larger AI community can be included in SHAREing's agenda.
workpackage: "wp2.3"
status: progress
---

## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 2.3](/about/workinggroups) and [WP 2.4](/about/workinggroups).

The task number is 014.


## Description

Despite the high demand for computational power for AI applications, uptake from AI 
applications of large shared compute platforms is surprisingly low. Anecdotally, 
researchers wanting to make use of AI are more inclined to procure their own hardware 
(frequently less powerful than that available as a shared resource, and which will be 
underutilised), or look for cloud time.


Hypothesised reasons for this include:

- That most AI training material produced by major vendors assumes that you are the only user on the hardware, running with root access, which does not translate directly to a traditional batch environment
- Users are more familiar with graphical/notebook interfaces, which do not easily automate in a batch system
- Users want the immediacy of seeing workloads start immediately, having rapid  failures in case of errors that can be iterated on quickly

These are, however, assumptions from the outside. The aim of this mini-project is to 
have a series of conversations (for example, one-to-one meetings, workshops, or focus 
groups) with members of the AI community, and interrogate which of these (or others) 
are the primary causes of lack of adoption of shared resources, and what can be done 
to make shared resources more attractive/useful for the AI community.

This should include conversations with the major shared AI platforms and centres - including the Bristol Centre for Supercomputing, the Alan Turing Institute, and the 
Edinburgh International Data Facility—and with a range of individual AI users.

A distinction should be drawn between projects doing training of new models, doing 
fine-tuning of existing models, and doing only inference using pre-existing models; the 
feedback of each group is important.

If possible, the work should tease out possible actions to make using large shared 
compute platforms for AI applications more approachable. This may include new 
training material or documentation of best practices for deploying AI applications in a 
shared environment; adjustments to deployment configurations (e.g. making notebook 
interfaces available on HPC, or using MIG GPUs to offer a large pool of GPUs for 
interactive use to test before submitting large batch workloads); or rethinking system 
software stacks at a lower level (e.g. improving deployment options for containerized 
workloads; having dual stacks where nodes may be transferred between Slurm and 
Kubernetes or similar).


## Outcomes

A summary report from discussions with members of the AI community on barriers to adopting shared resources. This should incorporate
- Feedback from training, fine-tuning, and inference-only users
- Suggestions for actions that may be taken, bearing in mind the limitations that systems need to retain compatibility with existing userbases, and to maximise utilisatio

