# Language Model Pre-Training

> The pre-training objectives and architectures that create foundation language models — masked language modeling (BERT), causal language modeling (GPT), encoder-decoder (T5), and why the field converged on decoder-only autoregressive models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[self-supervised-learning]] — pre-training IS self-supervised learning; MLM and CLM are SSL objectives applied to text; the pre-training revolution in NLP parallels SSL's impact in vision
- [[scaling-laws]] — pre-training efficiency is governed by Chinchilla scaling laws; the compute-optimal balance between model size and training tokens determines the pre-training recipe
- [[transfer-learning]] — pre-training creates the foundation model that transfer learning adapts; the quality of pre-training determines the ceiling for downstream fine-tuning
- [[tokenization]] — the tokenizer is chosen before pre-training and cannot be changed after; vocabulary size and tokenization algorithm directly affect pre-training efficiency
- [[data-engineering]] — pre-training data quality is arguably the most important factor; data filtering, deduplication, and domain mixing dominate pre-training engineering effort
- [[distributed-training]] — pre-training frontier models requires thousands of GPUs running for weeks; parallelism strategies and training stability are critical engineering challenges
- [[attention-and-transformers]] — the Transformer is the universal architecture for language model pre-training; architectural choices (GQA, RoPE, SwiGLU) are pre-training decisions
- [[large-language-models]] — pre-trained models become LLMs after alignment; the capabilities (and limitations) of LLMs are largely determined during pre-training
- [[autoregressive-models]] — causal language modeling IS autoregressive modeling applied to text; the factorization $P(x) = \prod P(x_i | x_{<i})$ is the mathematical foundation
