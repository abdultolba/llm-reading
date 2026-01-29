# LLaMA: Open and Efficient Foundation Language Models (2023)

**Authors:** Hugo Touvron et al.  
**Link:** https://arxiv.org/abs/2302.13971

## Why this paper matters

LLaMA marked a turning point for open-weight language models. It showed that careful architecture choices, better data curation, and compute-optimal training could produce models that rival much larger closed systems while remaining practical to run.

More quietly, LLaMA standardized a set of architectural defaults that now appear across most modern LLMs.

## Core ideas

### Efficiency-first design

Rather than chasing scale alone, LLaMA focuses on extracting the most performance per parameter. The models are trained using Chinchilla-style scaling, with significantly more tokens per parameter than earlier systems.

This emphasis on efficiency made smaller models surprisingly capable and larger ones more economical.

### Decoder-only Transformer with modern defaults

LLaMA uses a standard decoder-only Transformer but incorporates several design choices that later became common practice: RMSNorm instead of LayerNorm, SwiGLU activations in feed-forward layers, and rotary position embeddings.

Individually these changes are modest, but together they improve training stability and performance.

### High-quality training data

A major contribution of the paper is its attention to data composition. LLaMA relies on a filtered and deduplicated corpus with a higher proportion of high-quality text relative to raw web data.

This reinforced the idea that data quality can substitute for brute-force scale.

## Results

Across a range of benchmarks, LLaMA models often match or outperform much larger models trained with earlier recipes. The results demonstrate that strong performance does not require extreme parameter counts if training is done carefully.

The smaller variants in particular became popular as general-purpose backbones for downstream fine-tuning.

## Impact

LLaMA triggered a rapid expansion of the open LLM ecosystem. Many subsequent models adopted its architecture almost wholesale, treating it as a baseline rather than a research contribution.

It also accelerated experimentation by lowering the barrier to entry for researchers and practitioners.

## Modern perspective

Most current open-weight models can be understood as variations on the LLaMA recipe, with changes in data, scale, sparsity, or post-training. Even many closed models appear to follow similar architectural conventions.

Understanding LLaMA provides a practical reference point for what a strong, efficient dense Transformer looks like today.

## Notes

This paper connects the abstract results of scaling laws and Chinchilla to concrete architectural and training decisions. It is a useful reference when evaluating claims about efficiency or data quality in later models.
