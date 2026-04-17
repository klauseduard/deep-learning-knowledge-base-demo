# Gradient Descent

> The core optimization algorithm of deep learning, iteratively adjusting model parameters by moving them in the direction that reduces the loss function.

## Overview

Gradient descent is the engine that drives learning in neural networks. Given a model with parameters $w$ and a loss function $\mathcal{L}(w)$ that measures how poorly the model performs, gradient descent iteratively updates $w$ by computing the gradient $\nabla \mathcal{L}(w)$ — the vector of partial derivatives indicating the direction of steepest ascent — and stepping in the opposite direction. The update rule is:

$$w \leftarrow w - \eta \nabla \mathcal{L}(w)$$

where $\eta$ is the *learning rate*, a critical hyperparameter that controls the step size.

In practice, computing the gradient over the entire training dataset is prohibitively expensive. *Stochastic Gradient Descent* (SGD) approximates the true gradient by computing it over a randomly sampled *mini-batch* of training examples. This introduces noise into the gradient estimate, which paradoxically helps: the noise acts as a form of regularization, preventing the optimizer from settling into sharp minima that generalize poorly. Modern training typically uses mini-batch sizes ranging from 32 to several thousand examples.

The loss landscape of a deep network — the surface defined by $\mathcal{L}(w)$ over the high-dimensional parameter space — is complex, non-convex (unlike a simple bowl with one minimum, it has many valleys, ridges, and saddle points), and full of saddle points. Despite this, SGD and its variants reliably find good solutions. The combination of overparameterization, stochasticity, and careful learning rate scheduling has proven remarkably effective, and gradient-based optimization remains the only viable approach for training networks with millions to billions of parameters.

## Key Details

### Intuition

Imagine you are blindfolded on a hilly landscape and want to reach the lowest valley. At each step, you feel the slope of the ground beneath your feet and take a step downhill. The steeper the slope, the more confident you are in the direction. The learning rate is how big a step you take — too large and you overshoot valleys, too small and you barely move. Stochastic gradient descent is like feeling the slope through thick gloves: you get a noisy estimate of the direction, but over many steps you still make progress.

### Etymology & History

The method of steepest descent dates to Augustin-Louis Cauchy, who proposed it in 1847. The term "gradient" itself comes from the Latin *gradus* ("step" or "degree") and was adopted in vector calculus during the 19th century. Stochastic gradient descent was introduced by Herbert Robbins and Sutton Monro in 1951 as "stochastic approximation." The application of SGD to neural networks was pioneered by Rumelhart, Hinton, and Williams in their seminal 1986 backpropagation paper. The modern era of SGD for deep learning was catalyzed by Bottou (2010), who demonstrated that SGD's computational efficiency and implicit regularization made it superior to batch methods for large-scale learning.

### The Learning Rate

The learning rate $\eta$ is perhaps the single most important hyperparameter:

- **Too large**: the optimization diverges or oscillates wildly
- **Too small**: training is extremely slow and may get stuck in poor local minima
- **Just right**: the loss decreases steadily toward a good solution

Typical initial values range from $10^{-4}$ to $10^{-1}$, depending on the optimizer and architecture.

### Learning Rate Schedules

