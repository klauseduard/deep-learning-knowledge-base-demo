# Hardware-Software Co-Design

> The tight coupling between deep learning algorithms and hardware — custom GPU kernels (Triton, CUDA), compiler optimization (TVM, XLA), kernel fusion, operator design for specific hardware (tensor cores, sparsity units), and the feedback loop between architecture innovation and hardware capabilities.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gpu-and-accelerator-hardware]] — this article explains how software exploits the hardware capabilities described there; the memory hierarchy, tensor cores, and sparsity units are the targets for co-design
- [[efficient-attention-variants]] — Flash Attention is the canonical co-design example; its speedup comes entirely from hardware-aware implementation, not mathematical innovation
- [[inference-optimization]] — inference serving (vLLM, TensorRT, llama.cpp) heavily relies on fused kernels, quantization-hardware alignment, and memory management
- [[quantization]] — quantization is only useful when the target precision is hardware-accelerated; INT4 quantization + INT4 tensor cores = actual speedup
- [[neural-network-compression]] — 2:4 structured sparsity is designed for hardware acceleration; unstructured sparsity has limited hardware support
- [[distributed-training]] — communication optimization (overlap compute with communication, NCCL tuning, NVLink utilization) is a key co-design concern
- [[scaling-laws]] — co-design determines the actual compute efficiency that scaling laws assume; better utilization shifts the effective compute per dollar
