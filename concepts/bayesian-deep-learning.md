# Bayesian Deep Learning

> Incorporating uncertainty quantification into neural networks through Bayesian inference — placing distributions over weights instead of point estimates, with practical approximations including MC Dropout, variational inference, and deep ensembles, enabling models that know what they don't know.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[regularization]] — weight decay is equivalent to a Gaussian prior in Bayesian inference; dropout is approximate Bayesian inference (Gal & Ghahramani, 2016); all regularization has a Bayesian interpretation
- [[generalization-theory]] — Bayesian model selection (via the marginal likelihood) naturally penalizes model complexity; PAC-Bayes bounds provide generalization guarantees for models with stochastic weights
- [[loss-landscape-geometry]] — ensemble diversity comes from different local minima; Laplace approximation uses the loss curvature (Hessian); flat minima correspond to broad Bayesian posteriors
- [[loss-functions]] — cross-entropy loss is the negative log-likelihood in a Bayesian model; the ELBO decomposes into likelihood and KL terms
- [[ai-safety-and-alignment]] — reliable uncertainty is prerequisite for safe deployment; models should know when they don't know; OOD detection prevents confident errors on novel inputs
- [[information-theory]] — the ELBO involves KL divergence; the marginal likelihood connects to the minimum description length principle
- [[training-techniques]] — temperature scaling for calibration connects to softmax temperature in knowledge distillation; ensembles relate to model merging
- [[model-deployment]] — uncertainty-aware deployment enables abstention and human-in-the-loop workflows; calibration is a deployment requirement for safety-critical applications
