# State Space Models

> Linear recurrence architectures that process sequences in linear time by maintaining a fixed-size hidden state — the main architectural challenger to Transformers, combining RNN-like efficiency with Transformer-like parallelism during training.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — SSMs are the primary alternative/complement to attention; Mamba-2 proves a formal duality between them
- [[recurrent-neural-networks]] — SSMs are the modern answer to RNNs' sequential bottleneck, preserving recurrence while enabling parallelism
- [[large-language-models]] — hybrid SSM-Transformer architectures are an emerging alternative for LLM architectures
- [[inference-optimization]] — SSMs' constant-time generation avoids the KV-cache bottleneck entirely
- [[scaling-laws]] — it remains an open question whether SSM scaling laws differ from Transformer scaling laws
