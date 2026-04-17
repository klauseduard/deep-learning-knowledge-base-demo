# Few-Shot and Zero-Shot Learning

> Learning from minimal examples — metric-based few-shot methods (prototypical networks, matching networks), optimization-based (MAML), zero-shot transfer via CLIP and language descriptions, in-context learning as implicit few-shot, and the convergence of few-shot learning with foundation model capabilities.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[meta-learning]] — MAML, prototypical networks, and episodic training are the meta-learning foundations of few-shot; this article focuses on the methods while meta-learning covers the broader paradigm
- [[self-supervised-learning]] — CLIP's contrastive pre-training enables zero-shot; DINOv2, MAE features provide strong few-shot representations; self-supervised pre-training is increasingly the best few-shot feature extractor
- [[prompt-engineering-and-in-context-learning]] — in-context learning IS few-shot learning via the prompt; prompt engineering techniques (CoT, few-shot examples) directly map to the few-shot paradigm
- [[embeddings-and-representation-learning]] — metric-based few-shot methods operate in embedding space; the quality of the embedding determines few-shot performance; CLIP embeddings enable zero-shot via text-image alignment
- [[energy-based-models-and-contrastive-learning]] — CLIP's InfoNCE training directly applies contrastive learning theory; temperature, negative sampling, and alignment-uniformity principles from contrastive learning shape zero-shot quality
- [[transfer-learning]] — foundation model + linear probe is a few-shot approach that uses transfer learning; the feature quality from pre-training determines few-shot adaptability
- [[large-language-models]] — LLMs exhibit emergent few-shot abilities through in-context learning; GPT-3 demonstrated that scale alone creates few-shot capability without dedicated architecture
