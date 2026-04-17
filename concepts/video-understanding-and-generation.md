# Video Understanding and Generation

> Deep learning for video — from 3D CNNs and Video Transformers that recognize actions, to diffusion transformers that generate photorealistic video from text, plus video-language models that reason about temporal content.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[diffusion-models]] — Video generation models are direct extensions of image diffusion, using the same noise-denoise framework but applied to spacetime latent patches rather than 2D image latents
- [[attention-and-transformers]] — Video Transformers (TimeSformer, ViViT) apply attention to video, and the DiT backbone of Sora/Veo is a transformer; factorized spacetime attention is a key design choice
- [[convolutional-neural-networks]] — 3D CNNs (C3D, I3D, SlowFast) extend 2D convolutions to the temporal dimension; ResNet/Inception backbones were inflated for video understanding
- [[multimodal-models]] — Video-language models (Video-LLaVA, Gemini) are multimodal models that incorporate video as a modality alongside text; any-to-any models generate video from text
- [[self-supervised-learning]] — VideoMAE applies masked autoencoding to video with extreme (90–95%) masking ratios, exploiting video's temporal redundancy
- [[autoencoders]] — Spatial-temporal VAEs compress video into latent spaces for efficient diffusion; VQ-VAE-based tokenization is used in autoregressive video models
- [[scaling-laws]] — Sora's technical report showed that video generation quality scales predictably with compute, extending image generation scaling laws to video
- [[large-language-models]] — Text conditioning for video generation often uses LLM-derived text encoders (T5); video-language models use LLMs as the reasoning backbone
- [[object-detection]] — Video object detection and tracking extend spatial detection to the temporal domain; SAM 2 extends segmentation to video
