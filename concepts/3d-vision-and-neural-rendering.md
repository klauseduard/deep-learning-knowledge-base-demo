# 3D Vision and Neural Rendering

> Methods for reconstructing, representing, and rendering 3D scenes from 2D observations — from classical point cloud networks (PointNet) to neural implicit representations (NeRF) to explicit Gaussian primitives (3D Gaussian Splatting), plus diffusion-based 3D generation.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] -- CNNs provide the backbone for many 3D vision models (feature extraction for point clouds, image encoders for multi-view reconstruction). The U-Net architecture appears in many multi-view diffusion models.
- [[diffusion-models]] -- Score Distillation Sampling repurposes 2D diffusion models for 3D generation. Multi-view diffusion models generate consistent views for 3D reconstruction.
- [[attention-and-transformers]] -- Point Transformers apply self-attention to point clouds. Large Reconstruction Models (LRM) use transformers for feed-forward 3D reconstruction. Vision transformers extract features for multi-view systems.
- [[object-detection]] -- 3D object detection for autonomous driving extends 2D detection to predict 3D bounding boxes from point clouds or camera images.
- [[self-supervised-learning]] -- CLIP and DINO features embedded in 3D representations (LERF, feature-enriched Gaussians) enable open-vocabulary 3D understanding.
- [[multimodal-models]] -- Text-to-3D generation connects language understanding with 3D scene creation. 3D-aware multimodal models (3D-LLMs) reason about spatial relationships.
- [[generative-adversarial-networks]] -- Early 3D-aware generative models (EG3D, pi-GAN) used GAN architectures with neural rendering.
- [[autoencoders]] -- VAE latent spaces are used in latent 3D diffusion models. VQ-VAE variants encode 3D shapes for discrete generation.
- [[gpu-and-accelerator-hardware]] -- 3DGS's real-time performance depends critically on GPU rasterization capabilities and custom CUDA kernels. The tile-based rendering aligns with GPU tile-based architectures.
- [[inference-optimization]] -- Gaussian compression (quantization, pruning) mirrors techniques from LLM inference optimization. Real-time rendering requires similar hardware-aware engineering.
