# Neural Network Initialization

> How weights are set before training begins — Xavier/Glorot and He/Kaiming initialization, the signal propagation principle, fixup for deep residual networks, $\mu$P for hyperparameter transfer across scales, and why initialization determines whether training succeeds or fails.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[backpropagation]] — initialization directly determines whether gradients can flow through the network; vanishing/exploding gradients are initialization failures
- [[activation-functions]] — the activation function determines the correct initialization variance (factor of 2 for ReLU vs. 1 for linear); GELU, SiLU, and other activations have their own scaling factors
- [[normalization-techniques]] — normalization (BN, LN, RMSNorm) partially compensates for bad initialization by rescaling activations; fixup and T-Fixup show initialization can replace normalization
- [[optimization-theory-for-deep-learning]] — $\mu$P connects initialization to the NTK vs. feature learning regimes; standard parameterization pushes wide networks toward lazy training, $\mu$P ensures feature learning
- [[skip-connections]] — residual connections change the initialization requirements (variance accumulation); zero-residual initialization enables very deep networks
- [[scaling-laws]] — $\mu$P enables hyperparameter transfer across scales, directly connecting initialization to efficient scaling; tuning on small proxies saves compute at scale
- [[loss-landscape-geometry]] — initialization determines the starting point in the loss landscape; the basin of attraction reached depends on where optimization begins
- [[distributed-training]] — large-batch training requires careful initialization and learning rate scaling (LARS, LAMB) to maintain training dynamics at large batch sizes
