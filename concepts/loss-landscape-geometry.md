# Loss Landscape Geometry

> The structure of the loss function as a surface over parameter space — saddle points dominate over local minima, loss surfaces are surprisingly well-connected, and the geometry of the minima found by SGD (flat vs. sharp) correlates with generalization.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[generalization-theory]] — flat minima, implicit regularization by SGD, double descent, and lottery tickets all have loss landscape geometric interpretations
- [[gradient-descent]] — the optimizer navigates the loss landscape; SGD's noise biases it toward flat minima; learning rate and batch size control the noise scale
- [[backpropagation]] — computes the gradient that defines the local geometry; the Hessian (second-order information) characterizes curvature
- [[skip-connections]] — ResNets dramatically smooth the loss landscape compared to plain networks, enabling optimization of very deep models
- [[regularization]] — batch normalization smooths the loss landscape; weight decay constrains the parameter space region explored
- [[loss-functions]] — the choice of loss defines the landscape; cross-entropy and MSE produce different geometric structures
- [[training-techniques]] — learning rate schedules, warmup, and SAM all interact with loss landscape geometry
- [[meta-learning]] — MAML seeks initializations in regions where the landscape allows fast adaptation, connecting to flat minima ideas
- [[scaling-laws]] — larger models have smoother, more connected landscapes, partially explaining why scaling improves performance
