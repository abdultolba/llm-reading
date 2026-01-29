# Toolformer: Language Models Can Teach Themselves to Use Tools (2023)

**Authors:** Timo Schick et al.  
**Link:** https://arxiv.org/abs/2302.04761

## Why this paper matters

Toolformer showed that language models can learn to use external tools without direct human supervision. Instead of relying on manually curated tool-use datasets, the model generates its own training data by deciding when tool calls are useful and learning from the results.

This work reframed tool use as a self-supervised capability rather than a hand-engineered feature.

## Core ideas

### Self-supervised tool invocation

The model is given access to a set of tools, such as a calculator or search API, and learns when to invoke them by inserting tool calls into text. If using the tool improves the likelihood of the continuation, the tool call is retained as training data.

This allows the model to bootstrap tool use from raw text.

### Tools as text transformations

Tool calls and outputs are represented as text. This keeps the interface simple and allows standard language models to interact with tools without architectural changes.

The approach aligns closely with later agent frameworks that treat tools as part of the prompt.

### Learning when not to use tools

An important contribution is that the model learns to avoid unnecessary tool calls. Tool use is selective and context-dependent rather than reflexive.

This makes the behavior more efficient and natural.

## Results

Toolformer improves performance on tasks that benefit from external computation or retrieval, such as arithmetic and factual queries. The gains are achieved without degrading performance on tasks that do not require tools.

The paper demonstrates that tool use can be integrated without sacrificing general language ability.

## Impact

This work influenced later approaches to tool use, agents, and function calling. Many modern systems adopt similar ideas, even when they rely on supervised data or reinforcement learning rather than self-supervision.

Toolformer helped establish tool use as a core capability of language models.

## Modern perspective

While most production systems today use supervised or reinforced tool-use training, the core insight remains relevant. Models can learn when tools are helpful by observing their effect on prediction quality.

The paper connects naturally to ReAct and later agentic systems.

## Notes

This paper is best read as a conceptual demonstration rather than a complete system design. Its main contribution is showing that tool use does not require heavy human annotation.
