# Language Models are Few-Shot Learners (GPT-3, 2020)

**Authors:** Tom B. Brown et al.  
**Link:** https://arxiv.org/abs/2005.14165

## Why this paper matters

This paper marked a shift in how language models are used. Instead of training or fine-tuning models for each task, it showed that sufficiently large models can adapt to new tasks directly from text prompts.

The key contribution was not a new architecture, but evidence that **scale alone** unlocks new behavior. Few-shot and even zero-shot performance became viable simply by increasing model size and data.

This changed how people thought about prompting, evaluation, and deployment.

---

## Core ideas

### Autoregressive scaling

GPT-3 is a standard decoder-only Transformer trained with a next-token prediction objective. The novelty lies in its scale:

- up to 175 billion parameters
- massive and diverse training data
- no task-specific fine-tuning

The paper shows that performance follows smooth power-law trends as model size increases.

---

### In-context learning

The most important empirical finding is **in-context learning**.

By placing examples directly in the prompt, the model learns to infer the task and apply it to new inputs without gradient updates.

This behavior was not explicitly trained for and was weak or absent in smaller models.

---

### Prompting as an interface

Tasks are expressed as natural language instructions and examples rather than specialized input formats.

This reframes the model as a general-purpose text processor, with prompting serving as the control mechanism.

---

## Results

GPT-3 achieved competitive or state-of-the-art results across a wide range of
tasks:

- translation
- question answering
- cloze tasks
- basic reasoning benchmarks

Performance improved consistently with scale, particularly in the few-shot setting.

---

## Limitations discussed in the paper

- Models were inefficiently trained relative to later scaling laws
- Performance was brittle and prompt-sensitive
- Reasoning ability was shallow and inconsistent
- Outputs reflected biases present in training data

These limitations motivated much of the work that followed.

---

## Impact

This paper influenced:

- the rise of prompt engineering
- API-based model access rather than model distribution
- the view of LLMs as task-agnostic systems
- later work on instruction tuning and alignment

It also made clear that evaluation needed to account for prompting, not just model weights.

---

## Modern perspective

Later work showed that GPT-3-style models were undertrained for their size and could be made far more efficient with better compute allocation.

Nevertheless, this paper established the basic operating model for modern LLMs: large autoregressive Transformers controlled through text.

---

## Notes

- The architecture itself is straightforward; the behavior comes from scale.
- This paper pairs naturally with scaling laws and Chinchilla.
- Many later alignment and reasoning techniques can be seen as ways to stabilize and sharpen in-context learning.
