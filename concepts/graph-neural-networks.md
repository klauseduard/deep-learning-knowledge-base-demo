# Graph Neural Networks

> Neural networks that operate on graph-structured data — learning node, edge, and graph-level representations through message passing between neighbors — enabling deep learning on molecules, social networks, and knowledge graphs.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[convolutional-neural-networks]] — GCNs generalize convolutions from regular grids to irregular graphs; the "receptive field" concept transfers directly
- [[attention-and-transformers]] — GAT applies attention to graph neighbors; graph transformers apply full attention to all nodes
- [[multilayer-perceptrons]] — message and update functions are typically MLPs
- [[recurrent-neural-networks]] — over-squashing in GNNs is analogous to vanishing gradients in RNNs
- [[self-supervised-learning]] — graph contrastive learning (GraphCL, GCC) pre-trains GNNs without labels
- [[skip-connections]] — residual connections help mitigate over-smoothing in deeper GNNs
