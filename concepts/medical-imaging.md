# Medical Imaging

> Deep learning for clinical image analysis — radiology AI (chest X-ray, CT, mammography), pathology (whole-slide image analysis), retinal screening, FDA-approved models, U-Net in clinical workflows, and the unique challenges of medical data (privacy, class imbalance, domain shift, regulatory requirements).

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[semantic-segmentation]] — U-Net is the dominant medical segmentation architecture; nnU-Net's self-configuring approach is the standard baseline; MedSAM extends SAM to medical images
- [[convolutional-neural-networks]] — CNNs remain the backbone for most medical imaging (DenseNet, ResNet, EfficientNet); 3D CNNs for volumetric data (CT, MRI)
- [[federated-learning]] — the primary solution for training across hospitals without sharing patient data; FL studies show competitive performance with centralized training
- [[self-supervised-learning]] — addresses annotation scarcity; contrastive pre-training and masked image modeling on unlabeled medical images improve downstream performance with limited labels
- [[transfer-learning]] — ImageNet pre-training followed by medical fine-tuning is the default pipeline; domain-specific pre-training (medical foundation models) increasingly preferred
- [[data-augmentation]] — critical for small medical datasets; domain-specific augmentations (elastic deformation for histopathology, intensity jittering for MRI) alongside standard geometric transforms
- [[diffusion-models]] — synthetic medical image generation for data augmentation and privacy-preserving data sharing
- [[bayesian-deep-learning]] — uncertainty quantification is critical for clinical deployment; models should flag uncertain predictions for human review
