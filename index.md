---
layout: home
title: Quarter 2 Project Brainstorm
---

# Tejas Mani

[tmani@ucsd.edu](mailto:tmani@ucsd.edu)

**Section:** D36: Agentic Workload Analysis at Scale for Health and Biotechnology Use Cases  
**Mentors:** Renu Raman and Bryan Chin

**1. What is the most interesting topic covered in your domain this quarter?**

The most interesting topic I have covered in my domain this quarter is how strongly hardware architecture specifications can affect LLM inference and other agentic workloads. I have carried out several CPU and GPU benchmarks on a variety of machines, and my main takeaway is that raw computational performance often does not translate directly into better performance for a real-world AI application. These systems rely heavily on memory bandwidth, resource allocation, and inference-engine optimization to increase efficiency. In agentic workflows, which create mixed workloads across the CPU and GPU, evaluating the entire system is more informative than relying on isolated benchmarks. A compound task such as a database lookup on the CPU followed by LLM inference on the GPU can reveal bottlenecks that component-level tests miss.

**2. Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

For my Quarter 2 Project, I would like to investigate how CPU/GPU resource allocation and distributed inference affect the scalability of complex agentic AI workloads. Each workload would be mixed, requiring both CPU and GPU resources, and I would evaluate how different systems perform when several of these tasks run concurrently.

I see two promising application domains. The first uses the NIH ChestX-ray14 dataset to evaluate an agentic research workflow in which multiple agents retrieve medical literature, query patient-image metadata, and generate research insights simultaneously. The second uses voice data to explore interactive educational agents that process student speech, generate responses, and produce spoken output. Although the final application domain is not yet selected, the central investigation would remain the same: determining how to maximize system performance for a realistic agentic workload. I would measure throughput, end-to-end latency, CPU and GPU utilization, scalability under concurrent requests, and other relevant agentic metrics. These measurements would help identify bottlenecks and determine which configurations are best suited to the selected real-world application.

**3. What is a potential change you’d make to the approach taken in your current Quarter 1 Project?**

One change I would make to my Quarter 1 Project is to prioritize benchmark automation and begin each benchmark with a specific hypothesis. Much of our initial work involved manually configuring machine environments and copying scripts. Although this was useful early on, it became inefficient once we needed to run tests across multiple machines. I would instead develop a benchmarking pipeline that automatically configures environments, records hardware and software stacks, executes benchmark runs, and collects results in a consistent format.

I would also define a research question for every benchmark before running it. Running a benchmark without a hypothesis produces measurements, but it does not necessarily support useful analysis. Specific research questions would help us design controlled experiments and isolate the factors affecting performance. Together, automation and hypothesis-driven benchmarking would make our process more efficient and allow us to spend more time analyzing comparable results that contribute to our overall objective.

**4. What other techniques would you be interested in using in your project?**

I would be interested in techniques that go beyond the benchmarking steps we have used so far. Traditional benchmarks provide useful metrics such as memory bandwidth, throughput, and time to first token, but performance-profiling tools can help explain why particular machine configurations behave as they do. For an agentic workflow, tracing CPU and GPU utilization, memory use, and latency across individual stages—such as retrieval, LLM inference, and output generation—could reveal exactly where bottlenecks occur. Those findings could guide optimization and inform concurrency tests in which the number of agents or simultaneous requests is increased systematically. Combined with our existing benchmarks, these techniques would provide a stronger basis for explaining what makes a system perform well.
