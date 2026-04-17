# Long-Context and Memory Architectures

> Extending Transformer context beyond standard limits — from positional encoding extrapolation to architectural innovations (Infini-attention, RETRO, landmark attention, memory tokens) that enable processing hundreds of thousands to millions of tokens.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[positional-encoding]] — RoPE extension (position interpolation, YaRN) is the foundation for context length extrapolation; ALiBi provides natural length generalization
- [[efficient-attention-variants]] — Flash Attention, GQA, sparse attention, and KV-cache compression are the engineering prerequisites for long context; without them, long context is computationally infeasible
- [[state-space-models]] — SSMs offer $O(n)$ alternative to attention for long sequences; hybrid SSM-attention architectures combine the strengths of both
- [[retrieval-augmented-generation]] — RAG and long context are complementary approaches to accessing large knowledge bases; the optimal choice depends on document size, query volume, and cost constraints
- [[inference-optimization]] — KV-cache management (PagedAttention, quantization, token dropping) directly enables longer context at fixed memory budgets
- [[distributed-training]] — ring attention and sequence parallelism distribute long sequences across devices; training on 1M+ tokens requires distributed sequence processing
- [[attention-and-transformers]] — long context challenges fundamental properties of attention: the quadratic cost, the softmax distribution spreading over more tokens, and the "lost in the middle" phenomenon
- [[scaling-laws]] — context length may follow its own scaling laws; the relationship between context length, model size, and downstream performance is not yet fully characterized
