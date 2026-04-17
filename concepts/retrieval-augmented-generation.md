# Retrieval-Augmented Generation (RAG)

> Grounding LLM generation in retrieved external knowledge — chunking strategies, embedding-based retrieval, reranking, advanced RAG patterns (CRAG, self-RAG, graph RAG), and production pipeline design.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[embeddings-and-representation-learning]] — embedding models power the retrieval component; embedding quality directly determines retrieval quality; MTEB benchmarks measure retrieval capability
- [[large-language-models]] — the generation component; RAG augments LLM capabilities with external knowledge; context window size determines how much retrieved content can be used
- [[agents-and-tool-use]] — agentic RAG combines retrieval with reasoning; agents use RAG as a tool alongside web search, code execution, etc.
- [[inference-optimization]] — RAG adds latency (retrieval + reranking + longer prompts); optimizing the retrieval pipeline is crucial for production deployments
- [[prompt-engineering-and-in-context-learning]] — RAG fundamentally relies on in-context learning — retrieved documents are presented as context that the model learns from at inference time
- [[transfer-learning]] — RAG is an alternative to fine-tuning for domain adaptation; for many use cases, RAG with a general model outperforms a fine-tuned model without retrieval
- [[synthetic-data-generation]] — synthetic data can augment RAG knowledge bases; LLMs can generate question-answer pairs for RAG evaluation
- [[tokenization]] — chunk size in tokens depends on tokenizer; different tokenizers produce different chunk boundaries for the same text
