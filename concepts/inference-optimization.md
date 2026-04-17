# Inference Optimization

> Techniques that make running trained models fast and memory-efficient — from KV-cache management and quantization to speculative decoding and specialized serving systems — essential for deploying LLMs at scale.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[large-language-models]] — inference optimization is what makes LLM deployment economically viable
- [[attention-and-transformers]] — Flash Attention, GQA, and KV-cache all optimize the attention mechanism
- [[state-space-models]] — SSMs avoid the KV-cache bottleneck entirely with their fixed-size state
- [[distributed-training]] — tensor parallelism techniques are shared between training and inference
- [[training-techniques]] — quantization-aware training bridges training and inference optimization
- [[tensors]] — quantization changes tensor data types; memory layout affects kernel efficiency
