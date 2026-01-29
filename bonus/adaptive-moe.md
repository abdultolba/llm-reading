# Adaptive Mixtures of Local Experts (1991)

**Authors:** Robert A. Jacobs, Michael I. Jordan, Steven J. Nowlan, Geoffrey E. Hinton  
**Link:** https://www.cs.toronto.edu/~hinton/absps/jjnh91.pdf

## Why this paper matters

This paper introduced the core idea behind Mixture-of-Experts decades before modern deep learning made it practical. It framed learning as a problem of routing inputs to specialized submodels rather than forcing a single model to handle all cases uniformly.

Many of the concepts that appear in modern MoE systems originate here.

## Core ideas

### Divide and conquer through specialization

The model consists of multiple expert networks and a gating network that learns to assign inputs to experts. Each expert specializes in a subset of the input space, while the gate learns how to combine their outputs.

This allows the system to represent complex functions by decomposing them into simpler components.

### Soft gating and probabilistic routing

Unlike many modern MoE systems that use hard routing, this paper uses soft probabilistic assignments. Inputs contribute to multiple experts with different weights.

This makes training smoother but increases computational cost.

### Learning expert specialization

Specialization emerges through joint training of the experts and the gating network. Experts naturally focus on different regions of the input space without explicit supervision.

This anticipates later observations about expert specialization in large sparse models.

## Results

The paper demonstrates improved performance on regression and classification tasks compared to monolithic models. It shows that mixtures can learn complex decision boundaries more efficiently than single networks.

While the scale is small by modern standards, the qualitative behavior is clear.

## Impact

This work laid the theoretical and conceptual groundwork for later MoE research. Many ideas that reappear in modern sparse Transformers, such as routing, specialization, and conditional computation, can be traced directly back to this paper.

It is often cited as the origin of the MoE paradigm.

## Modern perspective

The main limitation of early MoE models was computational cost and optimization difficulty. Modern hardware and optimization techniques resolved many of these issues, allowing the same ideas to scale dramatically.

Reading this paper highlights how long the core ideas have existed.

## Notes

This paper is best read as historical context. The implementation details are dated, but the conceptual structure remains highly relevant.
