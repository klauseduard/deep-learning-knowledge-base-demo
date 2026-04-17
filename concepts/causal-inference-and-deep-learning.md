# Causal Inference and Deep Learning

> Moving beyond correlation to causation — causal discovery from observational data, treatment effect estimation with neural networks, causal representation learning, the structural causal model framework, and why causality matters for robustness, fairness, and generalization.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[generalization-theory]] — causal features generalize across environments while spurious correlations don't; IRM and domain generalization formalize this through the causal lens
- [[fairness-and-bias]] — counterfactual fairness (Kusner et al., 2017) defines fairness through causal models; causal reasoning distinguishes legitimate from illegitimate use of protected attributes
- [[adversarial-robustness]] — adversarial examples exploit non-causal features; models relying on causal features should be more robust to perturbations that change spurious correlations
- [[test-time-adaptation]] — distribution shift is a change in spurious correlations; models with causal representations should require less adaptation to new domains
- [[data-augmentation]] — augmentation breaks spurious correlations, forcing reliance on causal features; the causal perspective explains why augmentation improves generalization
- [[interpretability]] — causal models are inherently interpretable (the DAG shows why); mechanistic interpretability seeks causal circuits inside neural networks
- [[autoencoders]] — CausalVAE extends VAEs with causal structure; disentangled representation learning (β-VAE) aims for independent factors that are often causal
