# Neural ODEs and Continuous Models

> A paradigm that replaces discrete layer-by-layer computation with continuous dynamical systems described by ordinary differential equations — unifying neural networks, differential equations, and generative modeling.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[skip-connections]] — ResNets are Euler discretizations of Neural ODEs; the skip connection is what makes the ODE interpretation possible
- [[state-space-models]] — SSMs are linear ODEs with efficient discretization; Neural ODEs are the nonlinear generalization
- [[diffusion-models]] — diffusion models are Neural SDEs; the probability flow ODE is a Neural ODE, and flow matching simplifies training
- [[autoencoders]] — continuous normalizing flows generalize the latent space perspective of VAEs with exact likelihood computation
- [[generalization-theory]] — the continuous depth perspective offers new ways to analyze generalization via dynamical systems stability
- [[recurrent-neural-networks]] — Neural ODEs can be seen as continuous-time RNNs, handling the same sequential processing with different mathematical tools
- [[loss-landscape-geometry]] — the ODE perspective on ResNets connects to optimal transport and loss landscape theory
- [[text-to-image-generation]] — flow matching (from Neural ODE theory) is the basis of Stable Diffusion 3 and Flux
