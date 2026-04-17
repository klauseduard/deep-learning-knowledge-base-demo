# Loss Functions

> Mathematical functions that quantify the discrepancy between a model's predictions and the desired outputs, defining the objective that training optimizes.

## Overview

A loss function (also called a cost function or objective function) is the mathematical expression that a neural network's training procedure seeks to minimize. It takes the model's output and the ground-truth target and produces a single scalar value measuring how "wrong" the prediction is. The choice of loss function fundamentally shapes what the network learns — different loss functions encode different notions of what constitutes a good prediction.

The two most important families are **regression** losses, which measure numerical distance when predicting continuous values (e.g., predicting a house price or a pixel intensity), and **classification** losses, which measure the quality of probability distributions over discrete categories (e.g., "is this image a cat or a dog?"). **Cross-entropy** is the dominant classification loss — by far the most prevalent loss function in modern deep learning, underpinning everything from [[image-classification-milestones|image classification]] to [[large-language-models|language modeling]]. As Fleuret notes, "the standard loss for classification is the cross-entropy loss."

A subtlety that matters in practice is that the loss function can bias the model toward particular kinds of errors. Mean squared error (MSE) penalizes large errors quadratically, encouraging the model to predict the *conditional mean* — the average of all plausible outputs given the input. When the target is ambiguous (multiple valid outputs), this average may not itself be a valid output (e.g., a blurry image that is the average of many sharp images). Cross-entropy loss, by contrast, encourages the model to assign high probability to the correct answer, producing sharper predictions. This distinction becomes critical in [[diffusion-models|generative models]], where MSE can produce unrealistic blurry outputs.

## Key Details

### Intuition

A loss function is like a grading rubric for an exam. It defines exactly what "getting it right" means and how much penalty different mistakes incur. A strict rubric (cross-entropy) gives full credit only for the right answer. A lenient rubric (MSE) partially credits answers that are close. The rubric you choose determines what the student (model) optimizes for — and different rubrics lead to genuinely different learned behaviors.

### Etymology & History

The term "loss function" originated in statistical decision theory, formalized by Abraham Wald in 1950. The concept of minimizing expected loss (empirical risk) to train models was developed by Vladimir Vapnik as part of statistical learning theory in the 1960s–90s. Cross-entropy has roots in [[information-theory]] — Claude Shannon's 1948 paper defined entropy (a measure of uncertainty in a distribution), and Solomon Kullback and Richard Leibler formalized Kullback-Leibler (KL) divergence in 1951 — a measure of how much one probability distribution differs from another. Cross-entropy is directly related: it equals the true distribution's entropy plus the KL divergence from the predicted distribution, so minimizing cross-entropy is equivalent to making the model's predictions match the true distribution as closely as possible. The term "cost function" is more common in optimization theory, while "objective function" is the most general term.

### Mean Squared Error (MSE)

