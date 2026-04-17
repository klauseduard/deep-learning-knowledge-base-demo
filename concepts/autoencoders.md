# Autoencoders

> Neural networks that learn to compress data into a low-dimensional latent representation and then reconstruct it — used for dimensionality reduction, feature learning, and as the probabilistic backbone of variational generation.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[diffusion-models]] — latent diffusion models use a pre-trained VAE to define the latent space in which diffusion operates
- [[generative-adversarial-networks]] — rival generative framework; VAE-GAN hybrids combine both
- [[loss-functions]] — the ELBO combines reconstruction loss and KL divergence
- [[backpropagation]] — the reparameterization trick enables gradient flow through stochastic sampling
- [[interpretability]] — sparse autoencoders decompose neural network activations into interpretable features
- [[convolutional-neural-networks]] — image VAE encoders and decoders are typically CNNs
