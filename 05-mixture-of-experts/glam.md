# GLaM: Generalist Language Model (2022)

**Authors:** Deng et al.  
**Link:** https://arxiv.org/abs/2112.06905

## Why this paper matters

GLaM provided large-scale empirical validation that Mixture-of-Experts models can outperform dense models while using significantly less compute at inference time. It showed that sparsity is not just a way to scale parameters, but a way to improve efficiency and quality simultaneously.

This paper made MoE a serious contender for frontier language modeling.

## Core ideas

### Sparse activation at scale

GLaM uses a MoE Transformer where each token activates only a small subset of experts. While the total parameter count is extremely large, the number of active parameters per token remains comparable to much smaller dense models.

This allows the model to benefit from large capacity without paying the full inference cost.

### Expert specialization

As training progresses, experts naturally specialize in different linguistic patterns, domains, or tasks. The model learns to route tokens to appropriate experts without explicit supervision.

This specialization contributes to both efficiency and performance gains.

### Compute-efficient scaling

The paper emphasizes training and evaluating models under fixed compute budgets. Under these constraints, sparse models outperform dense alternatives, demonstrating better use of available resources.

## Results

GLaM achieves state-of-the-art performance on several language modeling benchmarks while using a fraction of the inference compute of dense models with comparable or worse performance.

The results show that sparsity can be a quality win, not just a cost optimization.

## Impact

This work strengthened the case for sparse scaling and influenced later MoE designs in both closed and open models. It also highlighted the importance of evaluating models under realistic compute constraints rather than raw parameter counts.

GLaM helped shift discussions away from headline parameter numbers toward effective compute.

## Modern perspective

Many later MoE systems build directly on the lessons from GLaM, including improvements in routing, stability, and deployment. The paper remains a key reference for understanding why sparse models can compete with dense ones at scale.

## Notes

This paper is best read after Switch Transformers. Together, they show how MoE architectures can be scaled from a conceptual idea into a practical, high-performing system.
