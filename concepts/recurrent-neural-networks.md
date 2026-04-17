# Recurrent Neural Networks

> Architectures with internal memory that process sequences element-by-element, updating a hidden state at each step — historically the dominant approach for temporal data before Transformers.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[attention-and-transformers]] — Transformers were designed to replace RNNs; attention was originally invented to augment RNNs
- [[backpropagation]] — BPTT is backpropagation applied to the unrolled recurrence; vanishing/exploding gradients are most severe here
- [[skip-connections]] — LSTM's additive cell state is an early form of residual connection
- [[state-space-models]] — SSMs achieve RNN-like recurrence with Transformer-like parallelism
- [[activation-functions]] — sigmoid gates and tanh activations are integral to LSTM/GRU
- [[autoregressive-models]] — RNNs were the original autoregressive sequence models
