# Positional Encoding

> Methods for injecting sequence order information into Transformers, whose self-attention mechanism is inherently permutation-invariant — from sinusoidal and learned absolute encodings to the modern revolution of Rotary Position Embeddings (RoPE) and ALiBi that enable long-context generalization.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — positional encoding is a required component of every Transformer; the choice of encoding method affects attention patterns, training stability, and context length capabilities
- [[recurrent-neural-networks]] — RNNs encode position implicitly through sequential processing; positional encoding is the Transformer's explicit replacement for this implicit ordering
- [[state-space-models]] — SSMs encode position through their recurrence structure; when combined with attention in hybrid models, positional encoding is needed for the attention layers
- [[large-language-models]] — context length is a key LLM capability; RoPE + extension methods (YaRN, NTK scaling) enabled the jump from 2K to 128K+ tokens
- [[scaling-laws]] — longer context enables new capabilities (in-context learning with many examples, document understanding) but increases compute quadratically with attention
- [[inference-optimization]] — longer contexts require more KV-cache memory; position encoding interacts with Flash Attention's implementation and KV-cache compression
- [[text-to-image-generation]] — diffusion transformers use positional encoding for spatial positions in image latents; 2D positional encoding for vision differs from 1D for language
