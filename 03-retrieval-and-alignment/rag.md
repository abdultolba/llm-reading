# Retrieval-Augmented Generation (2020)

**Authors:** Patrick Lewis et al.  
**Link:** https://arxiv.org/abs/2005.11401

## Why this paper matters

This paper formalized the idea that parametric language models do not need to store all knowledge internally. By pairing generation with retrieval over an external corpus, models can access up-to-date or domain-specific information without retraining.

Retrieval-augmented generation became a foundational pattern for building practical and trustworthy language systems, especially in settings where factual accuracy matters.

## Core ideas

### Separating knowledge from reasoning

The key conceptual move is to decouple knowledge storage from language generation. Instead of forcing the model to memorize facts during training, relevant documents are retrieved at inference time and provided as context.

This allows smaller models to perform competitively on knowledge-intensive tasks.

### Differentiable retrieval

The paper uses a dense retriever trained jointly with the generator. Retrieved documents are treated as latent variables, and generation marginalizes over multiple retrieved passages.

This framing allows retrieval and generation to be optimized together rather than as separate components.

### Sequence-to-sequence generation with context

The generator conditions on both the input query and the retrieved documents. Attention mechanisms allow the model to flexibly combine information across sources when producing an answer.

This makes the system robust to partial or noisy retrieval results.

## Results

RAG models outperform purely parametric models on open-domain question answering benchmarks. They also show improved factual consistency compared to models that rely solely on internal representations.

The paper demonstrates that retrieval can compensate for smaller model size when the task is knowledge-heavy.

## Impact

RAG became the conceptual basis for many production systems that combine LLMs with search, databases, or private document collections. While modern implementations often simplify the original training setup, the core idea remains unchanged.

The paper also influenced later work on tool use, memory-augmented models, and hybrid neural-symbolic systems.

## Modern perspective

Most real-world RAG systems today use frozen generators and off-the-shelf retrievers rather than fully joint training. Despite this, the original formulation remains useful for understanding the design space.

RAG reframed language models as components in larger systems rather than self-contained solutions.

## Notes

This paper is best read as a systems concept rather than a recipe. The most important takeaway is the architectural separation it introduced, not the specific training procedure.
