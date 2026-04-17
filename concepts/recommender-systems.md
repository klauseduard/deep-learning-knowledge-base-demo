# Recommender Systems

> Deep learning for personalized recommendations — from matrix factorization to neural collaborative filtering, two-tower retrieval models, sequential recommendation (SASRec, BERT4Rec), and the emerging role of LLMs in recommendation.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[embeddings-and-representation-learning]] — user and item embeddings are the core representations; ANN search over embeddings powers retrieval; embedding table design is the primary engineering challenge
- [[attention-and-transformers]] — SASRec and BERT4Rec apply Transformer attention to sequential recommendation; DIN uses attention over user history for ranking
- [[autoregressive-models]] — sequential recommendation is next-item prediction, directly paralleling autoregressive language modeling
- [[energy-based-models-and-contrastive-learning]] — contrastive losses (in-batch negatives) are standard for training two-tower models; the InfoNCE framework applies directly
- [[large-language-models]] — LLMs as recommendation engines (ranking, conversational rec) and as feature extractors; world knowledge complements collaborative signal
- [[retrieval-augmented-generation]] — the two-stage retrieve-then-rank pattern mirrors RAG's retrieve-then-generate; ANN search is shared infrastructure
- [[inference-optimization]] — serving recommendations at millions of QPS requires extreme optimization: embedding table sharding, model quantization, caching, and efficient ANN search
- [[fairness-and-bias]] — recommendation algorithms can amplify societal biases; fairness-aware ranking is an active area connecting to broader AI fairness
