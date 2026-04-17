# Transfer Learning

> Reusing knowledge from a model trained on one task/domain to improve performance on a different task/domain — the paradigm shift from training from scratch to fine-tuning pre-trained models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[self-supervised-learning]] — pre-training objectives (masked LM, contrastive learning, MAE) are the foundation of modern transfer learning
- [[training-techniques]] — fine-tuning strategies (learning rate schedules, warmup, LoRA) are core training techniques
- [[knowledge-distillation]] — an alternative to fine-tuning: transfer knowledge via soft labels rather than weight initialization
- [[meta-learning]] — learning to learn efficiently from few examples; MAML explicitly optimizes for transferability
- [[continual-learning]] — catastrophic forgetting during fine-tuning is the same problem continual learning addresses
- [[large-language-models]] — the pre-train → fine-tune → RLHF pipeline is the standard LLM development workflow
- [[embeddings-and-representation-learning]] — pre-trained representations are what make transfer possible; the quality of learned embeddings determines transfer effectiveness
- [[scaling-laws]] — larger pre-trained models generally transfer better, but with diminishing returns
- [[image-classification-milestones]] — ImageNet pre-training was the first massive success of transfer learning in deep learning
