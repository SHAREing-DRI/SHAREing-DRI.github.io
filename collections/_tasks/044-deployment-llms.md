---
title: "Deployment of LLMs on local infrastructure - Task 044"
layout: tasks
image: assets/images/logo.png
workpackage: "wp1.3"
status: open
---

## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 1.3](/workpackages/workpackage-1/).
The task number is 044.


## Summary

AI- and agent-driven development now dominates how research code gets written. Increasingly, using these tools isn't a matter of preference — it's a necessity for delivering robust solutions on the timescales modern research demands.

Yet this shift comes with real costs. From a systems perspective, relying on AI agents and large language models for programming raises hard questions that institutions can no longer ignore. Security, privacy, reliability, and digital sovereignty concerns are pushing many organizations to reconsider their dependence on US-based models and compute infrastructure for code development. The natural response is to bring LLM- and agent-based tooling in-house, running these models locally rather than through external providers.

## Methodology

This task description calls for a project exploring exactly that: how to install, configure, and roll out an open-weight model within a UK institution — one capable, in principle, of serving the needs of the entire UK research community. We propose to a project bidder evaluating GLM 5.2, a model already deployed in production by Cyfronet in Poland as part of the EU's research computing infrastructure. Systems of this class strike a compelling balance: they're powerful enough for serious coding workloads, yet modest enough in their hardware footprint that roughly eight NVIDIA GH200 cards are typically sufficient to host them.

The task's core objective is to make the OpenCode coding agent available to the broader user base. Beyond deployment, an ideal project would also produce practical guidance for system providers on running such models reliably at scale — including a careful study of workload placement, weighing whether components of OpenCode should run on developers' own machines versus shared compute nodes, so that agent activity doesn't inadvertently overwhelm or bring down login nodes.

## Outcomes

Working agent-based programming service which can, in theory, be rolled out to all of the UK.