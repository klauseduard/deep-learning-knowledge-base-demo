# Meta-Learning

> Learning to learn — algorithms that improve their learning ability from experience across tasks, enabling fast adaptation from few examples through learned initializations, metric spaces, or explicit learning algorithms.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[large-language-models]] — in-context learning is implicit meta-learning; Transformers trained on diverse data become general-purpose few-shot learners without explicit episodic training
- [[gradient-descent]] — MAML meta-learns an initialization for gradient descent; the inner loop *is* gradient descent, the outer loop optimizes *for* gradient descent
- [[self-supervised-learning]] — contrastive learning (SimCLR, CLIP) creates embedding spaces usable for few-shot classification via nearest-neighbor, paralleling metric-based meta-learning
- [[training-techniques]] — transfer learning (pre-train + fine-tune) is the practical alternative to meta-learning; LoRA enables efficient fine-tuning with limited data
- [[attention-and-transformers]] — Transformers can implement learning algorithms in their forward pass; in-context learning emerges from Transformer pre-training
- [[knowledge-distillation]] — few-shot learners can be distilled from larger models, combining meta-learning with model compression
- [[reinforcement-learning]] — meta-RL learns to learn new environments quickly; MAML was originally demonstrated on RL tasks
