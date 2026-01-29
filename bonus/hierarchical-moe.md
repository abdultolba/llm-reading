# Hierarchical Mixtures of Experts and the EM Algorithm (1994)

**Authors:** Michael I. Jordan, Robert A. Jacobs  
**Link:** https://www.cs.toronto.edu/~hinton/absps/jjnh94.pdf

## Why this paper matters

This paper extended the original Mixture-of-Experts framework by introducing hierarchical routing. Instead of a single gating network selecting among experts, experts are organized into a tree, allowing decisions to be made at multiple levels.

The work anticipated many ideas that later reappeared in large-scale sparse models, particularly around structured routing and conditional computation.

## Core ideas

### Hierarchical gating

Inputs are routed through a hierarchy of gating networks, with each level making progressively finer-grained decisions. Early gates select broad categories, while later gates select more specialized experts.

This reduces the effective routing complexity and allows the system to scale to larger numbers of experts.

### Tree-structured specialization

The hierarchy encourages experts to specialize at different levels of abstraction. Higher-level experts capture coarse distinctions, while lower-level experts focus on fine-grained patterns.

This mirrors how specialization often emerges in modern MoE systems.

### EM-based training

The paper uses expectation–maximization to train both the gating networks and the experts. This provides a principled probabilistic framework for learning routing decisions and expert parameters jointly.

While EM is rarely used directly in modern deep learning, the conceptual separation it enforces remains influential.

## Results

The hierarchical mixture outperforms flat mixtures on several tasks by improving scalability and specialization. The results show that structured routing can be more effective than a single gating layer.

Although the experiments are small, the qualitative insights generalize.

## Impact

This paper completed the early theoretical foundation of Mixture-of-Experts models. Many later systems implicitly adopt hierarchical or multi-stage routing, even when not explicitly framed this way.

The work provided a blueprint for thinking about routing as a structured decision process.

## Modern perspective

Modern MoE models typically use simpler routing mechanisms for efficiency, but hierarchical ideas resurface in routing heuristics, expert grouping, and multi-level sparsity.

Reading this paper highlights how many modern ideas were explored decades earlier, limited mainly by hardware and optimization techniques.

## Notes

This paper is best read after Adaptive Mixtures of Local Experts. Together, they form the conceptual roots of sparse and conditional computation in modern neural networks.
