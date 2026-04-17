# Text-to-Image Generation

> Generating images from text descriptions using diffusion models — the Stable Diffusion pipeline in detail, DALL-E, classifier-free guidance, ControlNet, IP-Adapter, and the engineering behind turning text prompts into high-quality images.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[diffusion-models]] — text-to-image is the primary application of diffusion; the denoising process, noise schedules, and sampling algorithms from the diffusion article are directly used here
- [[autoencoders]] — the VAE encoder/decoder that compresses images to/from latent space; VQ-VAE discrete codes inspired early text-to-image approaches
- [[attention-and-transformers]] — cross-attention connects text to image features; DiT replaces U-Net with a plain Transformer; the trend is toward Transformer-only architectures
- [[embeddings-and-representation-learning]] — CLIP embeddings provide the text-image alignment; CLIP score evaluates generation quality; IP-Adapter uses CLIP image embeddings for image conditioning
- [[self-supervised-learning]] — CLIP's contrastive pre-training enables zero-shot text-image alignment; the text encoder learns to embed prompts in a space aligned with visual semantics
- [[training-techniques]] — LoRA enables efficient fine-tuning; DreamBooth and Textual Inversion personalize models; classifier-free guidance is a training-time technique that enables inference-time control
- [[semantic-segmentation]] — U-Net architecture originated in segmentation; ControlNet uses segmentation maps as conditioning; SAM can provide masks for inpainting
- [[data-engineering]] — LAION-5B data quality directly affects model quality; synthetic recaptioning (DALL-E 3) shows data quality > quantity; copyright concerns drive data curation decisions
- [[scaling-laws]] — DiT architectures scale predictably with compute; the shift from U-Net to DiT is motivated by Transformer scaling properties
