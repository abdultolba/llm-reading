# LLMs, Transformers, and Reasoning Systems

This repository is a curated collection of papers for understanding how modern large language models are built, trained, and pushed toward reasoning and tool-using behavior.

The focus is on continuity. How the original Transformer led to current architectures, why scaling laws shaped training practice, how Mixture-of-Experts became viable, and how reasoning and alignment emerged as first-class concerns.

The papers are grouped by theme and roughly ordered in the sequence that makes the most sense to read them.

---

## How I Use This Repository

Each folder corresponds to a layer of the modern LLM stack.

For each paper, I keep short notes on:

- the core idea
- the technical contribution
- what persisted into later systems
- where the approach shows limits

The intent is to build intuition over time rather than to summarize every section of every paper.

---

## Organization and Reading Flow

### 00 — Foundations

The original Transformer and the ideas that replaced recurrent models.

- [Attention Is All You Need](00-foundations/attention-is-all-you-need.md)
- [The Illustrated Transformer](00-foundations/illustrated-transformer.md)
- [BERT](00-foundations/bert.md)

---

### 01 — Scaling Laws

Why scale works, how compute is allocated, and what changes when data becomes the limiting factor.

- [Language Models are Few-Shot Learners](01-scaling-laws/gpt3-few-shot.md)
- [Scaling Laws for Neural Language Models](01-scaling-laws/kaplan-scaling-laws.md)
- [Training Compute-Optimal Language Models (Chinchilla)](01-scaling-laws/chinchilla.md)

---

### 02 — Core Architectures

Design choices that became defaults across open and closed models.

- [LLaMA](02-architectures/llama.md)
- [RoFormer (Rotary Position Embeddings)](02-architectures/roformer.md)
- [FlashAttention](02-architectures/flashattention.md)

---

### 03 — Retrieval and Alignment

How models are grounded in external information and shaped to follow instructions.

- [Retrieval-Augmented Generation](03-retrieval-and-alignment/rag.md)
- [Training Language Models to Follow Instructions with Human Feedback](03-retrieval-and-alignment/instructgpt.md)
- [Direct Preference Optimization](03-retrieval-and-alignment/dpo.md)

---

### 04 — Reasoning and Agents

Work that made reasoning behavior explicit and connected language models to actions and tools.

- [Chain-of-Thought Prompting](04-reasoning-and-agents/chain-of-thought.md)
- [ReAct](04-reasoning-and-agents/react.md)
- [DeepSeek-R1](04-reasoning-and-agents/deepseek-r1.md)
- [Qwen3 Technical Report](04-reasoning-and-agents/qwen3.md)
- [Agentic Design Patterns](https://drive.google.com/file/d/1-5ho2aSZ-z0FcW8W_jMUoFSQ5hTKvJ43/view) (needs notes)

---

### 05 — Mixture-of-Experts

Conditional computation as a response to the limits of dense scaling.

- [Outrageously Large Neural Networks](05-mixture-of-experts/outrageously-large-nns.md)
- [Switch Transformers](05-mixture-of-experts/switch-transformers.md)
- [GLaM](05-mixture-of-experts/glam.md)
- [Sparse Upcycling](05-mixture-of-experts/sparse-upcycling.md)
- [Mixtral of Experts](05-mixture-of-experts/mixtral.md)

---

### 06 — Representation, Data, and Interpretability

What models internalize, how data quality changes outcomes, and how structure appears at scale.

- [The Platonic Representation Hypothesis](06-representation-and-data/platonic-representations.md)
- [Textbooks Are All You Need](06-representation-and-data/textbooks-are-all-you-need.md)
- [Scaling Monosemanticity](06-representation-and-data/monosemanticity.md)

---

### 07 — Systems and Training

Large-scale training infrastructure and practical training recipes.

- [PaLM](07-systems-and-training/palm.md)
- [The Smol Training Playbook](07-systems-and-training/smol-training-playbook.md)

---

## Bonus and Historical Context

Earlier work that continues to influence current designs.

- [T5](bonus/t5.md)
- [Toolformer](bonus/toolformer.md)
- [GShard](bonus/gshard.md)
- [Adaptive Mixtures of Local Experts](bonus/adaptive-moe.md)
- [Hierarchical Mixtures of Experts](bonus/hierarchical-moe.md)

---

## Motivation

As models have grown, the interesting problems have shifted. Scaling alone is no longer the whole story.

Reasoning behavior, sparsity, data quality, and post-training now drive most of the visible gains.

Reading these papers in isolation makes it easy to miss how tightly connected those ideas are. This collection is an attempt to keep those connections visible.

---

## Status

This is a living set of notes. Some papers are covered more deeply than others, and interpretations will change as newer results appear.

---

## License

Notes in this repository are released under the MIT license.  
The original papers remain the property of their respective authors.
