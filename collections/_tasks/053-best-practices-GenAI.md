---
title: "Explore best practices for using GenAI in Scientific Software development - Task 053"
layout: tasks
image: assets/images/logo.png
workpackage: "wp2.3"
status: open
---

## Fit to programme

This task has been identified by the working groups as part of the agenda behind [WP 2.3](/workpackages/workpackage-2/).

The task number is 053.


## Summary

The goal of this task is to explore the use of Generative AI (GenAI) for making efficient use of accelerate compute platforms. A lot of software developers now use GenAI. In fact, it appears that soon these tools will be firmly embedded into software engineering workflows and there is increasing pressure to adapt GenAI tools to increase productivity. Recently, the use of GenAI in HPC workflows has also been explored. While offering great promises, for example by automatically porting code to different hardware, rapidly exploring different parallelisation strategies and compiler configurations, this also poses substantial risks: GenAI can hallucinate, produce subtle bugs (which are often even harder to spot in parallel code) and create significant technical debt. There are security risks on shared parallel compute clusters. For example agents might exploit loopholes in the cluster configuration to escalate permissions, launch parallel jobs without authorisation or use compute resources for unintended purposes. The goal of this task is to identify best practices and develop guidelines for using GenAI responsibly in scientific software development for accelerated compute.

## Methodology

Initially, capture GenAI use patterns for example through community questionnaires. Explore relevant existing work through a focused literature review. Run a workshop/hackathon to discuss opportunities and risks and formulate best practices, which would then be condensed into e-learning content. This can also include discussion of EDI aspects: GenAI has the potential to increase the diversity of the software engineering community by lowering the barrier to write code, but there are also risks. For example, paid access to some tools might lead to new obstacles which could exclude some user communities. On the other hand, GenAI might make it easier for new users to quickly learn concepts in parallel and accelerated computing, which often comes with a steep learning curve. Break down the GenAI risk/benefit analysis for different stages in the accelerated compute workflow, such as: (1) learning accelerated compute techiques, (2) code development, (3) testing, (4) parallel debugging, (5) profiling & optimisation on accelerate compute hardware and (6) orchestrating parallel job submission and hardware allocation. Maybe the outcome will be that the use of GenAI should be minimised as far as possible on accelerated compute platforms, but in this case it would be good to capture solid arguments which can be used to defend this approach, given the increasing pressure to use GenAI tools.

The topic has received increased attention recently. For example, there has been a workshop on "Foundational large Language Models Advances for HPC" in conjunction with ISC 2025 (https://ornl.github.io/events/llm4hpc2025/). As pointed out in [1], machine learning already has a significant impact on specific communities which rely heavily on large scale scientific computing.

A brief, non-exhaustive literature review shows that there is a growing body of work on GenAI and scientific software development in general [2], the use of AI agents to assist users in accessing HPC facilities [3] and automated porting of parallel scientific codes [4,5]. The authors of [6] describe a LLM based toolchain for HPC tasks.

One of the outcomes of this task will be to ensure that this knowledge is transferred to the community targetted by SHAREing.

*[1] Dueben, P., Bauer, P., Fuhrer, O., Koldunov, N. and Kristiansen, J., 2026. Machine learning is revolutionizing weather forecasting-the next step is a change in how we work. Journal of the European Meteorological Society, 5, p.100050.*

*[2] Acharya, V., 2025. Generative AI and the transformation of software development practices. arXiv preprint arXiv:2510.10819.*

*[3] Rosendo, D., DeWitt, S., Souza, R., Austria, P., Ghosal, T., McDonnell, M., Miller, R., Skluzacek, T., Haley, J., Turcksin, B. and McGaha, J., 2025, November. AI Agents for Enabling Autonomous Experiments at ORNL's HPC and Manufacturing User Facilities. In Proceedings of the SC'25 Workshops of the International Conference for High Performance Computing, Networking, Storage and Analysis (pp. 2354-2361).*

*[4] Valero-Lara, P., Godoy, W.F., Gonzalez, J., Huante, A., Gauthier-Chaparro, H., Gonzalez, J., Tang, Y.K., Teranishi, K. and Vetter, J.S., 2025, September. LLM-Driven Fortran-to-C/C++ Portability for Parallel Scientific Codes. In 2025 IEEE International Conference on eScience (eScience) (pp. 385-394). IEEE.*

*[5] Dhruv, A. and Dubey, A., 2025, June. Leveraging large language models for code translation and software development in scientific computing. In Proceedings of the Platform for Advanced Scientific Computing Conference (pp. 1-9).*

*[6] Valero Lara, P., Young, A., Vetter, J.S., Jin, Z., Pophale, S., Alaul Haque Monil, M., Teranishi, K. and Godoy, W.F., 2025, November. Chathpc: Building the foundations for a productive and trustworthy ai-assisted hpc ecosystem. In Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis (pp. 458-474).*

## Outcomes

In addition to a detailed literature review, the key deliverable would be a collection of material which can be used to teach best practices of using GenAI when developing scientific software for accelerated compute platforms. This could also be used as a community reference to justify the use/non-use of GenAI. The published material can consist of a set of relevant examples in the different application areas (such as software engineering, testing, parallel profiling & optimisation, debugging, hardware orchestration) and practical hands-on exercises. The best route for developing this could be a workshop where participants contribute a set of challenges which are then addressed both using traditional and GenAI-driven software development and use of accelerate compute platforms.