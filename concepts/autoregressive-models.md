# Autoregressive Models

> Models that factorize the joint probability of a sequence into a product of conditional distributions, generating one token at a time from left to right. The dominant paradigm behind GPT, LLaMA, and most modern language models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — The transformer decoder with causal self-attention is the standard architecture for autoregressive language models.
- [[large-language-models]] — LLMs like GPT-3, LLaMA, and Claude are autoregressive transformers scaled to hundreds of billions of parameters.
- [[loss-functions]] — Autoregressive training uses cross-entropy loss between predicted and actual next-token distributions.
- [[scaling-laws]] — The power-law relationship between compute/data/parameters and loss was discovered in the context of autoregressive language models.
- [[diffusion-models]] — An alternative generative paradigm that models continuous data through iterative denoising rather than sequential token prediction.
