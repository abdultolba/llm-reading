# The Illustrated Transformer (2018)

**Author:** Jay Alammar  
**Link:** https://jalammar.github.io/illustrated-transformer/

## Why this piece matters

This is not a research paper, but it has probably done more than any single
resource to make the Transformer architecture understandable.

The value here is intuition. It explains attention, multi-head attention, and
the encoder–decoder structure visually and step by step, without assuming prior
familiarity with sequence models or linear algebra details.

For many people, this is the point where the Transformer actually “clicks.”

---

## Core ideas

### Attention as weighted information flow

The article frames attention as a way for each token to selectively pull
information from other tokens. Queries, keys, and values are presented as
learned projections that determine:

- what a token is looking for
- what other tokens offer
- what information gets passed forward

This framing makes it easier to reason about attention as a routing mechanism
rather than a black box.

---

### Multi-head attention

Multi-head attention is explained as parallel attention operations that focus on
different types of relationships at the same time. Each head operates in a
different subspace, allowing the model to capture multiple patterns
simultaneously.

This visual explanation is often clearer than the formal definition in the
original paper.

---

### Encoder–decoder flow

The encoder stack is presented as a repeated block that refines representations
through self-attention and feed-forward layers.

The decoder is shown as:

- masked self-attention over generated tokens
- cross-attention into encoder outputs
- a final projection to vocabulary logits

This makes the separation of concerns between encoding and generation explicit.

---

### Positional information

Because attention alone has no notion of order, the article clearly motivates
why positional encodings are necessary and how they are added to token
embeddings before attention is applied.

---

## What this clarifies that papers often don’t

- Why attention scales well with parallel hardware
- How information mixes across tokens layer by layer
- What multi-head attention actually buys you in practice
- How masking changes behavior during decoding

This is especially useful before reading implementation code or newer papers
that assume Transformer familiarity.

---

## Modern perspective

While the architecture shown is encoder–decoder and uses sinusoidal positional
encodings, the mental model transfers cleanly to:

- decoder-only LLMs
- rotary or learned positional embeddings
- sparse and optimized attention variants

Even in 2025, this remains one of the best on-ramps to the Transformer.

---

## Notes

- Worth revisiting after reading later papers; details land differently once
  you’ve seen scaling laws and modern architectures.
- Pairs well with reading the original Transformer paper immediately after.
