# Glossary of Deep Learning Terms

> Quick definitions for the jargon that appears across this knowledge base — terms common enough to encounter everywhere but too small for their own article.

## A

| Term | Definition |
|------|-----------|
| **Ablation study** | An experiment where you remove or disable one component of a system at a time to measure its contribution. "Ablating the skip connections drops accuracy by 4%." |
| **Argmax** | "The argument of the maximum" — returns the *index* (not the value) of the largest element. $\arg\max_c [0.2, 0.7, 0.1] = 1$ (index 1 has value 0.7). From Latin *argumentum* (input). Softmax is the smooth, differentiable approximation of argmax. |
| **Attention head** | One parallel instance of the attention mechanism inside a multi-head attention layer. Each head learns to attend to different relationships in the data. See [[attention-and-transformers]]. |

## B

| Term | Definition |
|------|-----------|
| **Backbone** | The main feature-extraction portion of a model, typically pre-trained, onto which task-specific layers are attached. A ResNet backbone with a detection head, for example. See [[transfer-learning]]. |
| **Batch** | The full set of training examples used to compute one gradient update. In practice, people often say "batch" when they mean *mini-batch*. |
| **Batch size** | The number of examples processed together in one forward/backward pass. Larger batches give more stable gradient estimates but use more memory. |
| **Beam search** | A decoding strategy that keeps the top-$k$ most likely partial sequences at each step, trading speed for better output quality than greedy decoding. See [[autoregressive-models]]. |
| **BLEU** | Bilingual Evaluation Understudy — a metric for machine translation quality that measures n-gram overlap between generated and reference text. |

## C

| Term | Definition |
|------|-----------|
| **Checkpoint** | A saved snapshot of a model's parameters (and often optimizer state) at a particular point during training, used for recovery or later fine-tuning. |
| **Classifier head** | A small network (often a single linear layer + softmax) appended to a backbone to produce class predictions. Swapping the head allows reusing the same backbone for different tasks. See [[transfer-learning]]. |
| **Contrastive loss** | A family of loss functions that pull representations of similar examples together and push dissimilar ones apart. See [[energy-based-models-and-contrastive-learning]]. |
| **Convergence** | The point during training where the loss stops meaningfully decreasing and the model's parameters stabilize. |
| **Cybernetics** | The study of feedback, control, and communication in machines and living organisms, founded by Norbert Wiener (1948). The intellectual parent of neural networks — McCulloch-Pitts neurons, the Perceptron, and Hebbian learning all emerged from the cybernetics community. The field fragmented in the 1960s into AI, control theory, and neuroscience, but its core idea — systems that learn by adjusting themselves based on feedback — is exactly what deep learning does. |
| **Cross-entropy** | The dominant classification loss function. The "cross" means *between two distributions* — it measures the cost of using the model's predicted distribution $q$ to represent data that actually follows the true distribution $p$. Equals the true entropy $H(p)$ plus the KL divergence $D_{KL}(p \| q)$, so minimizing cross-entropy = making predictions match reality. From [[information-theory]]. See [[loss-functions]]. |
| **Cross-validation** | An evaluation method where the dataset is split into $k$ folds; the model trains on $k{-}1$ folds and validates on the remaining one, rotating through all folds. |

## D

| Term | Definition |
|------|-----------|
| **Decoder** | The part of a model that maps a latent or encoded representation back to the output space (e.g., generating text token-by-token or reconstructing an image). See [[autoencoders]], [[attention-and-transformers]]. |
| **Downstream task** | A specific task (classification, summarization, etc.) that a pre-trained model is adapted to, as opposed to the generic pre-training objective. |

## E

| Term | Definition |
|------|-----------|
| **Embedding** | A learned dense vector representation that maps discrete items (words, tokens, categories) into continuous space where similar items are nearby. See [[embeddings-and-representation-learning]]. |
| **Encoder** | The part of a model that maps raw input into a compressed internal representation. BERT is an encoder-only model; a VAE has an encoder that maps images to latent vectors. See [[autoencoders]], [[attention-and-transformers]]. |
| **End-to-end** | Training a system from raw input to final output as a single differentiable model, rather than pipelining separately optimized components. |
| **Epoch** | One complete pass through the entire training dataset. Training for 10 epochs means the model sees every example 10 times. |

## F

