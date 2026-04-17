# Information Theory in Deep Learning

> The application of Shannon's information theory to understanding neural networks — entropy as a measure of uncertainty, mutual information for analyzing representations, the information bottleneck principle, and compression-based explanations of generalization.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[loss-functions]] — cross-entropy loss is a direct application of information theory; KL divergence appears in VAE and distillation losses
- [[autoencoders]] — the VAE objective (ELBO) is an information bottleneck; the KL term regularizes information in the latent code
- [[self-supervised-learning]] — InfoNCE (contrastive learning) is a mutual information lower bound; CLIP, SimCLR have information-theoretic interpretations
- [[knowledge-distillation]] — distillation loss is KL divergence between teacher and student distributions
- [[generalization-theory]] — PAC-Bayes bounds use KL divergence; MDL connects compression to generalization; the information bottleneck offers a framework for understanding why networks generalize
- [[regularization]] — dropout can be viewed as adding noise that reduces mutual information with the input; weight decay penalizes model complexity in an MDL sense
- [[speech-and-audio]] — neural audio codecs optimize rate-distortion trade-offs rooted in Shannon's source coding theorem
