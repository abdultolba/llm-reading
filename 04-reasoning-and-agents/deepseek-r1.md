# DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (2025)

**Authors:** Guo et al.  
**Link:** https://arxiv.org/abs/2501.12948

## Why this paper matters

This paper showed that large language models can develop strong, structured reasoning behavior through reinforcement learning alone, without supervised chain-of-thought data. It provided concrete evidence that reasoning can be incentivized directly at scale rather than injected through curated examples.

DeepSeek-R1 marked a shift from eliciting reasoning to actively training for it.

## Core ideas

### Reinforcement learning without supervised reasoning traces

The model is trained using reinforcement learning signals derived from task success rather than human-written reasoning demonstrations. Correct outcomes are rewarded, and incorrect ones are penalized, allowing the model to discover effective reasoning strategies on its own.

This avoids reliance on expensive or brittle chain-of-thought datasets.

### Self-verification and correction

During training, the model learns to generate intermediate reasoning steps that help it verify its own answers. These steps are not explicitly labeled but emerge as a useful internal tool for maximizing reward.

The resulting behavior resembles deliberate multi-step reasoning rather than shallow pattern matching.

### Scaling reinforcement learning

The paper demonstrates that reinforcement learning can be applied effectively at large scale when combined with strong base models and carefully designed reward signals. This counters the earlier view that RL is too unstable or inefficient for training frontier language models.

## Results

DeepSeek-R1 shows large gains on mathematical reasoning and logic benchmarks compared to instruction-tuned baselines. The improvements are most pronounced on tasks requiring long reasoning chains and self-consistency.

The model also exhibits improved robustness to prompt variation.

## Impact

This work influenced later research on reasoning-focused post-training and reinforced the idea that reasoning is a trainable capability rather than a fixed emergent property. It also helped legitimize reinforcement learning as a viable tool for shaping internal model behavior at scale.

## Modern perspective

Later models combine ideas from chain-of-thought prompting, preference optimization, and reinforcement learning. DeepSeek-R1 is notable for showing that explicit reasoning supervision is not strictly necessary if the training signal rewards correct outcomes.

The paper sits at the boundary between alignment work and capability training.

## Notes

This paper is best read after chain-of-thought and ReAct. It closes the loop by showing how reasoning behavior can be internalized rather than prompted.
