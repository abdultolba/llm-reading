# PaLM: Scaling Language Modeling with Pathways (2022)

**Authors:** Aakanksha Chowdhery et al.  
**Link:** https://arxiv.org/abs/2204.02311

## Why this paper matters

PaLM is a systems paper as much as it is a modeling paper. It demonstrates what it takes to train extremely large dense language models reliably and efficiently across thousands of accelerators. The work shows that scaling is not only a question of architecture and data, but also of orchestration, parallelism, and infrastructure.

PaLM set a reference point for what large-scale dense training looks like when done well.

## Core ideas

### Pathways as a training system

Pathways is a distributed training system that allows a single model to be sharded across many devices with flexible parallelism strategies. It supports data, model, and pipeline parallelism simultaneously, enabling efficient utilization of large accelerator clusters.

This made it possible to scale dense models to sizes that would otherwise be impractical.

### Dense scaling at extreme size

PaLM is a dense Transformer trained at very large scale, rather than a sparse or MoE model. The paper shows that dense scaling continues to yield gains when supported by sufficient infrastructure and careful optimization.

This provides an important contrast to sparse approaches.

### Stability and engineering discipline

A major contribution of the paper is its emphasis on training stability. Choices around initialization, optimizer settings, precision, and fault tolerance are treated as central concerns rather than implementation details.

This highlights how fragile large-scale training can be without disciplined engineering.

## Results

PaLM achieves strong performance across a wide range of benchmarks, including reasoning, code, and multilingual tasks. The gains scale smoothly with model size, reinforcing earlier scaling law observations.

The model demonstrates particularly strong few-shot and reasoning behavior for its time.

## Impact

PaLM influenced how large organizations approached training infrastructure and model orchestration. It made clear that system design can be as limiting as algorithmic innovation when pushing scale.

The paper also served as a dense-model counterpoint during the rise of MoE architectures.

## Modern perspective

While many later systems incorporate sparsity or adaptive computation, the lessons from PaLM remain relevant. Even sparse models rely on similar infrastructure challenges around communication, fault tolerance, and scheduling.

Understanding PaLM helps clarify the real-world costs and constraints of frontier model training.

## Notes

This paper is best read with attention to the systems details rather than the headline parameter counts. It provides insight into what breaks first when models become very large.
