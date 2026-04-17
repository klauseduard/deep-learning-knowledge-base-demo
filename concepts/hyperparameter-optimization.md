# Hyperparameter Optimization

> Systematically tuning model hyperparameters — grid and random search, Bayesian optimization (TPE, Gaussian processes), multi-fidelity methods (Hyperband, ASHA), population-based training, and the μP approach to hyperparameter transfer across model scales.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[optimization-beyond-sgd]] — HPO tunes the optimizer's hyperparameters (learning rate, β1, β2, weight decay); the optimizer choice itself is a hyperparameter; schedule selection (cosine, linear, 1cycle) interacts with learning rate
- [[optimization-theory-for-deep-learning]] — μP provides theoretical foundations for hyperparameter transfer; the edge of stability determines the maximum stable learning rate; implicit bias of SGD depends on learning rate
- [[neural-architecture-search]] — NAS is HPO for architecture; the search methods overlap (Bayesian optimization, evolutionary methods, multi-fidelity); NAS + HPO can be unified as a joint search
- [[scaling-laws]] — scaling laws predict optimal model size and training tokens; μP enables hyperparameter transfer across scales; the cost of HPO at scale motivates transfer methods
- [[training-techniques]] — learning rate schedules (warmup, cosine), mixed precision, and gradient accumulation are all hyperparameters that HPO can optimize
- [[distributed-training]] — large-scale HPO requires distributed evaluation; batch size interacts with data parallelism; PBT naturally maps to distributed training infrastructure
