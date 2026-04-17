# Optimization Beyond SGD

> Advanced optimizers that improve upon vanilla stochastic gradient descent — adaptive methods (Adam, AdaGrad, AdaFactor), large-batch techniques (LARS, LAMB), second-order methods, and learning rate schedules, forming the practical toolkit for training modern neural networks.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — all methods here are extensions of SGD; momentum, adaptive rates, and schedules are all modifications to the basic gradient descent update
- [[loss-landscape-geometry]] — optimizer choice affects which minima are found; SGD's noise biases toward flat minima; Adam may find sharper solutions; learning rate warmup avoids bad basins early in training
- [[training-techniques]] — learning rate schedules, mixed precision, and gradient clipping all interact with optimizer choice; the warmup+cosine schedule is integral to modern training recipes
- [[distributed-training]] — large-batch optimizers (LARS, LAMB) enable scaling batch size for data parallelism; ZeRO shards optimizer states across GPUs; optimizer state is often the largest memory consumer
- [[normalization-techniques]] — BatchNorm interacts with learning rate (BN enables larger LR); AdamW's weight decay behaves differently with normalized layers
- [[regularization]] — weight decay (in AdamW) is a regularization technique; Adam's adaptive rates change how weight decay is applied compared to SGD
- [[scaling-laws]] — optimizer efficiency affects compute-optimal training; the Chinchilla scaling laws assume a specific optimizer and schedule
