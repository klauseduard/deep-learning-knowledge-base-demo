# Distributed Training

> Techniques for splitting the computational workload of training neural networks across multiple GPUs and machines — essential for training models with billions of parameters that exceed the memory and compute capacity of any single device.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — distributed training is ultimately about parallelizing gradient computation
- [[large-language-models]] — cannot be trained without distributed systems; 3D parallelism is standard
- [[scaling-laws]] — the compute budgets predicted by scaling laws require distributed training to achieve
- [[training-techniques]] — mixed precision, gradient accumulation, and learning rate scaling are tightly coupled with distribution strategy
- [[backpropagation]] — activation checkpointing trades recomputing the forward pass for memory savings during backprop
- [[attention-and-transformers]] — tensor parallelism is designed around the Transformer's matrix multiplications
