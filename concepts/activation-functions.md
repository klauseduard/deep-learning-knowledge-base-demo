# Activation Functions

> Non-linear functions applied element-wise between layers, giving neural networks the ability to learn complex, non-linear mappings (input-to-output relationships) that pure linear layers cannot represent.

## Overview

Without activation functions, a neural network would be nothing more than a single linear transformation — no matter how many layers it has, stacking linear operations produces another linear operation. Activation functions break this linearity by applying a non-linear transformation to each element of the tensor independently. This is what gives deep networks their extraordinary expressive power: the ability to approximate arbitrary functions, as formalized by the [[multilayer-perceptrons|universal approximation theorem]].

The most widely used activation function in modern deep learning is the Rectified Linear Unit (ReLU), which simply sets negative values to zero and passes positive values unchanged. Despite its simplicity, ReLU resolved the [[backpropagation|vanishing gradient problem]] that had plagued earlier networks using sigmoid or tanh activations. Variants like Leaky ReLU and GELU follow the same philosophy — keep positive values intact while applying different treatments to negative values — and the choice between them is, as Fleuret notes, "generally driven by empirical performance."

A key insight is that the activation function need not be differentiable everywhere. ReLU has a kink at zero where the derivative is undefined, yet [[gradient-descent]] works perfectly well because it only requires that the gradient be "informative on average." [[neural-network-initialization|Proper initialization]] (Glorot/He) ensures that roughly half of all activations are positive at the start of training, keeping gradients flowing through the network.

## Key Details

### Intuition

Think of an activation function as a gate that each neuron passes its signal through. Without gates, signals would just add up linearly — a choir where everyone sings the same note at different volumes. The gates let each neuron decide whether and how strongly to "fire," creating the rich patterns that allow networks to represent complex relationships. ReLU is the simplest useful gate: it lets positive signals through unchanged and blocks negative ones entirely.

### Etymology & History

The term "activation function" comes from the analogy with biological neurons, which either "fire" (activate) or remain silent based on their input. The earliest artificial activation function was the step function in McCulloch and Pitts' 1943 neuron model, which output 1 if the input exceeded a threshold and 0 otherwise. The sigmoid function $\sigma(x) = 1/(1+e^{-x})$ was introduced as a smooth, differentiable alternative and dominated from the 1980s through the 2000s. The ReLU revolution began with Glorot, Bordes, and Bengio (2011) and was cemented by Krizhevsky, Sutskevsky, and Hinton's AlexNet (2012), which used ReLU to train a deep CNN that won ImageNet by a wide margin.

### Activation Function Curves

