# Object Detection

> Locating and classifying multiple objects within an image — predicting both *what* objects are present and *where* they are — from the two-stage R-CNN family to single-shot YOLO and the Transformer-based DETR.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — CNN backbones (ResNet, CSPDarknet) extract features; detection was the driving application for deeper CNNs and multi-scale features
- [[attention-and-transformers]] — DETR applies Transformers to detection; Swin Transformer serves as a detection backbone; deformable attention was invented for detection
- [[skip-connections]] — FPN uses top-down skip connections for multi-scale features; ResNet backbones rely on residual connections
- [[loss-functions]] — detection uses a combination of classification loss (cross-entropy/focal loss), regression loss (smooth L1/GIoU), and matching loss (Hungarian for DETR)
- [[self-supervised-learning]] — pre-trained backbones (ImageNet, MAE, DINO) significantly improve detection performance
- [[knowledge-distillation]] — distilling large detectors into smaller ones for edge deployment
- [[inference-optimization]] — real-time detection requires quantization, pruning, and TensorRT optimization for deployment
