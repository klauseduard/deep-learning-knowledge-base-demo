# 3D Generation Deep Dive

> Advanced 3D content creation from neural fields — NeRF variants (Instant-NGP, Zip-NeRF), 3D Gaussian Splatting optimization, text-to-3D (DreamFusion, Score Distillation), feed-forward 3D generation, and the path toward 4D dynamic scene synthesis.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[3d-vision-and-neural-rendering]] — this article deepens the generation side; NeRF/3DGS reconstruction techniques are the foundation upon which text-to-3D builds
- [[diffusion-models]] — SDS repurposes 2D diffusion models as 3D priors; VSD trains an additional diffusion model; multi-view diffusion generates consistent views
- [[text-to-image-generation]] — text-to-3D pipelines build directly on text-to-image models (Stable Diffusion, Imagen); classifier-free guidance and LoRA techniques transfer
- [[gpu-and-accelerator-hardware]] — 3DGS's real-time rendering exploits GPU rasterization; NeRF's ray marching is memory-bandwidth-limited; hardware determines which representation is practical
- [[self-supervised-learning]] — feed-forward 3D models (LRM, LGM) are trained on rendered multi-view images from 3D datasets, using reconstruction as a self-supervised objective
- [[video-understanding-and-generation]] — 4D generation connects to video generation; temporal consistency in 4D parallels frame coherence in video; video diffusion models may serve as 4D priors
