# Regularization

> Techniques that prevent neural networks from overfitting by constraining model capacity, injecting noise, or normalizing internal representations — enabling models to generalize from training data to unseen inputs.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — weight decay modifies the gradient; batch norm smooths the loss landscape
- [[convolutional-neural-networks]] — batch norm is integral to ResNets; spatial dropout is used for 2D features
- [[attention-and-transformers]] — layer normalization is integral to Transformers; dropout is applied to attention weights
- [[backpropagation]] — normalization layers help maintain well-conditioned gradients
- [[training-techniques]] — regularization is one component of the overall training recipe
