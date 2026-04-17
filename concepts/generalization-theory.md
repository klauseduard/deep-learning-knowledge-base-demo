# Generalization Theory

> The study of why deep networks — despite having far more parameters than training examples — generalize to unseen data rather than memorizing the training set, challenging classical statistical learning theory.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — SGD's implicit regularization is a leading explanation for generalization in overparameterized networks
- [[loss-functions]] — the loss landscape geometry (sharp vs. flat minima) determines generalization
- [[regularization]] — explicit regularizers (dropout, weight decay) improve generalization but cannot fully explain it; implicit regularization from SGD may be more important
- [[scaling-laws]] — scaling laws empirically characterize how generalization improves with scale, but generalization theory aims to explain *why*
- [[backpropagation]] — the training dynamics that produce generalization depend on how gradients flow through the network
- [[training-techniques]] — learning rate schedules, batch size, and training duration all affect generalization through their influence on the loss landscape
