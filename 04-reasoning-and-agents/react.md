# ReAct: Synergizing Reasoning and Acting in Language Models (2023)

**Authors:** Shunyu Yao et al.  
**Link:** https://arxiv.org/abs/2210.03629

## Why this paper matters

ReAct introduced a simple but powerful pattern for building agentic systems with language models. It showed that interleaving reasoning steps with actions and observations leads to better performance than treating reasoning and acting as separate phases.

This work helped establish the idea that language models can function as controllers within larger systems.

## Core ideas

### Interleaving thought and action

ReAct prompts the model to alternate between reasoning steps and explicit actions. Each action interacts with an external environment or tool, and the resulting observation is fed back into the model.

This tight loop allows reasoning to be grounded in external feedback.

### Text as a control interface

Actions are represented as structured text, making it easy to integrate tools without modifying the model. The same language model generates reasoning, selects actions, and interprets observations.

This approach avoids specialized architectures and keeps the system flexible.

### Improved interpretability and robustness

By exposing reasoning and actions explicitly, ReAct makes it easier to debug agent behavior. Errors can often be traced to specific reasoning steps or incorrect tool calls.

The approach also reduces hallucination by forcing the model to consult external sources.

## Results

ReAct improves performance on tasks such as question answering, interactive decision making, and multi-step problem solving. The gains are particularly strong in settings where external information or tools are required.

The paper demonstrates that reasoning traces and tool use reinforce each other.

## Impact

ReAct influenced a large body of work on agents, tool use, and autonomous systems. Many later frameworks adopt similar patterns, even when they do not explicitly cite the paper.

The idea of combining reasoning traces with environment interaction became a core design principle.

## Modern perspective

While modern agent systems often add memory, planning, or learned policies, the ReAct pattern remains recognizable. It provides a minimal template for turning a language model into an interactive system.

Understanding ReAct helps clarify how agentic behavior emerges from prompting rather than new model capabilities.

## Notes

This paper pairs naturally with chain-of-thought prompting. Together, they show how reasoning can guide both internal computation and external action.
