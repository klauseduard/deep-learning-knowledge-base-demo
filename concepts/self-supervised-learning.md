# Self-Supervised Learning

> A training paradigm where the model learns representations by solving pretext tasks derived from the data itself — no human labels required — enabling pre-training on vast unlabeled datasets.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[autoregressive-models]] — next-token prediction is the most successful SSL method for language
- [[large-language-models]] — LLM pre-training is fundamentally a self-supervised learning procedure
- [[attention-and-transformers]] — BERT, ViT/MAE, and GPT are all Transformer architectures trained with different SSL objectives
- [[loss-functions]] — contrastive loss, masked prediction loss, and reconstruction loss are all SSL training objectives
- [[training-techniques]] — the pre-train/fine-tune paradigm depends on SSL for the pre-training phase
- [[autoencoders]] — denoising autoencoders and MAE are closely related; VQ-VAE provides discrete targets for BEiT
- [[convolutional-neural-networks]] — SimCLR and MoCo typically use ResNet backbones
