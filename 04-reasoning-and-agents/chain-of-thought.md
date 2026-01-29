# Chain-of-Thought Prompting Elicits Reasoning in Large Language Models (2022)

**Authors:** Jason Wei et al.  
**Link:** https://arxiv.org/abs/2201.11903

## Why this paper matters

This paper showed that large language models can perform substantially better on multi-step reasoning tasks when encouraged to produce intermediate reasoning steps. Rather than training new architectures or objectives, the authors demonstrated that reasoning behavior can be elicited through prompting alone.

Chain-of-thought prompting reframed reasoning as a controllable behavior rather than an inherent capability that models either have or lack.

## Core ideas

### Reasoning via intermediate steps

By including explicit reasoning traces in prompts, the model is guided to break problems into smaller steps before producing an answer. This improves performance on arithmetic, symbolic reasoning, and logic tasks.

The effect grows stronger with model scale.

### Scale dependence

Smaller models do not benefit reliably from chain-of-thought prompting. The paper shows that the ability to follow and generate reasoning traces emerges only at sufficient scale.

This reinforced the idea that reasoning is an emergent property of large models rather than a feature that can be trained directly in small ones.

### Prompting as computation

The paper implicitly treats prompting as a form of programming. The structure of the prompt defines a computation the model learns to emulate, with the reasoning steps acting as scratch space.

This perspective influenced later work on tool use and agents.

## Results

Chain-of-thought prompting produces large gains on benchmarks like GSM8K and MultiArith when applied to sufficiently large models. The improvements often exceed those obtained by fine-tuning alone.

The paper also highlights that providing only the final answer is less effective than including the full reasoning process.

## Impact

This work triggered a wave of research into reasoning-focused prompting, training, and evaluation. It influenced instruction tuning datasets, reasoning benchmarks, and later reinforcement learning approaches aimed at improving structured reasoning.

The idea of exposing intermediate reasoning became central to how people interact with LLMs.

## Modern perspective

Later work has explored whether explicit reasoning traces are always necessary or whether they can be internalized. However, chain-of-thought prompting remains a reliable way to improve reasoning performance in practice.

The paper also raised important questions about faithfulness and whether generated reasoning reflects the model’s true internal process.

## Notes

This paper is best read alongside ReAct and later reasoning-focused training work. It provides the conceptual starting point for treating reasoning as an interface rather than a hidden mechanism.
