# Optimization Theory for Deep Learning

> Why gradient descent works in non-convex landscapes — implicit bias of SGD toward flat minima, edge of stability, progressive sharpening, the neural tangent kernel (NTK) regime vs. feature learning, and the gap between theory and practice.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[generalization-theory]] — implicit bias explains generalization from an optimization perspective; double descent and grokking are phenomena at the intersection of optimization and generalization
- [[loss-landscape-geometry]] — the loss landscape structure (saddle points, mode connectivity, flat vs. sharp minima) determines optimization dynamics; edge of stability directly links learning rate to landscape curvature
- [[optimization-beyond-sgd]] — practical optimizers (Adam, SAM) are designed based on (partial) theoretical understanding; the theory explains why learning rate warmup, gradient clipping, and batch size matter
- [[scaling-laws]] — the NTK vs. feature learning distinction may explain why larger models improve: more parameters enable richer feature learning, not just better kernel approximation
- [[regularization]] — implicit bias IS implicit regularization; explicit regularization (weight decay, dropout) interacts with SGD's implicit regularization, sometimes redundantly
- [[gradient-descent]] — the foundational algorithm whose theoretical properties this article analyzes; every result here is about understanding gradient descent's behavior in non-convex landscapes
- [[generalization-theory]] — grokking, double descent, and the implicit regularization of SGD are at the core of understanding why deep learning generalizes
- [[mechanistic-interpretability]] — grokking was first explained mechanistically (Nanda et al., 2023); optimization dynamics create interpretable circuits