> *Requires the [Obsidian Plotly plugin](https://github.com/Dmytro-Shulha/obsidian-plotly). Warmup + cosine decay is the standard schedule for modern transformer training.*

```plotly
data:
  - x: [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100]
    y: [0.0, 0.2, 0.4, 0.6, 0.8, 1.0, 0.999, 0.995, 0.989, 0.981, 0.97, 0.957, 0.942, 0.924, 0.905, 0.883, 0.86, 0.835, 0.808, 0.78, 0.75, 0.719, 0.687, 0.655, 0.621, 0.587, 0.552, 0.517, 0.483, 0.448, 0.413, 0.379, 0.346, 0.313, 0.281, 0.25, 0.22, 0.192, 0.165, 0.14, 0.117, 0.096, 0.076, 0.059, 0.043, 0.03, 0.019, 0.011, 0.005, 0.001, 0.0]
    name: "Warmup + Cosine Decay"
    type: scatter
    mode: lines
    line: {color: "#2196F3", width: 3}
  - x: [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100]
    y: [0.1, 0.14, 0.18, 0.22, 0.26, 0.3, 0.34, 0.38, 0.42, 0.46, 0.5, 0.54, 0.58, 0.62, 0.66, 0.7, 0.74, 0.78, 0.82, 0.86, 0.9, 0.94, 0.98, 0.982, 0.946, 0.91, 0.874, 0.838, 0.802, 0.766, 0.73, 0.694, 0.658, 0.622, 0.586, 0.55, 0.514, 0.478, 0.442, 0.406, 0.37, 0.334, 0.298, 0.262, 0.226, 0.19, 0.154, 0.118, 0.082, 0.046, 0.01]
    name: "One-Cycle"
    type: scatter
    mode: lines
    line: {color: "#FF5722", width: 3, dash: "dash"}
layout:
  title: "Common Learning Rate Schedules"
  xaxis:
    title: "Training Step (% of total)"
  yaxis:
    title: "Learning Rate (relative to peak)"
  legend:
    x: 0.65
    y: 0.98
```

The learning rate is rarely constant throughout training:

- **Warmup**: start with a very small $\eta$ and linearly increase it over the first few thousand steps; this stabilizes early training when gradients are unreliable
- **Cosine decay**: after warmup, decrease $\eta$ following a cosine curve from the peak value to near zero
- **Step decay**: reduce $\eta$ by a factor (e.g., $\times 0.1$) at predetermined epochs
- **One-cycle**: increase then decrease $\eta$ within each training run

### Momentum and Adaptive Optimizers

SGD can be enhanced with techniques that improve convergence. These aren't separate algorithms — they build on the same gradient descent principle but modify *how* the gradient is used to update parameters. See [[optimization-beyond-sgd]] for the full optimizer family tree.

**SGD with Momentum** addresses the problem of oscillation in narrow ravines of the loss landscape. Momentum adds a velocity term that accumulates a running average of past gradients:

$$v \leftarrow \beta v + \nabla \mathcal{L}(w), \quad w \leftarrow w - \eta v$$

where $\beta \approx 0.9$. This acts like a heavy ball rolling downhill — it builds speed in consistent directions and dampens oscillations.

**Adam** (Kingma & Ba, 2015) goes further by maintaining per-parameter running averages of both the gradient (first moment $m$) and squared gradient (second moment $v$):

$$m \leftarrow \beta_1 m + (1-\beta_1) \nabla \mathcal{L}, \quad v \leftarrow \beta_2 v + (1-\beta_2) (\nabla \mathcal{L})^2$$
$$w \leftarrow w - \eta \frac{\hat{m}}{\sqrt{\hat{v}} + \epsilon}$$

where $\hat{m}$ and $\hat{v}$ are bias-corrected estimates. Adam effectively gives each parameter its own adaptive learning rate. It is the default optimizer for **[[attention-and-transformers|transformer]]** training, though SGD with momentum remains competitive for **[[convolutional-neural-networks|convolutional networks]]**.

### Mini-Batch Size

The mini-batch size $B$ controls the trade-off between gradient quality and computational efficiency:

- **Small batches** ($B = 32$–$128$): noisier gradients, stronger regularization effect, less GPU utilization
- **Large batches** ($B = 1024$+): more accurate gradients, faster wall-clock training on parallel hardware, but may generalize worse without adjustments
- **Linear scaling rule**: when increasing batch size by $k\times$, increase learning rate by $k\times$ (Goyal et al., 2017). The reasoning: a larger batch averages over more samples, producing a $k\times$ less noisy gradient. Scaling the learning rate proportionally keeps the effective update magnitude per training example the same, preserving similar training dynamics. This breaks down at very large batch sizes, where warmup and specialized optimizers like LARS become necessary.

### The Loss Landscape

The loss function of a deep network defines a surface in a space with potentially billions of dimensions. Key features:

- **Local minima**: points where the loss is lower than all neighbors — feared historically but now understood to be mostly benign in high-dimensional spaces
- **Saddle points**: points where the gradient is zero but the loss increases in some directions and decreases in others — far more common than local minima in high dimensions
- **Flat regions**: areas where the loss changes very slowly, slowing down optimization
- **Sharp vs. flat minima**: flat minima tend to generalize better; SGD noise biases toward them

### Weight Initialization

Gradient descent requires a starting point. Random initialization must be carefully scaled to prevent activations and gradients from exploding or vanishing at the start of training. Xavier/Glorot initialization (2010) scales weights by $1/\sqrt{D_{in}}$, and Kaiming/He initialization (2015) adjusts for ReLU activations with $\sqrt{2/D_{in}}$.

## Learn

- [Gradient Descent — Interactive Learning](../teach/gradient-descent/index.html) — explore 3D loss landscapes, learning rate effects, momentum, and optimizer comparison
- [SGD by the Numbers](../teach/gradient-descent/sgd-math.html) — worked example: mini-batch gradient averaging and parameter updates with concrete arithmetic, plus a multi-epoch training runner

## Connections

- [[backpropagation]] — provides the gradients that gradient descent consumes
- [[loss-functions]] — defines the objective surface being optimized
- [[scaling-laws]] — relate compute budget (determined by SGD iterations) to model performance
- [[training-techniques]] — learning rate schedules, mixed precision, and other practical refinements
- [[regularization]] — weight decay adds an L2 penalty term to the gradient
- [[loss-landscape-geometry]] — the structure of the optimization surface SGD navigates
- [[optimization-theory-for-deep-learning]] — why SGD works despite non-convexity
- [[optimization-beyond-sgd]] — Adam, AdaGrad, LARS, and the full optimizer family tree
- [[attention-and-transformers]] — Adam is the default optimizer for transformer training
- [[convolutional-neural-networks]] — SGD with momentum remains competitive here

## Sources

- Cauchy, A. (1847). "Méthode générale pour la résolution des systèmes d'équations simultanées."
- Robbins, H. & Monro, S. (1951). "A Stochastic Approximation Method." *Annals of Mathematical Statistics*.
- Rumelhart, D., Hinton, G. & Williams, R. (1986). "Learning representations by back-propagating errors." *Nature*.
- Kingma, D. & Ba, J. (2015). "Adam: A Method for Stochastic Optimization." *ICLR*.
- Fleuret, F. (2023). *The Little Book of Deep Learning*. Chapters 3.3–3.5.

## Open Questions

- Why does SGD find good solutions in non-convex landscapes — is there a deeper theoretical explanation? (see [[optimization-theory-for-deep-learning]])
- Is Adam truly optimal, or are there better adaptive methods waiting to be discovered?
- How does the implicit regularization of SGD noise interact with explicit regularization techniques?
- Can second-order methods (using curvature information) become practical at scale?
