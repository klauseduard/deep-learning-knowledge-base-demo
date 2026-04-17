# Embeddings and Representation Learning

> Learning dense vector representations that capture semantic relationships — from word2vec's word embeddings through sentence transformers to CLIP's multimodal representations, forming the foundation for retrieval, similarity search, and transfer learning.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[self-supervised-learning]] — contrastive learning (SimCLR, MoCo, CLIP) is the primary method for training embedding models; masked language modeling (BERT) also produces embeddings
- [[attention-and-transformers]] — Transformers are the backbone of all modern embedding models; BERT, sentence transformers, and CLIP all use Transformer encoders
- [[multimodal-models]] — CLIP, SigLIP, and ImageBind create shared embedding spaces across modalities; multimodal retrieval depends on aligned embeddings
- [[information-theory]] — InfoNCE loss is a lower bound on mutual information; the information bottleneck principle explains what makes good representations
- [[large-language-models]] — RAG systems depend on embedding quality for retrieval; LLM hidden states are embeddings; in-context learning operates on embedded representations
- [[loss-functions]] — contrastive loss, triplet loss, and cosine similarity loss are the core training objectives for embedding models
- [[autoencoders]] — VAE latent spaces are learned embeddings; VQ-VAE provides discrete embeddings; autoencoder reconstruction encourages information preservation
- [[knowledge-distillation]] — smaller embedding models are often distilled from larger ones; embedding distillation preserves similarity structure while reducing dimensions
