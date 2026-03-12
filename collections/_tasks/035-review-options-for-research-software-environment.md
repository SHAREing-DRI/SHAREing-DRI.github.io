---
title: "Review options for providing research software environment in HPC - Task 035"
layout: tasks
 # set date when task has been approved by consortium. Remove once completed. Will then go into history
image: assets/images/logo.png
summary: 
workpackage: "wp1.2"
status: open
---


## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 1.2](/workpackages/workpackage-1/).

The task number is 035.

<!-- I need some pictures and links -->

## Description
There are different approaches to providing specialist software packages required by users on HPC systems, often multiple versions of one library may be needed to be compiled for different architectures or with different versions. "Modules" may be used but incur an administration overhead for RTPs. Allowing users to build their own packages may incur CPU / disk costs. Containerisation may also introduce unknown software with potential security implications.

## Approach
Review the sort of packages required by system users and the issues involved in providing them on a modern, up to date cluster - system updates often break functionality in specialist "out-of-tree" packages. Investigate options for automating rebuilds where possible. Communicate with other providers to explore what success or otherwise they have had with different strategies for providing their user environment.

## Outputs

A report giving the pros and cons of the common methods for providing specialist software packages to HPC users, so that a particular system can make an informed decision as to what suits them.

