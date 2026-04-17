# Reasoning in LLMs

> How large language models perform multi-step reasoning — from chain-of-thought prompting to dedicated reasoning models (o1, R1) trained with reinforcement learning, process reward models, and the emerging paradigm of test-time compute scaling.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[prompt-engineering-and-in-context-learning]] — CoT, self-consistency, and ToT are prompting techniques that elicit reasoning; reasoning models internalize these patterns through RL training
- [[reinforcement-learning]] — RL (PPO, GRPO, DPO) is the primary training method for reasoning models; reward from verifiable answers replaces human preference labels
- [[scaling-laws]] — test-time compute scaling introduces a second scaling axis alongside training compute; the interaction between these axes is not yet characterized
- [[ai-safety-and-alignment]] — reasoning models raise new safety concerns: hidden reasoning may contain deceptive intent; process reward models could enable better oversight; faithful reasoning is a prerequisite for trustworthy AI
- [[interpretability]] — understanding whether reasoning traces reflect actual model computation is a core interpretability question; mechanistic analysis of reasoning circuits is a frontier research area
- [[knowledge-distillation]] — reasoning capabilities can be distilled from large reasoning models to small ones via trace-based training
- [[inference-optimization]] — reasoning models have variable-length generation, complicating batching and cost estimation; speculative decoding and efficient generation are critical
- [[agents-and-tool-use]] — reasoning models improve agent reliability by enabling more careful planning before action; ReAct combines reasoning with tool use in agent loops
