# Model Merging and Editing

> Combining independently trained models without retraining (task arithmetic, TIES, model soups) and surgically modifying specific knowledge in model weights (ROME, MEMIT) — post-training techniques for composing capabilities and correcting errors.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[loss-landscape-geometry]] — linear mode connectivity and flat minima are the theoretical foundation for why model merging works; merging only succeeds when models are in the same loss basin
- [[transfer-learning]] — task arithmetic is a form of transfer (applying task vectors to new base models); LoRA and full fine-tuning produce the task vectors that merging combines
- [[training-techniques]] — model merging is an alternative to multi-task fine-tuning; it achieves similar results without joint training
- [[continual-learning]] — knowledge editing is a form of continual learning (adding new knowledge without forgetting); MEMIT addresses the forgetting problem through constrained optimization
- [[interpretability]] — ROME's causal tracing reveals where facts are stored (MLP layers as key-value memories), a core interpretability finding; knowledge editing validates mechanistic understanding
- [[large-language-models]] — model merging is widely used in the open-source LLM community; top leaderboard models are often merges
- [[scaling-laws]] — can model merging substitute for training compute? If merging multiple specialized 7B models produces a better result than training a single 14B model, this changes the compute-optimal strategy
- [[knowledge-distillation]] — an alternative to merging for combining model capabilities; distillation works across architectures while merging requires shared architecture
