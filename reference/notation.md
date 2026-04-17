# Mathematical Notation

> A reference for the symbols and conventions used throughout this knowledge base and in deep learning literature generally.

## Variables and Values

| Symbol | Meaning | Example |
|---|---|---|
| $x$ | Input data (a single example) | An image, a sentence, a feature vector |
| $y$ | True target / ground truth label | The correct class, the true next token |
| $\hat{y}$ | **Predicted** value — the hat (^) always means "estimated" or "predicted" | $\hat{y} = 0.7$ means the model predicts 0.7 |
| $w$, $W$ | Weights (learnable parameters) — lowercase for a scalar, uppercase for a matrix | $W_1$ is the weight matrix of layer 1 |
| $b$ | Bias (learnable parameter added after the linear transform) | $z = Wx + b$ |
| $h$, $h_l$ | Hidden activations — the output of layer $l$ | $h_2$ is the activation vector after layer 2 |
| $z$ | Pre-activation value (before the activation function is applied) | $z = Wx + b$, then $h = \sigma(z)$ |
| $\theta$ | All model parameters collectively | "Optimize over $\theta$" means adjust all weights and biases |
| $\hat{\theta}$ | Estimated parameter value — same hat convention as $\hat{y}$ | From statistics: $\hat{\theta}$ is our best guess of $\theta$ |

## Functions and Operators

| Symbol | Name | Meaning |
|---|---|---|
| $\mathcal{L}$ | Loss function (script L) | The function being minimized during training |
| $\sigma(x)$ | Sigmoid | $1 / (1 + e^{-x})$ — squashes input to $(0, 1)$ |
| $\text{relu}(x)$ | ReLU | $\max(0, x)$ |
| $\Phi(x)$ | Standard normal CDF | Probability that a draw from a bell curve falls below $x$ — used in [[activation-functions\|GELU]] |
| $\text{softmax}(z)_c$ | Softmax | $\exp(z_c) / \sum_j \exp(z_j)$ — converts logits to probabilities |
| $\log$ | Natural logarithm | In ML, $\log$ almost always means $\ln$ (base $e$), not $\log_{10}$ |
| $\exp(x)$ | Exponential | $e^x$ |
| $\| v \|$ | Norm | Length of a vector — $\| v \|_2 = \sqrt{\sum v_i^2}$ unless otherwise specified |
| $\arg\min_x f(x)$ | Argmin | The value of $x$ that minimizes $f$ (not the minimum value itself) |

## Derivatives and Gradients

| Symbol | Name | Meaning |
|---|---|---|
| $\frac{df}{dx}$ | Total derivative | Rate of change of $f$ with respect to $x$ (single variable) |
| $\frac{\partial f}{\partial x}$ | Partial derivative | Rate of change of $f$ w.r.t. $x$, holding all other variables fixed |
| $\nabla f$ | Gradient (nabla) | The vector of all partial derivatives: $\nabla f = \left(\frac{\partial f}{\partial x_1}, \ldots, \frac{\partial f}{\partial x_n}\right)$ |
| $\nabla_w \mathcal{L}$ | Gradient of loss w.r.t. weights | The specific gradient that [[gradient-descent]] uses to update parameters |
| $J$ or $\frac{\partial h_{l+1}}{\partial h_l}$ | Jacobian matrix | Matrix of all partial derivatives of a vector-valued function — how each output element depends on each input element |
| $\delta_l$ | Error signal | The gradient of the loss w.r.t. layer $l$'s activations — the value that propagates backward during [[backpropagation]] |

## Probability and Statistics

| Symbol | Meaning | Example |
|---|---|---|
| $P(A)$ | Probability of event $A$ | $P(y = \text{cat}) = 0.8$ |
| $P(A \mid B)$ | Conditional probability — probability of $A$ given $B$ | $P(x_t \mid x_{<t})$ = next token probability given context |
| $\mathbb{E}[X]$ | Expected value (mean) of random variable $X$ | $\mathbb{E}[X] = \sum x \cdot P(x)$ |
| $\mathbb{E}[Y \mid X]$ | Conditional mean — the expected value of $Y$ given a specific $X$ | "Given this input, what is the average correct output?" — the optimal prediction under MSE loss |
| $\mathcal{N}(\mu, \sigma^2)$ | Normal (Gaussian) distribution with mean $\mu$ and variance $\sigma^2$ | $W \sim \mathcal{N}(0, 1/n)$ means weights are drawn from this distribution |
| $\sim$ | "Distributed as" or "sampled from" | $x \sim P$ means $x$ is drawn from distribution $P$ |
| $D_{\text{KL}}(P \| Q)$ | Kullback-Leibler divergence | Measures how much distribution $P$ differs from $Q$ — see [[information-theory]] |
| $H(P)$ | Entropy | The average "surprise" or uncertainty of distribution $P$ |

## Training and Optimization

| Symbol | Meaning | Typical values |
|---|---|---|
| $\eta$ (eta) | Learning rate | $10^{-4}$ to $10^{-1}$ |
| $\beta$ (beta) | Momentum coefficient, or KL penalty weight | $\beta = 0.9$ for momentum |
| $\epsilon$ (epsilon) | Small constant for numerical stability, or perturbation size | $10^{-8}$ for Adam's denominator |
| $\lambda$ (lambda) | Regularization strength (weight decay) | $10^{-4}$ to $10^{-2}$ |
| $B$ | Batch size | 32, 256, 1024, etc. |
| $T$ | Sequence length, or temperature | Context-dependent |
| $N$ | Number of training examples | |
| $L$ | Number of layers, or loss value | Context-dependent |
| $D$ or $d$ | Dimensionality (of embeddings, hidden layers, etc.) | $d_{\text{model}} = 768$ |
| $C$ | Number of classes | |

## Conventions

- **Hat = predicted**: $\hat{y}$, $\hat{\theta}$, $\hat{p}$ always mean estimated/predicted values
- **Script letters = functions or sets**: $\mathcal{L}$ (loss), $\mathcal{N}$ (normal distribution), $\mathcal{D}$ (dataset)
- **Bold = vectors/matrices**: some texts use $\mathbf{x}$ for vectors and $\mathbf{W}$ for matrices, though this knowledge base generally uses plain italic
- **Subscripts = indexing**: $x_i$ is the $i$-th example, $w_l$ is the weight of layer $l$, $h_t$ is the hidden state at time $t$
- **Superscripts = powers or layer indices**: context-dependent — $x^2$ is squaring, $h^{(l)}$ is layer $l$ (parenthesized to distinguish from powers)
- **$\log$ means natural log**: throughout ML. If base-2 is intended, it's written $\log_2$
- **Sums over data vs. sums over dimensions**: $\frac{1}{N}\sum_{i=1}^N$ averages over examples in a batch; $\sum_{c=1}^C$ sums over classes or dimensions
