# Data Engineering for ML

> The practices and systems for collecting, curating, labeling, augmenting, and managing the data that neural networks learn from — the often-underappreciated foundation on which model quality rests.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[scaling-laws]] — performance scales as a power law with data quantity, but data quality and mixture can shift the scaling curve significantly
- [[self-supervised-learning]] — SSL reduces labeling needs by learning from unlabeled data; data augmentation policies define SSL invariances
- [[large-language-models]] — pre-training data curation (filtering, mixing, deduplication) is a major determinant of LLM capabilities
- [[knowledge-distillation]] — synthetic data generation (Alpaca, Orca) is a form of distillation where the teacher generates training examples
- [[regularization]] — data augmentation is a form of regularization; MixUp and CutMix have theoretical regularization interpretations
- [[federated-learning]] — addresses data governance when centralization is impossible
- [[training-techniques]] — pre-training/fine-tuning paradigm depends on having appropriate data at each stage; RLHF requires human preference data
- [[generalization-theory]] — data quality and diversity directly affect generalization; duplicate data promotes memorization over generalization
