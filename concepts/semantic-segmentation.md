# Semantic Segmentation

> Classifying every pixel in an image into a semantic category — from fully convolutional networks and U-Net to modern architectures like DeepLab and Segment Anything (SAM), enabling dense scene understanding.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — segmentation encoders are typically pre-trained CNN backbones (ResNet, EfficientNet); FCN is the foundational CNN-to-segmentation adaptation
- [[skip-connections]] — U-Net's concatenative skip connections and FPN's multi-scale features are central to preserving spatial detail; U-Net's architecture also underlies [[diffusion-models]]
- [[attention-and-transformers]] — ViT encoders (SETR, SegFormer), Transformer decoders (Mask2Former, SAM), and cross-attention for prompt-based segmentation
- [[object-detection]] — instance segmentation extends detection with per-object masks (Mask R-CNN); DETR-style set prediction applies to Mask2Former
- [[diffusion-models]] — U-Net architecture originated in segmentation and became the standard denoiser backbone for diffusion
- [[self-supervised-learning]] — SAM's ViT encoder benefits from self-supervised pre-training (MAE, DINO); large-scale SSL enables segmentation foundation models
- [[loss-functions]] — cross-entropy per pixel for semantic segmentation, dice loss for medical imaging, focal loss for class imbalance
