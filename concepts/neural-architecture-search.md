# Neural Architecture Search

> Automated methods for designing neural network architectures — replacing human intuition with search algorithms that explore the space of possible architectures to find optimal designs for a given task and hardware constraint.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — NAS was originally applied to CNN design; EfficientNet and NASNet are CNN architectures
- [[attention-and-transformers]] — AutoFormer and similar methods apply NAS to Transformer design spaces
- [[scaling-laws]] — compound scaling (EfficientNet) is a form of scaling law for architecture parameters
- [[reinforcement-learning]] — the original NAS used RL to train an architecture controller
- [[gradient-descent]] — DARTS uses gradient-based optimization for architecture search
- [[inference-optimization]] — hardware-aware NAS directly optimizes for deployment constraints (latency, memory, energy)
- [[knowledge-distillation]] — NAS-discovered small models can be further improved via distillation from larger teachers
