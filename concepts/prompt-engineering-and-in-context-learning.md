# Prompt Engineering and In-Context Learning

> Techniques for eliciting desired behavior from large language models through carefully crafted inputs — chain-of-thought reasoning, few-shot learning, system prompts, structured outputs, and the emerging science of how LLMs learn from context without parameter updates.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[large-language-models]] — ICL is an emergent capability of large-scale autoregressive models; prompt engineering is the primary interface for using LLMs
- [[meta-learning]] — ICL is implicit meta-learning; the pre-training process meta-trains the model across millions of tasks; MAML and ICL may implement similar algorithms (gradient descent)
- [[attention-and-transformers]] — ICL happens through the attention mechanism; induction heads are specific attention patterns that enable in-context pattern matching
- [[agents-and-tool-use]] — ReAct prompting bridges reasoning and action; function calling is structured prompting for tool use; agent loops are iterative prompt engineering
- [[training-techniques]] — RLHF makes models better at following instructions; the quality of instruction-following directly affects prompt engineering effectiveness
- [[ai-safety-and-alignment]] — prompt injection and jailbreaking are adversarial prompt engineering; many-shot jailbreaking exploits ICL for harmful purposes; system prompts are the first line of defense
- [[embeddings-and-representation-learning]] — RAG depends on embedding quality for retrieval; prompt content is itself embedded and processed through the model's representation layers
- [[scaling-laws]] — ICL capability improves with model scale; CoT only works above ~10B parameters; test-time compute scaling (reasoning models) extends scaling laws to inference
