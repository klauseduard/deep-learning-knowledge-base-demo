# GPU and Accelerator Hardware

> The physical compute substrate of deep learning — from NVIDIA GPU architectures and Google TPUs to memory hierarchies, interconnects, and the fundamental bottlenecks that shape how models are trained and served.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[distributed-training]] — hardware interconnects (NVLink, InfiniBand) directly determine which parallelism strategies are viable; memory capacity determines sharding requirements
- [[inference-optimization]] — the memory wall is *the* reason KV-cache management, quantization, and speculative decoding matter; Flash Attention is explicitly designed around the SRAM/HBM hierarchy
- [[training-techniques]] — mixed precision training exists because of hardware Tensor Core capabilities; BF16 was introduced for TPUs
- [[scaling-laws]] — compute-optimal scaling requires understanding the actual FLOPS delivered by hardware (MFU) and the cost per FLOP
- [[large-language-models]] — model size and context length are fundamentally constrained by GPU memory capacity and bandwidth
- [[mixture-of-experts]] — MoE reduces the compute-per-token, changing the arithmetic intensity profile and making expert routing an interconnect problem
- [[attention-and-transformers]] — the attention mechanism's quadratic memory scaling motivated both hardware features (Transformer Engine) and algorithms (Flash Attention)
- [[tensors]] — tensor data types (FP32, BF16, FP8, INT4) are hardware-level concepts that affect every computation
