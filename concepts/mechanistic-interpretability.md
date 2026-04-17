# Mechanistic Interpretability

> Reverse-engineering neural network computations into human-understandable circuits — superposition, sparse autoencoders for feature extraction, activation patching, induction heads, and the path from toy models to frontier LLMs.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[interpretability]] — mechanistic interpretability is a specific approach within the broader interpretability field; this article provides depth on circuits, superposition, and SAEs
- [[ai-safety-and-alignment]] — mechanistic understanding could provide safety guarantees that behavioral testing cannot; detecting deceptive features, verifying alignment properties
- [[attention-and-transformers]] — the residual stream framework and circuit analysis are specific to the Transformer architecture; attention head roles (induction, name mover) are architectural discoveries
- [[model-merging-and-editing]] — ROME's causal tracing is a mechanistic interpretability technique applied to knowledge editing; locating factual knowledge in MLPs validates the MLP-as-memory hypothesis
- [[self-supervised-learning]] — mechanistic interpretability reveals what pre-training objectives actually teach; induction heads emerge during pre-training as a specific capability
- [[large-language-models]] — the primary target for mech interp; understanding how LLMs implement in-context learning, factual recall, and reasoning
- [[adversarial-robustness]] — understanding internal representations may explain why adversarial examples exist and how to defend against them
- [[embeddings-and-representation-learning]] — the linear representation hypothesis connects mech interp to representation geometry; SAE features are learned representations
