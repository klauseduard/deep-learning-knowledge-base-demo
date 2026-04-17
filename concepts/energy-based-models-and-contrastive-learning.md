# Energy-Based Models and Contrastive Learning Theory

> The mathematical framework connecting energy-based models, noise contrastive estimation, the InfoNCE objective, and modern self-supervised learning — why contrastive learning works, how it avoids collapse, and its theoretical connections to mutual information and spectral methods.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[self-supervised-learning]] — contrastive learning (SimCLR, MoCo, BYOL) is the dominant SSL paradigm; this article provides the theoretical foundations for why it works
- [[loss-functions]] — InfoNCE is a specific loss function with information-theoretic properties; temperature and negative sampling are loss design choices
- [[information-theory]] — InfoNCE lower-bounds mutual information; the debate about whether MI maximization explains contrastive learning's success
- [[embeddings-and-representation-learning]] — contrastive learning produces the embeddings used for retrieval, zero-shot classification, and downstream tasks; uniformity-alignment quantifies embedding quality
- [[diffusion-models]] — score-based diffusion models ARE EBMs trained via denoising score matching; the energy/score perspective unifies generative and discriminative approaches
- [[data-augmentation]] — augmentation defines the positive pairs for contrastive learning; the augmentation graph determines what invariances the representation learns
- [[generalization-theory]] — spectral contrastive learning connects representation quality to graph spectral properties; explains why augmentation choice matters for downstream transfer
