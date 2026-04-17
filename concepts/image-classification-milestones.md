# Image Classification Milestones

> The architectural evolution from LeNet to Vision Transformers — each milestone solving a key problem and reshaping the field: LeNet (convolutions work), AlexNet (GPUs + depth), VGG (simplicity of 3×3), GoogLeNet (multi-scale), ResNet (skip connections), EfficientNet (compound scaling), and ViT (attention replaces convolution).

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — the dominant architecture family from LeNet through EfficientNet; ViT challenged the assumption that convolutions are necessary for vision
- [[activation-functions]] — ReLU (AlexNet) enabled deep training; GELU appears in ViT and modern models
- [[regularization]] — dropout (AlexNet), batch norm (Inception v2/ResNet), data augmentation (all models), and stochastic depth (DeiT)
- [[normalization-techniques]] — batch norm made ResNet trainable; layer norm is used in ViT/Swin; the shift from BN to LN mirrors the shift from CNNs to Transformers
- [[skip-connections]] — ResNet's residual connections are the single most reused innovation; appear in every subsequent architecture
- [[attention-and-transformers]] — ViT applied Transformers directly to vision; Swin combined attention with CNN-like hierarchy; squeeze-and-excitation (EfficientNet) is channel attention
- [[neural-architecture-search]] — EfficientNet's base architecture was found by NAS; MnasNet demonstrated mobile NAS
- [[self-supervised-learning]] — MAE, DINO, and BEiT showed that ViTs benefit enormously from SSL pre-training; DeiT used distillation as an alternative
- [[scaling-laws]] — ViT's performance scales predictably with data and model size; compound scaling (EfficientNet) formalized the depth-width-resolution relationship
- [[object-detection]] and [[semantic-segmentation]] — classification backbones are the feature extractors for detection (Faster R-CNN, DETR) and segmentation (FCN, DeepLab, SAM)
