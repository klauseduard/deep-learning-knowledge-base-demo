# Tokenization

> The process of converting raw text into discrete tokens that serve as the atomic units of language models — BPE, WordPiece, SentencePiece, and the trade-offs of vocabulary size and multilingual coverage.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — vocabulary size directly impacts sequence length ($O(n^2)$ attention cost), making tokenization efficiency crucial for long-context models
- [[large-language-models]] — tokenizer choice is foundational to LLM design; GPT, LLaMA, and BERT all use different tokenizers with different trade-offs
- [[positional-encoding]] — context length in *tokens* depends on tokenization; languages with high fertility hit context limits faster
- [[embeddings-and-representation-learning]] — the embedding matrix ($V \times d$) maps tokens to dense vectors; vocabulary size determines its size
- [[scaling-laws]] — token count in scaling laws refers to post-tokenization tokens; tokenizer efficiency directly affects how much "information per token" the model processes
- [[multimodal-models]] — visual and audio tokenizers (VQ-VAE, SoundStream) extend the tokenization concept beyond text
- [[prompt-engineering-and-in-context-learning]] — token counting matters for context window management; prompt engineers must be aware of tokenization artifacts
- [[quantization]] — embedding tables are often quantized separately; large vocabularies increase memory pressure
