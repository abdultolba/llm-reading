# Textbooks Are All You Need (2023)

**Authors:** Gunasekar et al.  
**Link:** https://arxiv.org/abs/2306.11644

## Why this paper matters

This paper showed that data quality can substitute for raw scale. By training on carefully curated, textbook-like synthetic data, relatively small models can outperform much larger models trained on noisy web corpora.

The results challenged the assumption that ever-larger datasets are always necessary for strong performance.

## Core ideas

### High-quality synthetic data

The paper constructs datasets designed to resemble textbooks: clear explanations, structured progression of concepts, and minimal noise. This contrasts with typical pretraining corpora that prioritize size over coherence.

The model benefits from seeing well-organized information rather than sheer volume.

### Curriculum effects

Because the data is structured, the model effectively follows a curriculum during training. Concepts are introduced in a logical order, which improves sample efficiency and generalization.

This mirrors ideas from human learning and classical curriculum learning.

### Smaller models, stronger performance

When trained on textbook-style data, smaller models match or exceed the performance of much larger baselines on reasoning and knowledge tasks. This suggests that many models are limited more by data quality than by parameter count.

## Results

The paper reports significant gains on reasoning-heavy benchmarks and shows improved training efficiency. Models converge faster and require fewer tokens to reach strong performance.

These gains hold even when total compute is substantially reduced.

## Impact

This work renewed interest in data curation, filtering, and synthetic data generation. It also influenced approaches that use large models to generate high-quality training data for smaller ones.

The paper reframed scaling as a joint problem of model size and data quality.

## Modern perspective

Many recent training pipelines incorporate synthetic or curated data inspired by this work. While scale remains important, the idea that structure and clarity matter has become more widely accepted.

The paper complements Chinchilla by showing that not all tokens are equally valuable.

## Notes

This paper is best read alongside work on synthetic data generation and curriculum learning. It provides a concrete example of how training data choices shape model behavior.
