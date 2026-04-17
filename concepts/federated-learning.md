# Federated Learning

> A distributed training paradigm where the model is trained across many devices or institutions without centralizing the data — each participant trains locally and shares only model updates, preserving data privacy.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[distributed-training]] — FL is a special case of distributed training with extreme communication constraints and data heterogeneity
- [[gradient-descent]] — FedAvg is essentially distributed SGD with infrequent communication and local epochs
- [[training-techniques]] — LoRA adapters make federated fine-tuning of LLMs practical by reducing communication cost
- [[knowledge-distillation]] — federated distillation shares predictions instead of weights, decoupling client architectures
- [[regularization]] — differential privacy adds noise that acts as regularization; FedProx's proximal term is a regularizer
- [[large-language-models]] — federated fine-tuning enables privacy-preserving adaptation of LLMs
- [[scaling-laws]] — how FL scales with number of participants, data heterogeneity, and communication rounds is an open research area
