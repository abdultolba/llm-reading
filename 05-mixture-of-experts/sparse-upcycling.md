# Sparse Upcycling: Training Mixture-of-Experts from Dense Checkpoints (2023)

**Authors:** Luke Metz, Daniel Y. Fu, et al.  
**Link:** https://arxiv.org/abs/2212.05055

## Why this paper matters

This paper showed that Mixture-of-Experts models do not need to be trained from scratch. Dense checkpoints can be converted into sparse MoE models and then continued training, reusing compute that would otherwise be discarded.

Sparse upcycling made MoE scaling far more practical and economically attractive.

## Core ideas

### Converting dense models into MoE

The approach starts from a trained dense model and replaces certain feed-forward layers with MoE layers. Expert weights are initialized by copying and perturbing the original dense weights rather than random initialization.

This preserves much of the learned representation while expanding model capacity.

### Efficient reuse of compute

By reusing dense checkpoints, the method avoids repeating the expensive early stages of training. The model begins MoE training from a strong baseline rather than from scratch.

This reframes sparsity as an extension of dense scaling rather than an alternative path.

### Stability during transition

The paper addresses training instabilities that can arise when introducing sparsity. Careful initialization, routing design, and training schedules allow the model to transition smoothly into an MoE regime.

This makes sparse training feasible even late in the training process.

## Results

Sparse upcycled models outperform both their original dense counterparts and similarly trained MoE models initialized from scratch, given the same additional compute.

The results demonstrate that sparsity can be layered on top of existing systems effectively.

## Impact

This work lowered the barrier to experimenting with MoE architectures. Teams could first train dense models and later convert them into sparse ones as compute budgets allowed.

The idea influenced later practices around iterative scaling and model reuse.

## Modern perspective

Sparse upcycling fits naturally with modern training pipelines that emphasize reuse, modularity, and incremental improvement. It also complements Chinchilla-style scaling by allowing compute to be reallocated across training phases.

Many recent MoE systems implicitly follow this pattern even when not described as upcycling.

## Notes

This paper is best read after Switch Transformers and GLaM. It explains how sparse models can be introduced pragmatically rather than as an all-or-nothing architectural decision.
