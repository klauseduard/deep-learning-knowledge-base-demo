# World Models and Predictive Learning

> Learning internal models of environment dynamics that predict future states — from Ha & Schmidhuber's dream-based RL agents to LeCun's JEPA vision, connecting reinforcement learning, video prediction, and the quest for autonomous machine intelligence.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[reinforcement-learning]] — world models enable model-based RL, where agents plan by imagining trajectories; MuZero and Dreamer are the flagship examples
- [[self-supervised-learning]] — JEPA, I-JEPA, and V-JEPA are self-supervised methods where the pretext task is prediction in representation space; world models are SSL applied to dynamics
- [[autoencoders]] — VAEs provide the perception component (compress observations to latent space); VQ-VAE tokenizes observations for autoregressive world models (IRIS)
- [[video-understanding-and-generation]] — video generation models (Sora) are implicitly world models; Genie shows that playable worlds can be extracted from video
- [[diffusion-models]] — diffusion-based world models generate future states; UniSim uses diffusion for universal simulation
- [[attention-and-transformers]] — Transformer-based world models (IRIS, Genie) use autoregressive prediction of tokenized observations, connecting world modeling to language modeling
- [[large-language-models]] — LLMs can be viewed as world models of text (predicting the next token is predicting the future of the text sequence); some argue LLMs build implicit world models of the processes generating text
- [[scaling-laws]] — world model quality presumably scales with model size and data, but the scaling laws for world models are much less studied than for language models
