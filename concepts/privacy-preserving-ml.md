# Privacy-Preserving Machine Learning

> Protecting data privacy during model training and inference — differential privacy (DP-SGD), secure multi-party computation, homomorphic encryption, membership inference attacks, and the fundamental tension between privacy and model utility.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[federated-learning]] — FL is a privacy-preserving architecture (data stays local), but alone doesn't provide formal guarantees; FL + DP (local or central DP) provides stronger privacy; MPC enables secure aggregation in FL
- [[fairness-and-bias]] — DP disproportionately affects underrepresented groups; privacy-fairness trade-offs require explicit attention; differential privacy can provide fairness guarantees in some settings
- [[data-engineering]] — training data deduplication, filtering of PII, and data governance are first-line privacy defenses; formal methods (DP, MPC) provide stronger guarantees
- [[medical-imaging]] — patient privacy (HIPAA, GDPR) is a binding constraint; DP fine-tuning and federated learning enable training on medical data; TEEs enable cloud-based medical AI
- [[large-language-models]] — LLMs memorize and can regurgitate training data; DP pre-training is impractical at scale; DP fine-tuning + data curation is the current best practice
- [[transfer-learning]] — pre-train on public data + private fine-tuning is the dominant privacy paradigm; LoRA + DP reduces noise dimension for efficient private adaptation
- [[ai-safety-and-alignment]] — privacy is a safety property; training data extraction is a safety failure; alignment techniques must preserve privacy guarantees
