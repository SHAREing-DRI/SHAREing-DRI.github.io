---
# BLOG POST METADATA
# Fill in the following fields. Do NOT remove the keys, just add the information.

layout: blog
# Unique URL for this post
permalink: /blogpost/check-your-gpu-is-working/
# Main title of the post
title: "Is Your GPU Actually Doing the Work?"
# E.g., Retreat, Workshop, Update
category: Update
# Optional but recommended
subtitle: "Lessons from benchmarking an LLM helpdesk on an HPC cluster"
# Full name of the author
author: "Fawada Qaiser"
author_image: ""
# Main post image
hero_image: ""
# Date of the post, please use the format: YYYY/MM/DD
date: 2026/10/06
social_links:
  - title: LinkedIn
    url: ""
  - title: Bluesky
    url: ""
  - title: Email
    url: "mailto:fawada.qaiser@durham.ac.uk"
---

<p>More and more AI services are being deployed on HPC systems — retrieval-augmented chatbots, inference endpoints, copilots for researchers. These aren't traditional simulation codes, and they behave differently under the microscope. We recently ran a performance assessment of one such service — a self-hosted RAG helpdesk that answers HPC support questions from local documentation, running an 8-billion-parameter language model on a GPU node — and it surfaced a few lessons that apply to almost any LLM-on-cluster deployment. None of them are exotic. That's exactly why they're worth sharing.</p>

<h2>Lesson 1: A working AI service and a GPU-accelerated one can look identical</h2>

<p>The service was deployed on a GPU node specifically to run inference on the accelerator. It answered questions correctly. It felt fine. By every outward sign, it was working.</p>

<p>It wasn't using the GPU.</p>

<p>We only caught it because we measured raw token-generation speed against what the hardware should deliver. The model was generating at around 5.7 tokens per second — far too slow for a model of that size on a data-centre GPU. Digging into the inference engine's logs revealed the cause: GPU discovery was silently timing out, and the engine was falling back to running the model entirely on the CPU. Not one layer of the model was on the GPU. The expensive accelerator — the whole reason for using that node — sat idle while the CPU did all the work.</p>

<p>There was no error message. No crash. Just answers that were slower than they should have been, in a way nobody would notice without a baseline to compare against.</p>

<div class="blog-quote">A correct answer tells you nothing about whether your accelerator is engaged. If you deploy LLM inference on a GPU, verify the GPU is actually being used — don't infer it from the fact that the service responds.</div>

<p>Inference frameworks are designed to degrade gracefully — if they can't reach the GPU, many will quietly run on CPU rather than fail. That "graceful" fallback can hide in production for a long time. Check that the model's layers are offloaded to the device, and watch device utilisation during a real request.</p>

<h2>Lesson 2: The fix was one line — and the payoff was ~40×</h2>

<p>The root cause was mundane: the inference service was being started from an environment that didn't have the GPU runtime libraries loaded. Without them on the library path, the framework couldn't find the GPU, discovery timed out, and it fell back to CPU. No component was broken; the pieces just weren't wired together at startup.</p>

<p>Loading the correct GPU runtime module before starting the service fixed it completely. The GPU was discovered, the whole model offloaded to it, and generation throughput jumped from ~5.7 to ~227 tokens per second — roughly a <strong>40× improvement</strong> from a one-line change to how the service launches.</p>

<p>The generalisable point: environment setup is part of the deployment, not a detail. A service that starts from an incomplete environment can run — just badly, and silently. It's worth making the correct startup environment explicit and verifiable, and ideally having startup fail loudly if the accelerator isn't found, rather than degrade quietly.</p>

<h2>Lesson 3: Measure where the time actually goes before optimising</h2>

<p>Once the GPU was working, we tested how the service handled multiple simultaneous users — the metric that actually matters for a shared service. Here came the surprise: fixing the GPU barely changed throughput under load. Single-user responses got much faster, but the number of users served per minute stayed roughly the same — around 30 either way.</p>

<p>That seems paradoxical until you break a request into its parts. We instrumented the service to time each stage separately, and the result was stark: <strong>document retrieval — the "search" half of retrieval-augmented generation — takes about 3% of a request. Text generation takes the other 97%.</strong></p>

<p>So neither of the "obvious" optimisation targets was the bottleneck. Retrieval was already negligible; making it faster would gain nothing. And the GPU wasn't the limit either — it blasts through each generation quickly. The real constraint was architectural: the service processed requests one at a time, generating a single stream on a single GPU. Watching device utilisation during concurrent load made it visible — the GPU spiked to near-100% for each generation, then went idle waiting for the next request, while the node's other GPUs were never touched at all.</p>

<div class="blog-quote">Decompose before you optimise. For a RAG service the intuitive suspects — vector search, retrieval, model speed — are often not where the time goes. Here, concurrency was limited by serialised generation, which points at a completely different fix than "speed up retrieval" or "buy faster hardware" would have.</div>

<h2>Lesson 4: AI services need service-appropriate assessment, not just HPC rubrics</h2>

<p>Traditional HPC performance assessment centres on things like CPU floating-point efficiency, memory scaling, and how a code scales across cores and nodes with MPI. A RAG chatbot fits almost none of that — there's no user-written compute kernel, no MPI, no multi-node execution, no core-count scaling knob to sweep.</p>

<p>Rather than force those rubrics and produce misleading numbers, we assessed the service on the metrics that genuinely characterise it: inference throughput (tokens per second), end-to-end response latency, cold-start versus warm behaviour, and concurrency. As AI workloads increasingly share HPC systems with simulation codes, this is a broader gap worth naming: our assessment toolkits need service-oriented rubrics — latency, throughput, concurrency, and answer quality — alongside the classic ones.</p>

<h2>The most important caveat: fast is not the same as correct</h2>

<p>Everything above is about performance — how fast the service runs and whether it uses the hardware well. It says nothing about whether the chatbot gives good answers: whether it retrieves the right documents and generates accurate, well-grounded responses rather than plausible-sounding fabrications.</p>

<p>That's a separate assessment, and a harder one. It needs a labelled set of questions with known-correct answers, and a mix of automated scoring and human review. We haven't done it yet. It's worth stating plainly, because a fast chatbot that confidently gives wrong answers is worse than a slow one — and performance benchmarks, however good, can't tell you which you have.</p>

<h2>Takeaways</h2>

<p><strong>Verify your accelerator is actually being used.</strong> A correct, responsive AI service can be running entirely on CPU. Check layer offload and device utilisation; don't assume.</p>

<p><strong>Treat startup environment as part of the deployment.</strong> Silent fallback from an incomplete environment is a real and costly failure mode. Prefer setups that fail loudly when the accelerator is missing.</p>

<p><strong>Decompose before optimising.</strong> For RAG services, retrieval and raw model speed are often not the bottleneck. Measure each stage; the constraint may be architectural.</p>

<p><strong>Performance and answer-quality are different assessments.</strong> Don't let a good benchmark stand in for a correct answer.</p>
