# Knowledge Distillation

> A training technique where a small "student" model learns to mimic a large "teacher" model's behavior — transferring knowledge from a high-capacity network into a compact, deployable one.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[training-techniques]] — distillation is a training technique for model compression and capability transfer; related to fine-tuning and transfer learning
- [[large-language-models]] — many smaller LLMs (Alpaca, Orca, Phi) are distilled from larger ones; distillation is central to the open-source LLM ecosystem
- [[diffusion-models]] — progressive and consistency distillation compress iterative diffusion into fast 1-step generators
- [[loss-functions]] — the distillation loss combines KL divergence (soft labels) with cross-entropy (hard labels)
- [[inference-optimization]] — distillation is a complementary technique to quantization and pruning for efficient deployment
- [[mixture-of-experts]] — MoE models can be distilled into smaller dense models for deployment
- [[scaling-laws]] — distillation effectively transfers the benefits of scale into smaller models
