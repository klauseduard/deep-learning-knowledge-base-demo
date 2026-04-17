# AI Agents and Tool Use

> LLM-based agents that reason, plan, and take actions by calling external tools — extending language models from passive text generators to autonomous problem-solvers that interact with the world.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[large-language-models]] -- LLMs are the "brain" of modern AI agents; all agent capabilities depend on the underlying model's reasoning and instruction-following abilities
- [[reinforcement-learning]] -- RL provides the theoretical framework for sequential decision-making; RLHF aligns the LLM backbone; reasoning models (o1, R1) use RL to learn planning
- [[attention-and-transformers]] -- The transformer's in-context learning ability (processing tool descriptions and results within the context window) is what makes tool use possible without per-tool fine-tuning
- [[training-techniques]] -- Fine-tuning for function calling, RLHF for instruction following, and RL for reasoning are all essential to making capable agents
- [[autoregressive-models]] -- Agents generate tool calls and reasoning traces autoregressively; the sequential nature of generation maps naturally to sequential action-taking
- [[inference-optimization]] -- Agent workloads involve many sequential LLM calls, making inference latency critical; KV-cache reuse across turns is especially important
- [[scaling-laws]] -- Whether agent capabilities scale predictably with model size, and whether "test-time compute scaling" (more thinking = better results) follows similar laws
