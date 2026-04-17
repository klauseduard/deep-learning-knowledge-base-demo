# NLP Tasks

> The core downstream tasks of natural language processing — named entity recognition, machine translation, text summarization, question answering, sentiment analysis — and how the paradigm shifted from task-specific architectures to unified language models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[language-model-pretraining]] — pre-training (BERT, GPT, T5) created the foundation models that handle all NLP tasks; the pre-training objective determines which tasks the model handles naturally
- [[large-language-models]] — LLMs subsume most NLP tasks via prompting; the task-specific era is giving way to general-purpose models
- [[prompt-engineering-and-in-context-learning]] — the interface between LLMs and NLP tasks; prompt design determines how well an LLM performs on each task
- [[retrieval-augmented-generation]] — open-domain QA and knowledge-intensive tasks are now typically solved via RAG rather than storing everything in model parameters
- [[embeddings-and-representation-learning]] — sentence embeddings power semantic search, document clustering, and similarity-based NLP tasks
- [[attention-and-transformers]] — the Transformer was designed for MT (seq2seq) and became the universal NLP architecture; self-attention replaced recurrence for all NLP tasks
- [[tokenization]] — subword tokenization determines how models process text; multilingual tokenization quality limits cross-lingual NLP
- [[transfer-learning]] — fine-tuning pre-trained models for specific NLP tasks is the dominant paradigm; PEFT methods (LoRA) make this efficient
