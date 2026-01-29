# Training Compute-Optimal Large Language Models (Chinchilla, 2022)

**Authors:** Jordan Hoffmann et al.  
**Link:** https://arxiv.org/abs/2203.15556

## Why this paper matters

This paper revised the prevailing understanding of how to scale language models efficiently. It showed that many large models, including GPT-3, were significantly undertrained on data relative to their parameter count. For a fixed compute budget, using more tokens and fewer parameters leads to better performance.

Chinchilla shifted the field away from parameter-centric scaling and toward data-centric scaling.

## Core ideas

### Revised compute-optimal frontier

The paper derives new empirical scaling relationships showing that optimal training requires model size and dataset size to grow together, roughly in proportion. In contrast to earlier practice, optimal models should see far more tokens than had been typical.

Under this regime, doubling compute should be spent roughly equally on increasing parameters and increasing data.

### Tokens matter more than parameters

One of the most impactful takeaways is that, at fixed compute, smaller models trained on more data outperform larger models trained on fewer tokens. This reframed performance gains as a data efficiency problem rather than purely a modeling problem.

This insight directly influenced later model families and training strategies.

### Controlled experimental design

The authors trained a family of models with consistent architecture and optimization settings while varying size and token count. This made it possible to isolate the effect of data scaling without confounding architectural changes.

The resulting trends were clean and reproducible.

## Results

Chinchilla, a 70B-parameter model trained on significantly more data than GPT-3, outperformed larger models on a wide range of benchmarks despite having fewer parameters.

This demonstrated that better compute allocation could deliver large gains without increasing inference cost.

## Impact

After this paper, training regimes changed across the industry. Models were trained longer, datasets were expanded aggressively, and data curation became a first-class concern.

The results also influenced open-weight models, where inference efficiency and training cost are tightly constrained.

## Modern perspective

While later work has explored deviations from dense scaling through sparsity and mixture-of-experts, the Chinchilla result remains a baseline reference. Even sparse models are now evaluated in terms of effective token exposure per parameter.

The paper also foreshadowed the importance of high-quality synthetic data as a way to scale tokens without relying entirely on raw web text.

## Notes

This paper is best read immediately after the original scaling laws paper. Together, they explain why early large models worked, why they were inefficient, and how later systems improved without simply growing larger.
