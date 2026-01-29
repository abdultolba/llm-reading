# Scaling Laws for Neural Language Models (2020)

**Authors:** Jared Kaplan, Sam McCandlish, Tom Henighan, Tom B. Brown, Benjamin Chess, Rewon Child, Scott Gray, Alec Radford, Jeffrey Wu, Dario Amodei  
**Link:** https://arxiv.org/abs/2001.08361

## Why this paper matters

This paper provided the first clean empirical framework for understanding how language model performance scales with model size, dataset size, and training compute. It turned what had been a vague intuition into quantitative laws and made it possible to reason about tradeoffs before training massive models.

More than any architectural change, these results shaped how organizations planned large-scale training runs over the next several years.

## Core ideas

### Power-law scaling

The central finding is that loss scales as a smooth power law with respect to model parameters, dataset size, and compute, over many orders of magnitude. There are no sharp phase transitions in loss itself; improvements are predictable if resources are allocated correctly.

This regularity suggested that larger models would continue to improve as long as scaling trends held.

### Compute-optimal training

Given a fixed compute budget, there is an optimal balance between model size and dataset size. Training models that are too large on too little data is inefficient, as is training small models on massive datasets.

At the time, most large language models were significantly overparameterized relative to their training data.

### Early saturation of capabilities

The paper observes that some downstream metrics saturate earlier than others, even while loss continues to improve. This hinted that raw loss is not always a perfect proxy for task performance, especially for reasoning or structured tasks.

## Methodology

The authors trained hundreds of models across a wide range of sizes and datasets, holding architecture and optimization details largely constant. This controlled setup made it possible to isolate scaling effects from other variables.

This approach later became standard practice for large-scale empirical work.

## Impact

Scaling laws changed how teams approached model development. Instead of treating training runs as bespoke experiments, they could be planned analytically. This reduced wasted compute and encouraged systematic scaling rather than ad hoc growth.

The results also reinforced the idea that architecture improvements alone would not replace the benefits of scale.

## Modern perspective

Later work, most notably Chinchilla, revised the compute-optimal frontier and showed that many models trained under these assumptions were undertrained on data. However, the basic power-law insight has held up remarkably well.

Most current scaling strategies still trace back to this framework, even when incorporating sparsity, mixture-of-experts, or improved data quality.

## Notes

This paper pairs closely with the GPT-3 paper and is best read immediately before Chinchilla. It explains why early large models worked at all and why they worked less efficiently than they could have.
