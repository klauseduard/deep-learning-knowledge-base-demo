# Mixture of Experts

> An architecture where only a subset of the model's parameters are active for each input, enabling much larger models without proportionally increasing computation — the key technique behind many frontier LLMs.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — MoE replaces the FFN within Transformer blocks; attention layers are typically kept dense
- [[scaling-laws]] — MoE effectively changes the scaling relationship between compute and capacity
- [[distributed-training]] — expert parallelism is a fourth parallelism dimension alongside data, tensor, and pipeline
- [[state-space-models]] — Jamba combines MoE with Mamba layers
- [[inference-optimization]] — MoE models require all expert weights loaded in memory despite sparse activation
- [[multilayer-perceptrons]] — each expert is a standard MLP/FFN