| Term | Definition |
|------|-----------|
| **Feature map** | The output of a convolutional layer — a spatial grid of learned feature activations. A layer with 64 filters produces 64 feature maps. See [[convolutional-neural-networks]]. |
| **Few-shot** | Providing a small number of labeled examples (typically 1–32) to a model, either as training data or in-context demonstrations. See [[few-shot-and-zero-shot-learning]]. |
| **Fine-tuning** | Continuing training of a pre-trained model on a smaller, task-specific dataset, typically with a lower learning rate. See [[transfer-learning]], [[training-techniques]]. |
| **FLOP / FLOPS** | Floating-point operation (FLOP) vs. floating-point operations per second (FLOPS). Model cost is measured in FLOPs; hardware speed in FLOPS. A GPT-3 training run uses ~$3.6 \times 10^{23}$ FLOPs. |
| **Frozen layers** | Layers whose parameters are held fixed (not updated by the optimizer) during training, often used when fine-tuning only the head of a pre-trained model. See [[transfer-learning]]. |

## G

| Term | Definition |
|------|-----------|
| **Gradient clipping** | Capping the gradient magnitude before an optimizer step to prevent exploding gradients. Common in RNN and Transformer training. See [[training-techniques]]. |
| **Ground truth** | The correct, known label or target for a given input — the $y$ in a $(x, y)$ training pair. |

## H

| Term | Definition |
|------|-----------|
| **Hallucination** | When a generative model produces confident but factually incorrect output. Particularly studied in LLMs. See [[large-language-models]]. |
| **Hidden layer** | Any layer between the input and output layers of a network. The "deep" in deep learning refers to having many hidden layers. |
| **Hyperparameter** | A setting chosen before training begins (learning rate, batch size, number of layers) as opposed to a *parameter* learned during training (weights, biases). See [[hyperparameter-optimization]]. |

## I

| Term | Definition |
|------|-----------|
| **Inference** | Using a trained model to make predictions on new data, as opposed to training it. Also called "forward pass" or "prediction." See [[inference-optimization]]. |
| **In-distribution / Out-of-distribution (OOD)** | Data that resembles the training set (in-distribution) vs. data drawn from a different distribution (OOD). Models often fail silently on OOD inputs. |

## K

| Term | Definition |
|------|-----------|
| **Kernel (convolution)** | A small matrix of learnable weights that slides across the input to produce a feature map. A $3 \times 3$ kernel looks at 9 neighboring values at each position. See [[convolutional-neural-networks]]. |
| **KV-cache** | During autoregressive generation, caching previously computed key and value tensors so each new token only requires one new attention computation rather than reprocessing the entire sequence. See [[inference-optimization]]. |

## L

| Term | Definition |
|------|-----------|
| **Latent space** | The internal, typically lower-dimensional representation space that a model maps inputs into. Points nearby in latent space represent semantically similar inputs. See [[autoencoders]]. |
| **Logits** | The raw, unnormalized output scores of a model before softmax is applied. For a 10-class classifier, the logits are a 10-dimensional vector; softmax converts them to probabilities. |
| **LoRA** | Low-Rank Adaptation — a parameter-efficient fine-tuning method that injects small trainable matrices into frozen layers rather than updating all weights. See [[training-techniques]]. |

## M

| Term | Definition |
|------|-----------|
| **Mini-batch** | A subset of the training data (e.g., 32 or 256 examples) used to compute an approximate gradient update. Standard practice in SGD — full-batch training is rare. See [[gradient-descent]]. |
| **Mixed precision** | Training with both 16-bit and 32-bit floating-point numbers — 16-bit for speed and memory, 32-bit for numerically sensitive operations like loss accumulation. See [[gpu-and-accelerator-hardware]]. |

## N

| Term | Definition |
|------|-----------|
| **Null / baseline model** | The simplest possible model for a task (random guessing, always predicting the mean, majority class) used as a lower bound on performance. |

## O

| Term | Definition |
|------|-----------|
| **One-hot encoding** | Representing a categorical value as a binary vector with a single 1 and all other entries 0. Class 3 out of 5 classes becomes $[0, 0, 1, 0, 0]$. |
| **Overfitting** | When a model memorizes training data rather than learning general patterns, resulting in low training loss but poor performance on unseen data. See [[regularization]], [[generalization-theory]]. |

## P

