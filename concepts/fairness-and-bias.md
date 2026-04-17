# Fairness and Bias in Deep Learning

> How deep learning systems encode and amplify societal biases — sources of bias (data, annotation, model, deployment), fairness definitions and their incompatibilities, debiasing techniques, algorithmic auditing, and the tension between fairness and accuracy.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[ai-safety-and-alignment]] — bias is a core safety concern; RLHF and Constitutional AI aim to reduce harmful outputs; the alignment tax may disproportionately affect fairness
- [[data-engineering]] — bias enters primarily through data; data curation, filtering, and augmentation are the first line of defense
- [[medical-imaging]] — clinical AI bias has direct health consequences; AI recognizing patient race from X-rays raises concerns about shortcut features
- [[embeddings-and-representation-learning]] — word and sentence embeddings encode societal biases; debiasing embeddings is a specific research area
- [[text-to-image-generation]] — image generation amplifies stereotypes in training data; bias-aware generation is an active challenge
- [[synthetic-data-generation]] — synthetic data can augment underrepresented groups but may also encode the generator's biases
- [[recommender-systems]] — recommendation algorithms amplify popularity bias and can discriminate in exposure and opportunity
- [[large-language-models]] — LLMs absorb biases from web text; debiasing LLMs through RLHF, data curation, and Constitutional AI is ongoing
