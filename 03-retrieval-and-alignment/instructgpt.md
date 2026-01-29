# Training Language Models to Follow Instructions with Human Feedback (InstructGPT, 2022)

**Authors:** Long Ouyang et al.  
**Link:** https://arxiv.org/abs/2203.02155

## Why this paper matters

This paper defined the modern post-training pipeline for large language models. It showed that models trained purely for next-token prediction are not well aligned with human intent, and that relatively small amounts of human feedback can dramatically change model behavior.

InstructGPT demonstrated that alignment and usability are not automatic consequences of scale. They must be trained explicitly.

## Core ideas

### Instruction tuning

The first step is supervised fine-tuning on a dataset of human-written prompts and ideal responses. This shifts the model from generic language modeling toward following explicit instructions.

Even before reinforcement learning, this step produces large gains in helpfulness and task adherence.

### Reward modeling

Human annotators rank multiple model outputs for the same prompt. These rankings are used to train a reward model that predicts human preference.

This converts qualitative human judgments into a learnable objective that can be optimized at scale.

### Reinforcement learning from human feedback

The base model is optimized against the reward model using reinforcement learning, specifically PPO. The objective balances maximizing reward with staying close to the original model to avoid degradation.

This step sharpens helpfulness, politeness, and safety-related behavior.

## Results

InstructGPT models are consistently preferred by human evaluators over much larger base models trained only with next-token prediction. In some cases, a 1.3B aligned model outperforms a 175B unaligned model in terms of user preference.

This result reframed progress in LLMs as a product of training procedure, not just scale.

## Impact

The InstructGPT pipeline became the standard approach for deploying LLMs. Variants of this process are now used across instruction-tuned models, chat assistants, and aligned open-weight systems.

It also motivated a large body of work focused on simplifying, stabilizing, or replacing PPO-based alignment.

## Modern perspective

While later methods reduce reliance on reinforcement learning, the conceptual structure introduced here remains intact. Most alignment techniques still involve some combination of supervised instruction data, preference modeling, and optimization toward human judgments.

Understanding InstructGPT is essential for interpreting the behavior of modern chat models.

## Notes

This paper pairs naturally with Direct Preference Optimization, which rethinks how preference data is incorporated without explicit reinforcement learning.
