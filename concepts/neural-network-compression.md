# Neural Network Compression

> Reducing model size and computational cost through pruning (removing unnecessary weights), structured compression, and combined strategies — enabling deployment on resource-constrained devices without proportional quality loss.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[quantization]] — pruning and quantization are complementary compression techniques; combining them multiplicatively reduces model size
- [[knowledge-distillation]] — distillation trains a smaller model from scratch, while pruning reduces an existing model; they can be combined (prune, then distill)
- [[generalization-theory]] — the lottery ticket hypothesis connects to the question of why overparameterized networks work; sparse subnetworks explain what the extra parameters are "for" (exploration during training)
- [[inference-optimization]] — pruning enables faster inference, especially with hardware-supported sparsity patterns (2:4 on NVIDIA GPUs)
- [[gpu-and-accelerator-hardware]] — hardware sparsity support (2:4 on A100/H100) determines which pruning patterns actually accelerate inference
- [[model-deployment]] — compression is essential for edge/mobile deployment; the compression pipeline (prune → quantize → distill → optimize) is core to the deployment workflow
- [[scaling-laws]] — compression changes the effective parameter count; understanding how pruned models relate to dense models of equivalent size is an open scaling question
- [[transfer-learning]] — LoRA is a form of low-rank compression applied to weight updates; pruned models can be fine-tuned with LoRA for efficient adaptation
