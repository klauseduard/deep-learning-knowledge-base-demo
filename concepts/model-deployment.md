# Model Deployment

> The engineering of taking trained models from research to production — model formats (ONNX, TorchScript), runtime optimization (TensorRT, Core ML), serving infrastructure (Triton, vLLM), edge deployment, and the MLOps lifecycle that keeps deployed models reliable.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[inference-optimization]] — the algorithmic optimizations (KV-cache, Flash Attention, speculative decoding, quantization) that deployment infrastructure builds upon
- [[knowledge-distillation]] — the primary technique for creating smaller, deployment-friendly models from large teachers
- [[neural-architecture-search]] — hardware-aware NAS designs models optimized for specific deployment targets (mobile latency, edge memory)
- [[gpu-and-accelerator-hardware]] — the target hardware determines which optimizations are effective; Tensor Cores, Neural Engines, and NPUs shape the deployment stack
- [[distributed-training]] — model parallelism techniques (tensor parallelism, pipeline parallelism) reappear in distributed serving for large models
- [[large-language-models]] — LLM serving is the most demanding deployment challenge; autoregressive generation, massive KV-caches, and long contexts require specialized infrastructure
- [[training-techniques]] — quantization-aware training, LoRA adapters, and model merging all affect what gets deployed and how