```plotly
data:
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    name: ReLU
    type: scatter
    mode: lines
    line: {color: "#2196F3", width: 3}
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [0.018, 0.023, 0.0293, 0.0373, 0.0474, 0.0601, 0.0759, 0.0953, 0.1192, 0.148, 0.1824, 0.2227, 0.2689, 0.3208, 0.3775, 0.4378, 0.5, 0.5622, 0.6225, 0.6792, 0.7311, 0.7773, 0.8176, 0.852, 0.8808, 0.9047, 0.9241, 0.9399, 0.9526, 0.9627, 0.9707, 0.977, 0.982]
    name: Sigmoid
    type: scatter
    mode: lines
    line: {color: "#FF9800", width: 2, dash: dot}
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [-0.9993, -0.9989, -0.9982, -0.997, -0.9951, -0.9919, -0.9866, -0.978, -0.964, -0.9414, -0.9051, -0.8483, -0.7616, -0.6351, -0.4621, -0.2449, 0.0, 0.2449, 0.4621, 0.6351, 0.7616, 0.8483, 0.9051, 0.9414, 0.964, 0.978, 0.9866, 0.9919, 0.9951, 0.997, 0.9982, 0.9989, 0.9993]
    name: Tanh
    type: scatter
    mode: lines
    line: {color: "#4CAF50", width: 2, dash: dash}
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [-0.0001, -0.0002, -0.0006, -0.0016, -0.0036, -0.0077, -0.0151, -0.0272, -0.0454, -0.0702, -0.1004, -0.1323, -0.1588, -0.17, -0.1543, -0.1003, 0.0, 0.1497, 0.3457, 0.58, 0.8412, 1.1177, 1.3996, 1.6798, 1.9546, 2.2228, 2.4849, 2.7423, 2.9964, 3.2484, 3.4994, 3.7498, 3.9999]
    name: GELU
    type: scatter
    mode: lines
    line: {color: "#E91E63", width: 3}
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [-0.4, -0.375, -0.35, -0.325, -0.3, -0.275, -0.25, -0.225, -0.2, -0.175, -0.15, -0.125, -0.1, -0.075, -0.05, -0.025, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    name: Leaky ReLU
    type: scatter
    mode: lines
    line: {color: "#9C27B0", width: 2, dash: dashdot}
  - x: [-4.0, -3.75, -3.5, -3.25, -3.0, -2.75, -2.5, -2.25, -2.0, -1.75, -1.5, -1.25, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0, 2.25, 2.5, 2.75, 3.0, 3.25, 3.5, 3.75, 4.0]
    y: [-0.0719, -0.0862, -0.1026, -0.1213, -0.1423, -0.1652, -0.1896, -0.2145, -0.2384, -0.2591, -0.2736, -0.2784, -0.2689, -0.2406, -0.1888, -0.1095, 0.0, 0.1405, 0.3112, 0.5094, 0.7311, 0.9716, 1.2264, 1.4909, 1.7616, 2.0355, 2.3104, 2.5848, 2.8577, 3.1287, 3.3974, 3.6638, 3.9281]
    name: SiLU/Swish
    type: scatter
    mode: lines
    line: {color: "#795548", width: 2}
layout:
  title: Common Activation Functions
  xaxis: {title: x, zeroline: true, zerolinewidth: 1}
  yaxis: {title: f(x), zeroline: true, zerolinewidth: 1}
  legend: {x: 0.02, y: 0.98}
  hovermode: closest
```

