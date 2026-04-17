# Efficient Attention Variants

> Modifications to standard Transformer attention that reduce the $O(n^2)$ computational and memory cost — sparse attention, linear attention, Flash Attention, multi-query/grouped-query attention, and sliding window approaches for long-context models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — all efficient variants modify the standard attention mechanism defined here
- [[inference-optimization]] — Flash Attention, GQA, KV-cache compression are core inference optimizations
- [[gpu-and-accelerator-hardware]] — Flash Attention is designed around the GPU memory hierarchy (SRAM vs. HBM); hardware determines which optimizations matter
- [[state-space-models]] — SSMs offer $O(n)$ sequence processing as an alternative to efficient attention; hybrid models combine both
- [[large-language-models]] — long-context LLMs (Gemini 1M, Claude 200K) depend on efficient attention for practical operation
- [[distributed-training]] — sequence parallelism and ring attention distribute the attention computation across devices
- [[positional-encoding]] — RoPE and ALiBi are designed with efficient attention in mind (RoPE works naturally with Flash Attention; ALiBi enables extrapolation with sliding windows)
- [[scaling-laws]] — context length scaling and its compute costs are determined by attention efficiency
