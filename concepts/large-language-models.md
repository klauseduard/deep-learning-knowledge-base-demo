# Large Language Models

> Large-scale autoregressive transformers trained on massive text corpora that exhibit broad language understanding, few-shot learning, and generation capabilities — the most impactful AI development of the 2020s.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — The transformer decoder with causal self-attention is the core architecture of all LLMs.
- [[autoregressive-models]] — LLMs are autoregressive: they model $P(x_t | x_{<t})$ and generate text one token at a time.
- [[scaling-laws]] — Power-law scaling relationships guide the design of LLM training runs and predict performance.
- [[training-techniques]] — Pre-training, SFT, RLHF, LoRA, and quantization are all essential to the LLM pipeline.
- [[diffusion-models]] — An alternative generative paradigm; some multimodal models combine LLMs with diffusion for image generation.
- [[loss-functions]] — Cross-entropy loss for pre-training; reward modeling loss and DPO loss for alignment.
