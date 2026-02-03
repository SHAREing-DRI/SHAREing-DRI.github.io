---
title: "Lustre installation documentation - Task 022"
layout: tasks
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: assets/images/logo.png
summary: A write up of how we install various Lustre systems on different hardware here, including commandline flags for people to follow.
workpackage: "wp2.3"
status: open
---


## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 2.3](/workpackages/workpackage-2/).

The task number is 022.

<!-- I need some pictures and links -->

## Summary

Lustre is a high performance parallel file system used by the majority
of large scale computing systems, typically multi-Petabytes in size.
It is open source, and currently developed by several companies and
research institutions.  Some large-scale computing sites have the
technical capability and confidence to self-install and self-support
their Lustre file systems.  However, more commonly, confidence is
lacking and so expensive support contracts are used, along with vendor
specific Lustre implementations.

This project is seeking proposals to draw together recipes and
instructions that are used by self-installation of open source Lustre,
and which have been demonstrated to work.  It seeks practical
installation recipes on known (described) hardware configurations,
including any steps taken to optimise Lustre installations.

The captured documentation should also describe any weaknesses in the
designs, and lessons learned from the installations.  It should also
provide a description of any considerations taken into account when
ordering hardware, and when configuring the file system.  Each Lustre
installation performed at different institutions is slightly
different, on different types of hardware, and so different variations
of systems will also be documented.

This project will help to encourage and incentivise HPC teams to share
their internal Lustre documentation and installation notes.


## Approach and methodology

The projects responding to this call will select one or more Lustre
installations, primarily those in production, though prototype and
test systems are also within scope.

The hardware and software design decisions will be described and
documented.

A recipe for setting up and configuring the file system will be
documented, following any installation transcripts that are available
(likely with rationalisation, and removal of unnecessary trial
components, testing and experimentation).  RTP-friendly guides will be
developed, and key scripts, commandline instructions and codes will be
provided.

The hardware used for each system will be described in depth, with
considerations and rationale around why these specifications were
used.

Tuning information and documentation of performance testing will also
be provided, along with the pros and cons of the designs.

This will be a training opportunity for the RTPs carrying out the work,
as they will need to learn and understand the installation steps taken
and thereby gain information for future systems.

Should the opportunity arise, this information can then be used to aid
the design, installation and configuration of new systems.  The
project should also seek to deliver a talks at national events and
Lustre User Group meetings.

The projects should be feasible within timescale and budget.  A
stretch goal of a white paper will likely be achievable.

## Risk

Much of the information already exists, but typically in forms not easily
understandable, and so the key risk is timescale and effort
availability.

## Outputs

Documentation and installation guides hosted on the SHAREing website
and elsewhere.  A DOI record should be associated with the outputs
where possible.


