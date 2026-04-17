# Diffusion Models

> Generative models that learn to reverse a gradual noising process, transforming pure Gaussian noise into structured data like images, audio, and video through iterative denoising.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — The U-Net architecture used in most diffusion models is built from convolutional layers with skip connections.
- [[attention-and-transformers]] — Attention layers are used within the U-Net, and DiT replaces the entire U-Net with a transformer. Text conditioning uses transformer-based CLIP encoders.
- [[large-language-models]] — Multimodal models combine LLMs with diffusion decoders for text-to-image generation. LLMs can orchestrate diffusion models via tool use.
- [[loss-functions]] — The diffusion training objective is a weighted MSE between predicted and actual noise, derived from the variational lower bound.
- [[autoregressive-models]] — An alternative generative paradigm; autoregressive models factorize the joint distribution sequentially, while diffusion models use iterative refinement over all dimensions simultaneously.
- [[video-understanding-and-generation]] — Video generation (Sora, Veo, Kling) applies the diffusion framework to spacetime latent patches using DiT backbones, extending latent diffusion from images to video.
