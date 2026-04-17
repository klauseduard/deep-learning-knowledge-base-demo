# Data Augmentation

> Artificially expanding training data by applying label-preserving transformations — from geometric flips and crops to learned policies (RandAugment) and sample-mixing strategies (mixup, CutMix) — a universal regularizer that improves generalization across vision, language, and audio.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[regularization]] — augmentation is the most effective regularizer in practice; Cutout and dropout share the principle of forcing the model to use redundant features
- [[data-engineering]] — augmentation amplifies existing data; combined with synthetic data generation, it addresses data scarcity from two angles
- [[self-supervised-learning]] — contrastive learning (SimCLR, MoCo, BYOL) is fundamentally an augmentation-driven paradigm: learn representations invariant to augmentation transforms
- [[image-classification-milestones]] — every milestone used augmentation: AlexNet (random crops/flips), ResNet (multi-scale), DeiT (heavy augmentation replacing massive data)
- [[adversarial-robustness]] — adversarial training is a form of worst-case augmentation; mixup and CutMix provide mild robustness improvements
- [[generalization-theory]] — augmentation's regularization effect connects to the bias-variance trade-off; more augmentation reduces variance at the cost of potential bias
- [[training-techniques]] — augmentation is a core training technique interacting with learning rate, batch size, and training duration
- [[tokenization]] — subword regularization is text-level augmentation; different tokenizations of the same text create training diversity
