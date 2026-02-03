---
title: "Write up of node failure rates - Task 025"
layout: tasks
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: assets/images/logo.png
summary: Based on captured data over the years, including systems where dynamic power on/off is used.
workpackage: "wp2.3"
status: open
---


## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 2.3](/workpackages/workpackage-2/).

The task number is 025.

<!-- I need some pictures and links -->

## Summary

HPC facilities consist of many individual server nodes working in
parallel.  Failures are not uncommon, and can include RAM, CPU, disk
and motherboard problems.  When under warranty, these failed
components are replaced by the system vendor.  However, once the
system is out of warranty, either funding must be found to replace
these components, or the system is left to gradually shrink in size.

Replaced out-of-warranty components are often from resellers
(refurbished), and may themselves have issues.

This project should explore and investigate failure rate of different
HPC systems over the years, and seek to document how likely components
are to fail.  This in tern will then provide information about likely
system shrinkage rates, which will be invaluable to Resource
Allocation Committees and funders when seeing to predict future system
availability and requirements for refresh cycles.

In carrying out this project, RTP skills in bash system accounting and
diagnostics will be developed and improved.  The methods used will be
documented and made available online.

## Approach

Information within the batch system (e.g Slurm, PBS) databases should be
captured and studied, to work out node failure rates as a function of
time.  Additionally information about vendor and self-supported
repairs will be gathered from logs taken by the RTP teams.

This information should be analysed to capture the overall node failure rate,
and the actual node failure rate (after any repair).  Failure rate as a
function as age should be extracted.

Additional information which could affect failure rate should also be
gathered.  This includes cooling type, node behaviour and typical
usage (are they run at 100% all the time, are they powered off when
not in use, are they often idle,etc), and also node complexity: do
they have accelerators, serve multiple networks, hosts multiple disks,
etc.



## Outputs

The key output should be an online report documenting node failure rates
for different hardware types and ages.  Additionally, the recipe
followed to determine rates should be provided.  These should be presented
on the SHAREing website with an associated DOI.

