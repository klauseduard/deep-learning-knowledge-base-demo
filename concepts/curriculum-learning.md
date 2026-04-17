# Curriculum Learning

> Training neural networks by presenting examples in a meaningful order — from easy to hard — rather than randomly, inspired by how humans learn through structured curricula, with applications to faster convergence, better generalization, and training stability.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — curriculum learning changes the gradient distribution over training; easy examples provide cleaner gradients early on
- [[loss-functions]] — loss values on individual examples serve as the primary difficulty measure in self-paced learning
- [[data-engineering]] — curriculum is a data presentation strategy; data quality, augmentation, and mixing all interact with curriculum design
- [[training-techniques]] — learning rate warmup is an implicit curriculum (start with small, safe steps); pre-training → fine-tuning is a macro-level curriculum
- [[reinforcement-learning]] — curriculum is natural in RL where environment difficulty is controllable; reward shaping and domain randomization are curriculum strategies
- [[loss-landscape-geometry]] — curriculum smooths the effective loss landscape early in training, connecting to continuation methods and flat minima
- [[scaling-laws]] — data ordering's impact on scaling efficiency is an open question; curriculum may shift the scaling curve
- [[regularization]] — training on easy examples first acts as implicit regularization by avoiding overfitting to noisy hard examples
