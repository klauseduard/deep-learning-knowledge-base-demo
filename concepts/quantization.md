# Quantization

> Reducing the numerical precision of neural network weights and activations — from FP32/FP16 to INT8/INT4 and below — to shrink model size, reduce memory bandwidth, and accelerate inference, with methods ranging from post-training quantization (GPTQ, AWQ) to quantization-aware training.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[inference-optimization]] — quantization is the most impactful single technique for efficient inference; it directly reduces memory bandwidth (the primary bottleneck) and enables running larger models on smaller hardware
- [[gpu-and-accelerator-hardware]] — hardware precision support determines what quantization is practical; the progression FP32→FP16→INT8→FP8→FP4 in NVIDIA GPUs directly enables lower-precision deployment
- [[model-deployment]] — quantization is the first step in the deployment pipeline; GGUF for CPU, GPTQ for GPU, Core ML for Apple devices each have their own quantization formats
- [[training-techniques]] — QLoRA combines quantization with LoRA for memory-efficient fine-tuning; mixed precision training is quantization applied to the training process
- [[knowledge-distillation]] — distillation and quantization are complementary compression techniques; distill to a smaller model, then quantize it for maximum compression
- [[large-language-models]] — quantization is what makes local LLM inference possible; the hobbyist community runs 70B models on consumer hardware entirely because of INT4 quantization
- [[distributed-training]] — quantized communication (gradient compression) reduces inter-GPU bandwidth in distributed training; ZeRO and FSDP can use quantized optimizer states
- [[information-theory]] — quantization is lossy compression; the rate-distortion trade-off from information theory provides the theoretical framework for understanding quantization quality
