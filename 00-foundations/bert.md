# BERT: Pre-training of Deep Bidirectional Transformers (2018)

**Authors:** Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova  
**Link:** https://arxiv.org/abs/1810.04805

## Why this paper matters

BERT established pre-training as the default way to build strong language
representations. More importantly, it showed that **deep bidirectionality**
changes what a Transformer can learn.

Before BERT, most language models were either left-to-right or shallowly
bidirectional. BERT demonstrated that training on full left-and-right context
produces representations that transfer far better to downstream tasks.

Even though modern LLMs are usually decoder-only, many core ideas in BERT still
shape how models are trained, evaluated, and adapted.

---

## Core ideas

### Bidirectional encoder pre-training

BERT uses a Transformer **encoder stack** trained to model context on both sides
of every token. This contrasts with autoregressive models, which only see past
tokens during training.

The result is token representations that encode richer syntactic and semantic
information.

---

### Masked Language Modeling (MLM)

Instead of predicting the next token, BERT randomly masks a subset of input
tokens and trains the model to predict them.

This forces the model to:

- rely on both left and right context
- build internal representations rather than memorizing surface patterns

MLM trades off generative capability for representational quality.

---

### Next Sentence Prediction (NSP)

BERT includes an auxiliary objective that predicts whether two sentences appear
consecutively in the source text.

While later work questioned its necessity, NSP influenced how sentence-level
tasks and classification heads were designed in early Transformer systems.

---

## Architecture and training

- Standard Transformer encoder layers
- Learned positional embeddings
- Large-scale pre-training on BooksCorpus and Wikipedia
- Fine-tuning with minimal task-specific changes

The fine-tuning paradigm was one of BERT’s biggest practical contributions.
A single pre-trained model could be adapted to many tasks with small labeled
datasets.

---

## Results and impact

BERT achieved large improvements across NLP benchmarks at the time, including
question answering, sentence classification, and natural language inference.

Its release shifted the field toward:

- universal pre-trained backbones
- benchmark-driven evaluation
- separating representation learning from task-specific modeling

---

## Modern perspective

Most frontier LLMs no longer use MLM or encoder-only architectures.
However, BERT’s influence remains visible in:

- representation-focused objectives
- contrastive and denoising pre-training
- embedding models and rerankers
- retrieval and classification systems paired with generative models

Understanding BERT helps clarify what decoder-only models give up and what they
gain.

---

## Notes

- Encoder-only models excel at understanding tasks but do not generate text
  naturally.
- Many later ideas around data efficiency and task transfer build directly on
  this work.
