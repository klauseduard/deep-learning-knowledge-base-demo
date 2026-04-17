# Evaluation and Benchmarking

> How deep learning models are measured — benchmark design and contamination, Goodhart's law in ML, human evaluation and arena-style ranking, metric reliability, and the gap between benchmarks and real-world performance.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[scaling-laws]] — benchmarks are how we measure whether scaling delivers capability; Chinchilla scaling was validated through benchmark performance; the evaluation gap challenges whether benchmark gains translate to real utility
- [[nlp-tasks]] — traditional NLP benchmarks (GLUE, SQuAD, WMT BLEU) track task-specific progress; the shift to unified LLM benchmarks (MMLU, MT-Bench) reflects the paradigm shift from task-specific to general models
- [[reasoning-in-llms]] — reasoning capabilities are the hardest to evaluate; process reward models evaluate intermediate steps; the gap between benchmark reasoning and real-world reasoning is large
- [[fairness-and-bias]] — disaggregated evaluation across demographic groups is essential; BBQ and WinoBias specifically test for bias; Chatbot Arena demographics may not represent all users
- [[prompt-engineering-and-in-context-learning]] — benchmark scores depend heavily on prompt format; few-shot vs. zero-shot, chain-of-thought prompting can dramatically change results, making "fair" comparison difficult
- [[data-engineering]] — benchmark contamination is a data engineering problem; training data decontamination is increasingly critical for trustworthy evaluation
- [[ai-safety-and-alignment]] — safety evaluation (HarmBench, TruthfulQA) is inherently harder than capability evaluation; red-teaming reveals vulnerabilities that benchmarks miss
