# Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet (2024)

**Authors:** Templeton et al.  
**Link:** https://transformer-circuits.pub/2024/scaling-monosemanticity/

## Why this paper matters

This work represents a major advance in mechanistic interpretability. It provides evidence that as language models scale, a growing fraction of their internal features become monosemantic, meaning they correspond to single, human-interpretable concepts rather than tangled mixtures.

The paper moves interpretability from anecdotal examples toward systematic measurement.

## Core ideas

### Feature extraction at scale

The authors apply sparse autoencoders to internal activations of a large language model in order to extract features that are more interpretable than raw neuron activations. These features often correspond to concrete concepts such as entities, syntactic roles, or abstract ideas.

This approach treats interpretability as a representation learning problem.

### Monosemanticity increases with scale

Larger models exhibit a higher proportion of monosemantic features. As model size grows, features become cleaner and more disentangled, making internal structure easier to analyze rather than harder.

This runs counter to the intuition that scale necessarily leads to inscrutability.

### Circuits and composition

Interpretable features can be composed into small computational circuits that implement recognizable behaviors. This suggests that high-level model behavior can be decomposed into structured internal mechanisms.

The work builds a bridge between feature-level analysis and functional understanding.

## Results

The paper demonstrates millions of interpretable features extracted from a single model and shows consistent patterns across layers and components. Many features activate selectively and predictably across diverse contexts.

These results provide concrete evidence that large models contain discoverable internal structure.

## Impact

This work significantly raised expectations for what mechanistic interpretability can achieve. It suggested that understanding large language models in detail may be tractable, given the right tools and scale.

The results also support broader claims about representation convergence at scale.

## Modern perspective

Mechanistic interpretability has since expanded on these methods, applying them to other models and architectures. Sparse feature extraction is now a core technique in the field.

This paper is often cited as a turning point from exploratory interpretability toward systematic analysis.

## Notes

This paper benefits from slow reading and hands-on exploration of the accompanying visualizations. It pairs naturally with the Platonic Representation Hypothesis and earlier work on feature disentanglement.
