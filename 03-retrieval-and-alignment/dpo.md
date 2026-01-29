# Direct Preference Optimization (2023)

**Authors:** Rafael Rafailov et al.  
**Link:** https://arxiv.org/abs/2305.18290

## Why this paper matters

This paper introduced a simpler and more stable alternative to reinforcement learning from human feedback. Direct Preference Optimization showed that preference alignment can be achieved directly through a supervised loss, without training an explicit reward model or running PPO.

DPO reduced the engineering complexity of alignment while preserving much of its effectiveness.

## Core ideas

### Preferences as a classification problem

DPO reframes preference learning as a binary classification task between a preferred and a dispreferred response. The model is trained to increase the likelihood of the preferred output relative to the rejected one.

This removes the need for a separate reward model.

### Implicit reward modeling

Although no reward model is trained explicitly, the optimization implicitly learns a reward function. The relative log-likelihood difference between responses plays the role of the reward signal.

This makes the training objective easier to reason about and debug.

### KL control via the loss

DPO includes a term that keeps the updated model close to the reference model. This serves the same stabilizing role as the KL penalty used in PPO-based RLHF.

The result is a controlled update that improves preference alignment without drifting too far from the base model.

## Results

DPO achieves comparable or better alignment performance than PPO-based methods on several benchmarks, with fewer training instabilities and lower computational cost.

The paper shows that much of the complexity of RLHF was not strictly necessary.

## Impact

DPO quickly became popular in the open-source community due to its simplicity and accessibility. It enabled smaller teams to experiment with alignment techniques that were previously difficult to implement correctly.

Many later methods build directly on the DPO formulation.

## Modern perspective

While more recent approaches extend or modify the basic DPO objective, the core idea remains influential. Preference optimization is now often treated as a supervised learning problem rather than a reinforcement learning one.

DPO helped demystify alignment by showing that simpler objectives can work well in practice.

## Notes

This paper is best read immediately after InstructGPT. Together, they clarify which parts of RLHF are essential and which are implementation artifacts.
