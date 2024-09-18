# LLM Serving Papers
**Last Update: 2024-09-11**
- [LLM Serving Papers](#llm-serving-papers)
  - [Survey](#survey)
  - [Offloading](#offloading)

## Survey
|Paper|Code|Category|Abstract
|--|--|--|--|
[[2407.12391] LLM Inference Serving: Survey of Recent Advances and Opportunities (arxiv.org)](https://arxiv.org/abs/2407.12391)|||Focus on system-level enhancements without altering LLM decoding algorithms, including memory (KV cache management), compute (scheduling), scalability (cloud-LLM) and emerging fields|
[[2407.14645] Performance Modeling and Workload Analysis of Distributed Large Language Model Training and Inference (arxiv.org)](https://arxiv.org/abs/2407.14645)||||
[[2404.14294] A Survey on Efficient Inference for Large Language Models (arxiv.org)](https://arxiv.org/abs/2404.14294)||||
[[2402.16363] LLM Inference Unveiled: Survey and Roofline Model Insights (arxiv.org)](https://arxiv.org/abs/2402.16363)|https://github.com/hahnyuan/LLM-Viewer||Framework based on Roofline model, profiling different hardware and inference configs. Cover model compression, algorithm, system and hardware optimizations|
[The CAP Principle for LLM Serving: A Survey of Long-Context Large Language Model Serving](https://arxiv.org/pdf/2405.11299)||Long Context||

## Offloading
|Paper|Code|Scenario|Challenge|Method|Category|
|--|--|--|--|--|--|
[[2303.06865] FlexGen: High-Throughput Generative Inference of Large Language Models with a Single GPU (arxiv.org)](https://arxiv.org/abs/2303.06865)|https://github.com/FMInference/FlexiGen|latency-insensitive tasks with batch processing|inefficiency in offloading with GPU,CPU,Disk. what to offload, where to offload in memory hierarchy, when to offload during inference|inference as computational graph. cost model by profiling IO and compute, with variables of tensor placements -> linear-programming model||
[[2408.07092] Post-Training Sparse Attention with Double Sparsity (arxiv.org)](https://arxiv.org/abs/2408.07092)|https://github.com/andy-yang-1/DoubleSparse|post-training sparse attention, retain full KV Cache|retrieval accuracy(retain full KV Cache), hardware-friendly(continuous memory access), memory usage(manage offloading with full KV Cache)|two level algorithm: static channel sparsity + dynamic token sparsity. engineering: compact label cache, prefetching token based on embedding similarities 