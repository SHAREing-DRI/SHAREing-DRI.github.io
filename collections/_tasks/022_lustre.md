---
title: "Practical Lustre installation and management guide development"
layout: champions
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: https://images.pexels.com/photos/12210678/pexels-photo-12210678.jpeg
summary: A write up of how we install various Lustre systems on different hardware here, including commandline flags for people to follow.
workpackage: "wp2.3"
status: progress
person:
  name: Alastair Basden
  role: Director of COSMA
  institution: Durham University
  image: "https://apps.dur.ac.uk/biography/image/1768"
---


## Fit to programme
This was a proposed solution answering Task 022: Lustre installation documentation, behind [WP 2.3](/workpackages/workpackage-2/).


<!-- I need some pictures and links -->

## Summary
Lustre is a high performance parallel file system used by the majority
of large scale computing systems, typically multi-Petabytes in
size. It is open source, and currently developed by several companies
and research institutions.   Very few large-scale accelerated
computing sites have the technical capability and confidence to
self-install and self-support their Lustre file systems, and so
expensive support contracts are used, along with vendor-specific
Lustre implementations.  Typically when upgrades and expansions are
needed, or failures occur, vendors can mandate significant maintenance
periods.

Recipes used by self-supporting sites are often not made public,
primarily due to a lack of effort, and each Lustre installation is
slightly different, on different hardware.  This proposal will draw
together a number of recipes, designs and instructions from operating
installations, including maintenance instructions, describing the
hardware configurations and the choices made.  Optimisation steps will
also be described.

This documentation will include design weaknesses, lessons learned,
and considerations taken into account during installation.


## Outputs

RTP-focused documentation for Lustre file system specification,
installation and configuration.

We will also deliver a talk at a national conference or Lustre User
Group meeting.


