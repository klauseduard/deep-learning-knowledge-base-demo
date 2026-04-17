# Knowledge Graphs and Structured Knowledge

> Representing and reasoning over structured knowledge with deep learning — knowledge graph embeddings (TransE, RotatE, ComplEx), KG-enhanced language models, knowledge base completion, neuro-symbolic reasoning, and the interplay between parametric and explicit knowledge.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[graph-neural-networks]] — R-GCN, CompGCN, and NBFNet apply GNN architectures to KG reasoning; message passing over the KG structure captures multi-hop relational patterns
- [[retrieval-augmented-generation]] — Graph RAG retrieves structured KG context instead of flat text chunks; KG-grounded generation reduces hallucination by providing verifiable facts
- [[embeddings-and-representation-learning]] — KG embeddings map entities and relations to vectors; the geometric properties (translation, rotation, reflection) determine which relation patterns can be modeled
- [[large-language-models]] — LLMs store knowledge parametrically in weights; KGs store knowledge explicitly in triples; the integration of both is an active research area
- [[model-merging-and-editing]] — knowledge editing (ROME, MEMIT) surgically modifies parametric knowledge; KGs provide the ground truth for which facts to update
- [[reasoning-in-llms]] — multi-hop reasoning over knowledge connects to KG path reasoning; neuro-symbolic methods combine LLM reasoning with formal logic
- [[nlp-tasks]] — named entity recognition, relation extraction, and entity linking are the NLP tasks that construct and populate KGs from text
