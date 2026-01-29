# The Smol Training Playbook (2025)

**Authors:** Hugging Face  
**Link:** https://huggingface.co/docs/trl/smol

## Why this resource matters

This playbook distills several years of hard-won lessons about training language models efficiently. Rather than focusing on frontier-scale systems, it emphasizes how to get strong results with limited compute, smaller models, and practical engineering choices.

It serves as a bridge between research papers and real-world training workflows.

## Core ideas

### Small models, strong baselines

The playbook emphasizes that many failures attributed to model size are actually due to weak baselines or poor training setups. With careful choices around data, optimization, and evaluation, relatively small models can perform surprisingly well.

This reframes training as an optimization problem rather than a scale problem.

### End-to-end perspective

Rather than isolating pretraining, fine-tuning, or alignment, the playbook treats the full lifecycle as a single pipeline. Decisions made early, such as data filtering or tokenizer choice, propagate downstream and shape final performance.

This holistic view mirrors how production systems are built.

### Practical alignment techniques

The playbook provides concrete guidance on instruction tuning, preference optimization, and lightweight alignment methods that do not require complex reinforcement learning setups. These techniques make alignment accessible to smaller teams.

The focus is on reliability and debuggability rather than novelty.

## Results and guidance

While not a benchmark paper, the playbook offers empirical guidance backed by experiments and community experience. It highlights common failure modes and provides defaults that work well across a range of settings.

Many of the recommendations align closely with findings from Chinchilla, DPO, and synthetic data work.

## Impact

This resource helped standardize training practices in the open-source ecosystem. It lowered the barrier to entry for training and aligning models and reduced reliance on brittle, ad hoc experimentation.

The playbook also reinforced the idea that good engineering choices compound.

## Modern perspective

As models and tooling continue to evolve, the specific recipes will change, but the principles remain stable. Efficiency, data quality, and careful evaluation matter at every scale.

The Smol Training Playbook captures these principles in a form that is immediately usable.

## Notes

This is a practical reference rather than a theoretical work. It is best used alongside the papers in this repository as a guide for turning ideas into working systems.
