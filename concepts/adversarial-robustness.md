# Adversarial Robustness

> The study of how small, carefully crafted perturbations can fool neural networks, and the defenses (adversarial training, certified robustness) developed to make models reliable under attack.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[ai-safety-and-alignment]] — adversarial robustness is a prerequisite for trustworthy AI; adversarial attacks on LLMs (jailbreaks) are a form of adversarial examples on text
- [[loss-landscape-geometry]] — adversarial training flattens the loss landscape; SAM and adversarial training share the goal of seeking flat minima
- [[regularization]] — adversarial training acts as a form of regularization, improving generalization to certain distribution shifts
- [[generalization-theory]] — the robustness-accuracy trade-off reveals that robust and standard generalization may require fundamentally different representations
- [[training-techniques]] — adversarial training is a training technique, though 5–10× more expensive than standard training
- [[diffusion-models]] — diffusion-based purification is a recent defense approach: denoise adversarial inputs before classification
- [[interpretability]] — robust models learn more interpretable features; adversarial examples probe what models actually learn
- [[bayesian-deep-learning]] — uncertainty estimation relates to adversarial detection; adversarial examples often have unusual uncertainty profiles