> *Requires the [Obsidian Plotly plugin](https://github.com/Dmytro-Shulha/obsidian-plotly). Notice ReLU's sharp kink at 0, sigmoid/tanh saturation for large |x|, and GELU's smooth approximation of ReLU.*

### Activation Function Derivatives

The derivative of the activation function determines how the error signal flows during [[backpropagation]]. Where the derivative is near zero, the gradient vanishes; where it is large, the gradient may explode.

```plotly
data:
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, -0.01, 0.01, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
    name: "ReLU'"
    type: scatter
    mode: lines
    line: {color: "#2196F3", width: 3}
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0.018, 0.028, 0.045, 0.071, 0.105, 0.148, 0.197, 0.217, 0.235, 0.246, 0.250, 0.246, 0.235, 0.217, 0.197, 0.148, 0.105, 0.071, 0.045, 0.028, 0.018]
    name: "Sigmoid'"
    type: scatter
    mode: lines
    line: {color: "#FF9800", width: 2, dash: dot}
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0.001, 0.004, 0.010, 0.026, 0.071, 0.181, 0.420, 0.597, 0.786, 0.940, 1.000, 0.940, 0.786, 0.597, 0.420, 0.181, 0.071, 0.026, 0.010, 0.004, 0.001]
    name: "Tanh'"
    type: scatter
    mode: lines
    line: {color: "#4CAF50", width: 2, dash: dash}
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0.0, 0.001, 0.004, 0.015, 0.046, 0.110, 0.228, 0.321, 0.422, 0.540, 0.500, 0.660, 0.808, 0.917, 0.977, 0.999, 1.000, 1.000, 1.000, 1.000, 1.000]
    name: "GELU'"
    type: scatter
    mode: lines
    line: {color: "#E91E63", width: 3}
layout:
  title: "Activation Function Derivatives"
  xaxis: {title: x, zeroline: true, zerolinewidth: 1}
  yaxis: {title: "f'(x)", zeroline: true, zerolinewidth: 1, range: [-0.05, 1.15]}
  legend: {x: 0.02, y: 0.98}
  hovermode: closest
```

> *Compare: sigmoid's derivative peaks at just 0.25 — each sigmoid layer multiplies the gradient by at most 0.25, causing exponential decay in deep networks. ReLU's derivative is either 0 or 1, avoiding attenuation entirely. GELU transitions smoothly between 0 and 1.*

### Desirable Mathematical Properties

What makes a good activation function? Not all properties can be satisfied simultaneously — different architectures make different trade-offs:

| Property                     | Why it matters                                                                                                             | Functions that satisfy it                                                                     |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Non-linearity**            | Without it, the network collapses to a single linear layer regardless of depth                                             | All (this is the whole point)                                                                 |
| **Non-vanishing gradient**   | Derivatives that stay away from 0 allow the error signal to flow through many layers during [[backpropagation]]            | ReLU (for $x > 0$), Leaky ReLU, GELU, SiLU                                                    |
| **Zero-centered output**     | Outputs centered around 0 prevent systematic bias in the gradients of the next layer's weights, which improves convergence | Tanh, GELU, SiLU (sigmoid and ReLU are not zero-centered)                                     |
| **Bounded output**           | Keeps activations in a fixed range, preventing numerical overflow                                                          | Sigmoid $(0,1)$, Tanh $(-1,1)$ (ReLU is unbounded above)                                      |
| **Monotonicity**             | Ensures one-to-one relationship and stable gradients — the function always increases or stays flat                         | ReLU, Leaky ReLU, Sigmoid, Tanh (GELU and SiLU are non-monotonic: they dip slightly negative) |
| **Smoothness**               | Continuous derivatives enable more stable optimization and are required for some theoretical analyses                      | GELU, SiLU, Sigmoid, Tanh (ReLU has a non-differentiable kink at 0)                           |
| **Computational efficiency** | Faster to compute means faster training and inference                                                                      | ReLU (one comparison), Leaky ReLU (one multiply + comparison)                                 |
| **Sparse activation**        | Many outputs being exactly zero creates a sparse representation, which can improve efficiency and interpretability         | ReLU (outputs exactly 0 for negative inputs)                                                  |

The historical trend has been from bounded, saturating functions (sigmoid → tanh) toward unbounded, non-saturating ones (ReLU → GELU). Modern defaults (GELU for [[attention-and-transformers|Transformers]], ReLU for [[convolutional-neural-networks|CNNs]]) were found empirically — theory can explain why some properties help, but cannot yet predict the best choice for a given architecture.

### ReLU (Rectified Linear Unit)

$$\text{relu}(x) = \begin{cases} 0 & \text{if } x < 0 \\ x & \text{otherwise} \end{cases} = \max(0, x)$$

- **Gradient**: 1 for $x > 0$, 0 for $x < 0$, undefined at $x = 0$ (typically set to 0)
- **Advantages**: simple, fast, no saturation for positive inputs, sparse activation
- **Disadvantage**: "dead neurons" — if a neuron's input is always negative (e.g., due to a large negative bias or an unlucky weight update), ReLU outputs exactly 0 and its gradient is exactly 0, so the neuron receives no error signal and can never recover. In extreme cases, a large learning rate can kill a significant fraction of neurons in a single update
- Introduced by Nair & Hinton (2010), popularized by Glorot et al. (2011)

### Tanh (Hyperbolic Tangent)

$$\tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$

- Output range: $(-1, 1)$, zero-centered
- **Gradient**: $1 - \tanh^2(x)$, approaches 0 for large $|x|$ (saturation)
- Was the standard before ReLU; saturates on both positive and negative sides, aggravating the [[backpropagation|vanishing gradient problem]]
- Still used in specific contexts: as the cell state transform in [[recurrent-neural-networks|LSTM and GRU]] gating mechanisms (where bounded output is needed to control information flow), and in some [[normalization-techniques|normalization]] schemes

### Sigmoid

$$\sigma(x) = \frac{1}{1 + e^{-x}}$$

- Output range: $(0, 1)$ — naturally interpretable as a probability
- **Gradient**: $\sigma(x)(1 - \sigma(x))$, maximum of 0.25 at $x = 0$
- Suffers from [[backpropagation|vanishing gradients]] (max derivative of 0.25) and non-zero-centered outputs
- Now primarily used for binary classification outputs and as the gate activation in [[recurrent-neural-networks|LSTM and GRU]] — where its $(0, 1)$ output range naturally represents "how much to let through" (0 = block, 1 = pass)

### Leaky ReLU

$$\text{leakyrelu}(x) = \begin{cases} ax & \text{if } x < 0 \\ x & \text{otherwise} \end{cases}$$

where $a$ is a small positive constant (typically 0.01).

- Introduced by Maas et al. (2013)
- Avoids dead neurons by allowing a small gradient for negative inputs
- Parametric ReLU (PReLU) learns $a$ as a trainable parameter (He et al., 2015)

### GELU (Gaussian Error Linear Unit)

$$\text{gelu}(x) = x \cdot \Phi(x)$$

where $\Phi(x)$ is the *cumulative distribution function* (CDF) of the standard normal distribution — the probability that a random draw from a bell curve falls below $x$. This probability is near 0 for very negative $x$, exactly 0.5 at $x = 0$, and near 1 for very positive $x$. So GELU multiplies each value by the probability that it is "large": large positive values pass through almost unchanged ($x \cdot 1 \approx x$), large negative values are suppressed ($x \cdot 0 \approx 0$), and values near zero are partially scaled ($x \cdot 0.5$). The result is a smooth, probabilistic version of ReLU's hard threshold.

```plotly
data:
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [-0.0001, -0.0006, -0.0036, -0.0151, -0.0454, -0.1004, -0.1588, -0.17, -0.1543, -0.1003, 0.0, 0.1497, 0.3457, 0.58, 0.8412, 1.3996, 1.9546, 2.4849, 2.9964, 3.4994, 3.9999]
    name: "GELU(x)"
    type: scatter
    mode: lines
    line: {color: "#E91E63", width: 3}
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, 0.0, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0.0, 0.001, 0.004, 0.015, 0.046, 0.110, 0.228, 0.321, 0.422, 0.540, 0.500, 0.660, 0.808, 0.917, 0.977, 0.999, 1.000, 1.000, 1.000, 1.000, 1.000]
    name: "GELU'(x) — derivative"
    type: scatter
    mode: lines
    line: {color: "#E91E63", width: 2, dash: dash}
  - x: [-4.0, -3.5, -3.0, -2.5, -2.0, -1.5, -1.0, -0.75, -0.5, -0.25, -0.01, 0.01, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    y: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.01, 0.25, 0.5, 0.75, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0]
    name: "ReLU(x) — for comparison"
    type: scatter
    mode: lines
    line: {color: "#2196F3", width: 1.5, dash: dot}
layout:
  title: "GELU vs. ReLU: function and derivative"
  xaxis: {title: x, zeroline: true, zerolinewidth: 1}
  yaxis: {title: "", zeroline: true, zerolinewidth: 1}
  legend: {x: 0.02, y: 0.98}
  hovermode: closest
  annotations:
    - x: -1.0
      y: -0.17
      text: "slight negative dip<br>(non-monotonic)"
      showarrow: true
      arrowhead: 2
      ax: -40
      ay: -40
      font: {size: 10}
    - x: 1.5
      y: 0.999
      text: "derivative ≈ 1<br>(gradient flows freely)"
      showarrow: true
      arrowhead: 2
      ax: 40
      ay: -30
      font: {size: 10}
```

> *GELU (solid) vs. ReLU (dotted): GELU smoothly transitions where ReLU has a hard kink. The dashed line shows GELU's derivative — it rises smoothly from 0 to 1, meaning the gradient transitions gradually rather than jumping from "fully blocked" to "fully passed." The slight negative dip around $x = -1$ is the non-monotonic region.*

- Introduced by Hendrycks and Gimpel (2016)
- The default activation in [[attention-and-transformers\|Transformer]] architectures (BERT, GPT, ViT)
- In practice, the CDF is not computed directly. Instead, a fast approximation is used: $\text{gelu}(x) \approx 0.5x(1 + \tanh[\sqrt{2/\pi}(x + 0.044715x^3)])$

### SiLU / Swish

$$\text{silu}(x) = x \cdot \sigma(x)$$

- Discovered through automated search by Ramachandran et al. (2017)
- Very similar to GELU in practice
- Used in some vision models (EfficientNet — found via [[neural-architecture-search]])

### Choosing an Activation Function

| Architecture | Typical Choice | Reasoning |
|---|---|---|
| [[convolutional-neural-networks\|CNNs]] (ResNets) | ReLU | Simple, well-tested, works with [[normalization-techniques\|batch norm]] |
| [[attention-and-transformers\|Transformers]] | GELU | Smooth, empirically better for attention models |
| [[recurrent-neural-networks\|LSTMs/GRUs]] | Tanh + Sigmoid | Tanh for cell state, sigmoid for gates |
| Output ([[loss-functions\|classification]]) | [[loss-functions\|Softmax]] | Converts logits to a probability distribution over classes |
| Output (binary classification) | Sigmoid | Outputs a single probability in $(0, 1)$ |
| Output ([[loss-functions\|regression]]) | None (identity) | Unrestricted output range for predicting continuous values |

### Initialization Interaction

The choice of activation function determines the correct [[neural-network-initialization|weight initialization]] — the goal is to keep both activations and gradients at a stable magnitude across layers at the start of training:
- **Sigmoid/Tanh**: Xavier initialization, $W \sim \mathcal{N}(0, 1/D_{in})$ (Glorot & Bengio, 2010) — assumes the activation preserves variance (approximately true for tanh near zero)
- **ReLU**: He initialization, $W \sim \mathcal{N}(0, 2/D_{in})$ (He et al., 2015) — the factor of 2 compensates for ReLU zeroing out roughly half the activations, which halves the variance

## Learn

- [Activation Function Explorer](../teach/activation-functions/index.html) — interactive: drag along curves to probe function values and derivatives, compare any two functions, and stack layers to see how repeated activation crushes (sigmoid) or preserves (ReLU) signals

## Connections

- [[backpropagation]] — activation derivatives determine how the error signal flows backward; saturating activations (sigmoid, tanh) cause vanishing gradients
- [[multilayer-perceptrons]] — activation functions between linear layers are what make MLPs non-linear and enable universal approximation
- [[attention-and-transformers]] — use GELU in feed-forward blocks
- [[convolutional-neural-networks]] — typically use ReLU after each convolution
- [[recurrent-neural-networks]] — LSTM and GRU use sigmoid as gate activations and tanh for cell state transforms
- [[neural-network-initialization]] — the activation function determines the correct initialization scale (Xavier for tanh, He for ReLU)
- [[normalization-techniques]] — batch norm and layer norm interact with activation functions to stabilize gradient flow
- [[loss-functions]] — softmax (used as the output activation for classification) connects to cross-entropy loss

## Sources

- Glorot, X., Bordes, A. & Bengio, Y. (2011). "Deep Sparse Rectifier Neural Networks." *AISTATS*.
- Hendrycks, D. & Gimpel, K. (2016). "Gaussian Error Linear Units (GELUs)." arXiv:1606.08415.
- Maas, A., Hannun, A. & Ng, A. (2013). "Rectifier Nonlinearities Improve Neural Network Acoustic Models." *ICML Workshop*.
- Fleuret, F. (2023). *The Little Book of Deep Learning*. Chapter 4.3.

## Open Questions

- Is there a principled way to choose or learn the optimal activation function for a given task?
- Why does GELU work better than ReLU in transformers — is it the smoothness, the probabilistic interpretation, or something else?
- Could non-monotonic activation functions offer advantages for certain problems?
- Are there activation functions better suited to quantized / low-precision computation?