> *Requires the [Obsidian Plotly plugin](https://github.com/Dmytro-Shulha/obsidian-plotly). Notice how MSE penalizes large errors quadratically, while MAE penalizes linearly and Huber transitions between the two.*

```plotly
data:
  - x: [-3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0]
    y: [9.0, 7.562, 6.25, 5.062, 4.0, 3.062, 2.25, 1.562, 1.0, 0.562, 0.25, 0.062, 0.0, 0.062, 0.25, 0.562, 1.0, 1.562, 2.25, 3.062, 4.0, 5.062, 6.25, 7.562, 9.0]
    name: "MSE (e²)"
    type: scatter
    mode: lines
    line: {color: "#2196F3", width: 3}
  - x: [-3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0]
    y: [3.0, 2.75, 2.5, 2.25, 2.0, 1.75, 1.5, 1.25, 1.0, 0.75, 0.5, 0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0]
    name: "MAE (|e|)"
    type: scatter
    mode: lines
    line: {color: "#FF5722", width: 3, dash: "dash"}
  - x: [-3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0]
    y: [2.5, 2.25, 2.0, 1.75, 1.5, 1.25, 1.0, 0.75, 0.5, 0.281, 0.125, 0.031, 0.0, 0.031, 0.125, 0.281, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5]
    name: "Huber (δ=1)"
    type: scatter
    mode: lines
    line: {color: "#4CAF50", width: 3, dash: "dot"}
layout:
  title: "Regression Loss Functions"
  xaxis:
    title: "Prediction Error (ŷ - y)"
    zeroline: true
    zerolinewidth: 1
  yaxis:
    title: "Loss"
    zeroline: true
  legend:
    x: 0.4
    y: 0.98
    xanchor: center
```

For regression tasks — predicting continuous values — the standard loss is:

$$\mathcal{L}_{\text{MSE}} = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2$$

where $y_i$ is the target and $\hat{y}_i$ is the prediction. Properties:
- Penalizes large errors disproportionately (quadratic) — an error of 2 costs 4x as much as an error of 1
- The optimal prediction under MSE is the **conditional mean** $\mathbb{E}[Y | X]$ — "given this input $X$, what is the average of all valid outputs $Y$?" For most tasks there's only one right answer, so this is just that answer. But when the task is ambiguous (e.g., "generate a face matching this description"), many valid outputs exist, and the conditional mean is their pixel-wise average — a blurry composite that doesn't look like any real face. This is why MSE tends to produce blurry outputs for generation tasks
- Gradient: $\frac{\partial \mathcal{L}}{\partial \hat{y}_i} = \frac{2}{N}(\hat{y}_i - y_i)$ — proportional to the error, so larger errors produce larger [[gradient-descent|gradient steps]]

**Mean Absolute Error (MAE)** replaces the squared error with the absolute value:

$$\mathcal{L}_{\text{MAE}} = \frac{1}{N} \sum_{i=1}^{N} |y_i - \hat{y}_i|$$

This penalizes errors linearly rather than quadratically — an error of 2 costs exactly 2x as much as an error of 1, not 4x. MAE is more robust to outliers (a single extreme error doesn't dominate the loss) and the optimal prediction is the conditional median rather than the conditional mean.

### Cross-Entropy Loss

```plotly
data:
  - x: [0.01, 0.02, 0.03, 0.05, 0.07, 0.1, 0.15, 0.2, 0.25, 0.3, 0.35, 0.4, 0.45, 0.5, 0.55, 0.6, 0.65, 0.7, 0.75, 0.8, 0.85, 0.9, 0.95, 0.99]
    y: [4.605, 3.912, 3.507, 2.996, 2.659, 2.303, 1.897, 1.609, 1.386, 1.204, 1.050, 0.916, 0.799, 0.693, 0.598, 0.511, 0.431, 0.357, 0.288, 0.223, 0.163, 0.105, 0.051, 0.010]
    name: "-log(p) — cross-entropy loss"
    type: scatter
    mode: lines
    line: {color: "#7b5ea7", width: 3}
    fill: tozeroy
    fillcolor: "rgba(123, 94, 167, 0.08)"
layout:
  title: "Cross-Entropy Loss: -log(ŷₖ)"
  xaxis:
    title: "Predicted probability of correct class (ŷₖ)"
    zeroline: true
    range: [0, 1.02]
  yaxis:
    title: "Loss"
    zeroline: true
    range: [0, 5]
  annotations:
    - x: 0.05
      y: 3.0
      text: "Confident & wrong:<br>loss explodes →∞"
      showarrow: true
      arrowhead: 2
      ax: 60
      ay: -20
      font: {size: 11, color: "#c0392b"}
    - x: 0.9
      y: 0.105
      text: "Confident & correct:<br>loss ≈ 0"
      showarrow: true
      arrowhead: 2
      ax: -50
      ay: -40
      font: {size: 11, color: "#27864a"}
  hovermode: closest
```

> *The shape of $-\log(p)$ is the key to understanding cross-entropy: the loss is near zero when the model assigns high probability to the correct answer, rises gently for moderate errors, and explodes toward infinity when the model is confidently wrong. This asymmetry is what makes cross-entropy effective — it creates a powerful gradient signal to correct mistakes.*

For classification — predicting a probability distribution over $C$ classes:

$$\mathcal{L}_{\text{CE}} = -\sum_{c=1}^{C} y_c \log \hat{y}_c$$

where $y$ is a **one-hot vector** (a vector that is 1 for the correct class and 0 for all others — e.g., for "cat" in a [cat, dog, fish] classifier: $y = [1, 0, 0]$) and $\hat{y}$ is the model's predicted probability distribution over the classes.

Since the one-hot vector zeros out all terms except the correct class $k$, this simplifies to:

$$\mathcal{L}_{\text{CE}} = -\log \hat{y}_k$$

The loss is the negative logarithm of the predicted probability of the correct answer. Why the logarithm? Because $-\log(p)$ has exactly the right shape: it is 0 when $p = 1$ (the model is perfectly confident and correct), rises gently for small errors, and shoots to $\infty$ as $p \to 0$ (the model assigns near-zero probability to the right answer). This asymmetric penalty means the model is severely punished for being confidently wrong, but barely rewarded for being more confident when already correct. The connection to [[information-theory]] is direct: cross-entropy measures how many bits are wasted when using the model's predicted distribution to encode data drawn from the true distribution.

**Softmax: from raw scores to probabilities.** The network's final layer outputs raw, unbounded scores called **logits** — one per class ($z_1, \ldots, z_C$). These must be converted to a probability distribution (non-negative, sums to 1) before the cross-entropy loss can be applied. The **softmax** function does this:

$$\hat{y}_c = \frac{\exp(z_c)}{\sum_{j=1}^{C} \exp(z_j)}$$

The exponential $\exp(z)$ ensures all values are positive. Dividing by the sum ensures they add to 1. The exponential also amplifies differences: if one logit is much larger than the others, softmax assigns it a probability close to 1 — a "winner-take-all" effect that becomes more extreme as the logit magnitudes grow. In practice, a numerically stable version subtracts $\max_j z_j$ from all logits before exponentiating (this doesn't change the result since $\exp(z_c - m) / \sum \exp(z_j - m) = \exp(z_c) / \sum \exp(z_j)$, but prevents overflow from large exponentials).

Properties:
- Loss approaches 0 when $\hat{y}_k \to 1$ (confident and correct)
- Loss approaches $\infty$ when $\hat{y}_k \to 0$ (confident and wrong) — a harsh penalty
- Gradient w.r.t. logits has the elegant form: $\frac{\partial \mathcal{L}}{\partial z_c} = \hat{y}_c - y_c$ — simply "predicted minus actual." The gradient for the correct class is $(\hat{y}_k - 1)$, pushing its logit up; the gradient for wrong classes is $\hat{y}_c$, pushing their logits down

### Autoregressive Cross-Entropy

For [[autoregressive-models|sequence models]] like [[large-language-models]], the loss is the sum of cross-entropies at each position — "how well did the model predict each next token?":

$$\mathcal{L} = -\sum_{t=1}^{T} \log P(x_t | x_1, \ldots, x_{t-1})$$

Each term is a standard cross-entropy loss where the model's softmax output at position $t$ is evaluated against the actual token $x_t$. This is the standard training objective for language models. Because the model is causal (each position can only attend to earlier positions via [[attention-and-transformers|causal masking]]), all $T$ position losses can be computed in parallel during training, even though generation proceeds one [[tokenization|token]] at a time.

### Contrastive Loss

Used in models like [[multimodal-models|CLIP]] (Radford et al., 2021) that learn to align [[embeddings-and-representation-learning|embeddings]] from different modalities:

Given a batch of $N$ paired embeddings (e.g., image $f(i_m)$ and text $g(t_n)$), compute the $N \times N$ similarity matrix $l_{m,n} = f(i_m) \cdot g(t_n)$. The loss treats each row and column as a classification problem: for row $n$, the correct match is column $n$.

$$\mathcal{L} = -\frac{1}{N} \sum_{n=1}^{N} \left[ \log \frac{\exp(l_{n,n})}{\sum_m \exp(l_{m,n})} + \log \frac{\exp(l_{n,n})}{\sum_m \exp(l_{n,m})} \right]$$

This encourages matching pairs to have high similarity while pushing non-matching pairs apart.

### Other Notable Losses

- **Hinge loss**: $\max(0, 1 - y \cdot \hat{y})$ — used in SVMs, not differentiable at the kink (similar to the ReLU kink in [[activation-functions]])
- **Huber loss**: MSE for small errors, MAE for large errors — combines benefits of both (smooth transition controlled by threshold $\delta$, shown in the regression loss chart above)
- **Focal loss** (Lin et al., 2017): down-weights easy examples in imbalanced classification — used in [[object-detection]] where background overwhelms foreground
- **Perceptual loss**: compare features extracted by a pre-trained [[convolutional-neural-networks|CNN]] rather than raw pixels — produces sharper results for image generation
- **Adversarial loss**: the generator in a [[generative-adversarial-networks|GAN]] maximizes the discriminator's loss

## Learn

- [Cross-Entropy & Softmax — Worked Math](../teach/loss-functions/cross-entropy-math.html) — step-by-step: softmax computation with real numbers, cross-entropy loss, the gradient formula, and a parameter update — every intermediate value shown
- [Cross-Entropy & Softmax Explorer](../teach/loss-functions/index.html) — interactive: adjust logits and watch softmax probabilities, the $-\log(p)$ loss curve, and per-class gradients respond in real time. Includes temperature control and presets for confident-correct, confident-wrong, and edge cases.

## Connections

- [[backpropagation]] — the loss is the starting node of the backward pass; the loss gradient is the error signal that propagates through the network
- [[gradient-descent]] — minimizes the loss function over parameter space
- [[activation-functions]] — softmax converts logits to probabilities for cross-entropy; sigmoid is used for binary cross-entropy
- [[information-theory]] — cross-entropy and KL divergence originate from information theory; the loss measures wasted bits
- [[autoregressive-models]] — use summed cross-entropy over sequence positions
- [[large-language-models]] — trained with autoregressive cross-entropy, aligned with RLHF reward
- [[diffusion-models]] — trained with denoising objectives related to log-likelihood
- [[generative-adversarial-networks]] — adversarial loss pits generator against discriminator
- [[self-supervised-learning]] — contrastive losses (InfoNCE) and reconstruction losses drive self-supervised pre-training
- [[object-detection]] — focal loss addresses class imbalance in detection

## Sources

- Shannon, C. (1948). "A Mathematical Theory of Communication." *Bell System Technical Journal*.
- Kullback, S. & Leibler, R. (1951). "On Information and Sufficiency." *Annals of Mathematical Statistics*.
- Radford, A. et al. (2021). "Learning Transferable Visual Models From Natural Language Supervision." *ICML*.
- Fleuret, F. (2023). *The Little Book of Deep Learning*. Chapter 3.1.

## Open Questions

- Can we design loss functions that better capture human perceptual quality for generation tasks?
- How should losses be combined when a model has multiple objectives (multi-task learning)?
- What is the theoretical relationship between the loss landscape geometry and generalization?
- Are there alternatives to cross-entropy for classification that offer better calibration?
