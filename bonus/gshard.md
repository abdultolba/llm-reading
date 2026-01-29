# GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding (2020)

**Authors:** Dmitry Lepikhin et al.  
**Link:** https://arxiv.org/abs/2006.16668

## Why this paper matters

GShard addressed a practical bottleneck in scaling large models: how to train models with massive parameter counts across many devices without hand-designed parallelism strategies. It introduced automatic sharding techniques that made large-scale sparse models tractable.

The work provided critical infrastructure for later Mixture-of-Experts systems.

## Core ideas

### Automatic sharding

GShard automatically partitions model parameters and computation across devices. Instead of manually specifying how tensors are split, the system infers sharding strategies based on the computation graph.

This significantly reduces engineering overhead when scaling models.

### Conditional computation support

The system is designed to handle conditional computation, where different inputs activate different subsets of parameters. This is essential for MoE models, where expert routing creates dynamic execution paths.

GShard ensures that these dynamic patterns remain efficient and scalable.

### Tight integration with training systems

GShard is tightly coupled with large-scale training infrastructure, handling communication, synchronization, and fault tolerance. This integration makes it possible to scale sparse models without sacrificing reliability.

The focus is on making large models trainable in practice.

## Results

The paper demonstrates that GShard enables training of very large sparse models with strong performance and manageable overhead. It supports both dense and sparse architectures, but shows particular benefits for MoE-style models.

These results helped validate sparsity as a scalable approach.

## Impact

GShard became a foundational component in Google’s large-model training stack. It influenced later systems and provided key support for models like Switch Transformers and GLaM.

The paper helped shift attention toward systems-level solutions for scaling, not just architectural changes.

## Modern perspective

Many ideas from GShard now appear in modern distributed training frameworks, even outside Google. Automatic sharding and flexible parallelism are now expected features rather than experimental ones.

Understanding GShard helps clarify why large sparse models became feasible when they did.

## Notes

This paper is best read alongside Switch Transformers and other MoE work. It explains the systems advances that made those models possible at scale.