| Term | Definition |
|------|-----------|
| **Padding** | Adding zeros (or other values) around the border of an input tensor so that convolution or attention operations produce the desired output size. |
| **Parameter count** | The total number of learnable weights in a model. GPT-3 has 175B parameters; a small ResNet has ~25M. |
| **Perplexity** | A language model evaluation metric: $2^{H}$ where $H$ is the cross-entropy loss. Lower is better. A perplexity of 20 means the model is, on average, as uncertain as choosing uniformly among 20 options. |
| **Pooling** | A downsampling operation that reduces spatial dimensions — max pooling takes the maximum value in each window; average pooling takes the mean. See [[convolutional-neural-networks]]. |
| **Pre-training** | The initial phase of training on a large, general dataset (e.g., internet text or ImageNet) before fine-tuning on a specific task. See [[training-techniques]], [[language-model-pretraining]]. |

## Q

| Term | Definition |
|------|-----------|
| **Query / Key / Value (Q, K, V)** | The three projections used in the attention mechanism. The query asks "what am I looking for?", keys say "what do I contain?", and the dot product between them determines how much each value contributes. See [[attention-and-transformers]]. |

## R

| Term | Definition |
|------|-----------|
| **Receptive field** | The region of the input that influences a particular neuron's activation. Deeper layers in a CNN have larger receptive fields. See [[convolutional-neural-networks]]. |
| **Representation** | The internal activations or feature vectors a model produces at intermediate layers. Good representations capture structure useful for downstream tasks. |

## S

| Term | Definition |
|------|-----------|
| **Softmax** | The function $\exp(z_c) / \sum \exp(z_j)$ that converts a vector of raw scores (logits) into a probability distribution. The name means "soft argmax" — argmax is "hard" (returns 1 for the winner, 0 for all others), while softmax is a smooth, differentiable approximation that approaches argmax as temperature $T \to 0$. Named by John Bridle (1990). See [[loss-functions]]. |
| **SOTA** | State of the art — the best known performance on a benchmark at a given time. "This method achieves SOTA on ImageNet." |
| **Stride** | The step size when sliding a kernel or pooling window across the input. Stride 2 means the window moves 2 positions each step, halving the spatial dimensions. See [[convolutional-neural-networks]]. |
| **Supervised / Unsupervised / Self-supervised** | Supervised: training with labeled data $(x, y)$. Unsupervised: finding structure without labels. Self-supervised: generating labels from the data itself (e.g., predicting masked tokens). See [[self-supervised-learning]]. |

## T

| Term | Definition |
|------|-----------|
| **Teacher forcing** | Training a sequence model by feeding the ground-truth previous token (rather than its own prediction) at each step. Speeds convergence but can cause exposure bias at inference time. |
| **Temperature** | A scalar that sharpens or flattens a probability distribution. Dividing logits by $T > 1$ before softmax makes the output more uniform (more random); $T < 1$ makes it peakier (more deterministic). |
| **Token** | The atomic unit a language model operates on — typically a subword piece, not a whole word. "unhappiness" might become ["un", "happiness"] or ["un", "happi", "ness"]. See [[tokenization]]. |
| **Top-k / Top-p sampling** | Decoding strategies that restrict token selection to the $k$ most probable tokens (top-k) or the smallest set whose cumulative probability exceeds $p$ (top-p / nucleus sampling). See [[autoregressive-models]]. |

## U

| Term | Definition |
|------|-----------|
| **Underfitting** | When a model is too simple or insufficiently trained to capture the patterns in the data, resulting in high error on both training and test sets. |
| **Upstream task** | The general pre-training task (e.g., next-token prediction, masked language modeling) that a foundation model is trained on before adaptation to downstream tasks. |

## W

| Term | Definition |
|------|-----------|
| **Warm-up** | Gradually increasing the learning rate from near-zero during the first few hundred or thousand steps of training, preventing early instability. See [[optimization-beyond-sgd]]. |
| **Weight decay** | A regularization technique that adds a penalty proportional to the magnitude of the weights, encouraging smaller parameter values. Equivalent to L2 regularization in SGD; slightly different in Adam (AdamW). See [[regularization]]. |

## Z

| Term | Definition |
|------|-----------|
| **Zero-shot** | Using a model on a task it was never explicitly trained on, relying solely on its pre-trained knowledge and a natural-language description of the task. See [[few-shot-and-zero-shot-learning]]. |
