# Continual Learning

> Training neural networks on a sequence of tasks without forgetting previous ones — addressing catastrophic forgetting through regularization (EWC), architectural methods (progressive networks), and replay-based approaches, enabling models that accumulate knowledge over time.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — catastrophic forgetting is fundamentally a property of gradient-based optimization; the gradient for the current task doesn't preserve past task solutions
- [[regularization]] — EWC and SI add regularization terms that protect important weights; all regularization-based CL methods modify the loss
- [[knowledge-distillation]] — LwF and DER++ use distillation to preserve old task knowledge; soft labels from old models serve as "memory"
- [[generalization-theory]] — continual learning relates to plasticity-stability trade-off; flat minima ([[loss-landscape-geometry]]) may be more robust to forgetting
- [[training-techniques]] — LoRA adapters reduce forgetting by constraining the update space; pre-training provides robust initializations for sequential learning
- [[large-language-models]] — in-context learning sidesteps forgetting; RAG externalizes knowledge; continual pre-training is a practical CL challenge
- [[meta-learning]] — meta-continual learning learns to learn sequentially; MAML-style initializations may resist forgetting
- [[reinforcement-learning]] — experience replay in RL (DQN's replay buffer) directly inspired CL replay methods
