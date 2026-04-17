# Key People in Deep Learning

> A reference for the researchers whose work appears repeatedly across this knowledge base — organized by area of contribution.

## Foundations and Early Neural Networks

| Person | Contributions |
|--------|---------------|
| **Warren McCulloch & Walter Pitts** | Proposed the first mathematical model of an artificial neuron (1943) — a binary threshold unit that established the computational metaphor for neural networks. [[multilayer-perceptrons]] |
| **Frank Rosenblatt** | Invented the Perceptron (1958), the first trainable neural network, with a learning rule that provably converges for linearly separable data. [[multilayer-perceptrons]], [[gradient-descent]] |
| **Marvin Minsky & Seymour Papert** | Published *Perceptrons* (1969), proving the single-layer perceptron cannot learn XOR — triggering the first "AI winter" for neural networks. [[multilayer-perceptrons]] |
| **Paul Werbos** | First described backpropagation for neural networks in his 1974 PhD thesis, years before it gained widespread attention. [[backpropagation]] |

## Backpropagation and the Connectionist Revival

| Person | Contributions |
|--------|---------------|
| **David Rumelhart, Geoffrey Hinton & Ronald Williams** | Popularized backpropagation (1986) with clear derivation and compelling experiments, igniting the connectionist revolution. [[backpropagation]], [[gradient-descent]] |
| **Geoffrey Hinton** | Decades of foundational work: Boltzmann machines, backpropagation, deep belief networks (2006 pre-training breakthrough), dropout, knowledge distillation, capsule networks. 2024 Nobel Prize in Physics. [[backpropagation]], [[regularization]], [[knowledge-distillation]], [[autoencoders]] |
| **Yann LeCun** | Invented convolutional neural networks (LeNet, 1989), pioneered handwriting recognition, and championed self-supervised learning (JEPA). 2018 Turing Award (with Hinton and Bengio). [[convolutional-neural-networks]], [[image-classification-milestones]], [[self-supervised-learning]], [[world-models-and-predictive-learning]] |
| **Yoshua Bengio** | Demonstrated the difficulty of learning long-term dependencies (1994), introduced neural language models and word embeddings (2003), and championed deep learning through the 2000s "AI winter." 2018 Turing Award. [[recurrent-neural-networks]], [[embeddings-and-representation-learning]], [[language-model-pretraining]], [[generalization-theory]] |

## Recurrent Networks and Sequence Modeling

| Person | Contributions |
|--------|---------------|
| **Sepp Hochreiter** | Co-invented LSTM (1997, with Schmidhuber), solving the vanishing gradient problem for recurrent networks. Later contributed the lottery ticket-adjacent flat minima analysis and Sharpness-Aware Minimization ideas. [[recurrent-neural-networks]], [[loss-landscape-geometry]] |
| **Jurgen Schmidhuber** | Co-invented LSTM (1997), early work on meta-learning (1987), self-referential networks, and world models. Prolific contributor to sequence modeling and learning-to-learn. [[recurrent-neural-networks]], [[meta-learning]], [[world-models-and-predictive-learning]] |
| **Alex Graves** | Extended LSTMs with attention (2014), connectionist temporal classification (CTC), and Neural Turing Machines — bridging recurrent networks and memory-augmented architectures. [[recurrent-neural-networks]], [[attention-and-transformers]], [[speech-recognition-deep-dive]] |

## Attention and Transformers

| Person | Contributions |
|--------|---------------|
| **Dzmitry Bahdanau** | Introduced the attention mechanism for neural machine translation (2015) — the direct precursor to Transformer self-attention. [[attention-and-transformers]], [[nlp-tasks]] |
| **Ashish Vaswani et al.** | "Attention Is All You Need" (2017) — introduced the Transformer architecture (self-attention, multi-head attention, positional encoding), arguably the most influential deep learning paper. [[attention-and-transformers]], [[positional-encoding]], [[large-language-models]] |

## Computer Vision

| Person | Contributions |
|--------|---------------|
| **Alex Krizhevsky** | AlexNet (2012) — won ImageNet with a deep CNN using ReLU, dropout, and GPU training, launching the modern deep learning era. [[image-classification-milestones]], [[convolutional-neural-networks]], [[activation-functions]] |
| **Karen Simonyan & Andrew Zisserman** | VGGNet (2014) — demonstrated that depth with small 3x3 filters is key, establishing the design pattern for deep CNNs. [[image-classification-milestones]], [[convolutional-neural-networks]] |
| **Christian Szegedy** | GoogLeNet/Inception (2014) — introduced multi-scale processing and efficient architecture design; also discovered adversarial examples (2013). [[image-classification-milestones]], [[adversarial-robustness]] |
| **Kaiming He** | ResNet (2015) — skip connections enabling 100+ layer training; also He initialization, Mask R-CNN, and MAE (masked autoencoders for vision). [[skip-connections]], [[image-classification-milestones]], [[neural-network-initialization]], [[semantic-segmentation]], [[self-supervised-learning]] |
| **Ross Girshick** | Pioneered the R-CNN family (R-CNN, Fast R-CNN, Faster R-CNN) for object detection, defining the two-stage detection paradigm. [[object-detection]], [[semantic-segmentation]] |
| **Joseph Redmon** | Created YOLO (2016) — single-shot real-time object detection, fundamentally changing the speed-accuracy trade-off. [[object-detection]] |
| **Alexey Dosovitskiy** | Vision Transformer (ViT, 2020) — proved that pure Transformer attention can replace convolutions for image classification when trained at scale. [[image-classification-milestones]], [[attention-and-transformers]] |
| **Alexander Kirillov et al.** | Segment Anything Model (SAM, 2023) — a promptable foundation model for image segmentation, analogous to the foundation model paradigm in NLP. [[semantic-segmentation]] |

## Generative Models

| Person | Contributions |
|--------|---------------|
| **Ian Goodfellow** | Invented Generative Adversarial Networks (GANs, 2014) — the adversarial training framework that dominated image generation for years. Also contributed to adversarial robustness (FGSM). [[generative-adversarial-networks]], [[adversarial-robustness]] |
| **Diederik P. Kingma** | Co-invented both Variational Autoencoders (VAE, 2013) and the Adam optimizer (2014) — two of the most widely used tools in deep learning. [[autoencoders]], [[optimization-beyond-sgd]] |
| **Tero Karras** | StyleGAN series (2018-2024) — progressive growing, style-based generators, and the pinnacle of GAN image quality. [[generative-adversarial-networks]] |
| **Jonathan Ho** | DDPM (2020) — demonstrated that diffusion models can generate high-quality images, launching the diffusion revolution. Co-authored classifier-free guidance. [[diffusion-models]], [[text-to-image-generation]] |
| **Yang Song** | Score-based generative modeling — unified diffusion and score matching into a continuous-time framework (Score SDE). [[diffusion-models]], [[neural-odes-and-continuous-models]] |
| **Robin Rombach** | Latent Diffusion / Stable Diffusion (2022) — applying diffusion in a compressed VAE latent space, making high-resolution generation practical. [[diffusion-models]], [[text-to-image-generation]], [[autoencoders]] |
| **Aditya Ramesh** | DALL-E (2021) and DALL-E 2 (2022) — pioneering text-to-image generation combining CLIP embeddings with diffusion. [[text-to-image-generation]], [[multimodal-models]] |

## Language Models and NLP

| Person | Contributions |
|--------|---------------|
| **Tomas Mikolov** | Word2Vec (2013) — efficient word embeddings that demonstrated linear semantic arithmetic ("king - man + woman = queen"). [[embeddings-and-representation-learning]], [[language-model-pretraining]] |
| **Alec Radford** | Lead author on GPT (2018) and GPT-2 (2019) at OpenAI — demonstrated that unsupervised language model pre-training produces powerful general-purpose representations. Also co-authored CLIP and Whisper. [[large-language-models]], [[language-model-pretraining]], [[self-supervised-learning]], [[multimodal-models]], [[speech-recognition-deep-dive]] |
| **Jacob Devlin** | BERT (2018) — masked language modeling with bidirectional Transformers, dominating NLP benchmarks and establishing the pre-train/fine-tune paradigm. [[language-model-pretraining]], [[self-supervised-learning]], [[nlp-tasks]] |
| **Colin Raffel** | T5 (2019) — unified NLP tasks as text-to-text, systematically comparing pre-training objectives and establishing the encoder-decoder approach. [[language-model-pretraining]], [[instruction-tuning-and-multi-task-learning]] |
| **Hugo Touvron** | LLaMA (2023) — Meta's open-weight language model series that catalyzed the open-source LLM ecosystem. [[large-language-models]], [[scaling-laws]] |
| **Jason Wei** | Chain-of-thought prompting (2022) and FLAN instruction tuning — demonstrated that prompting strategy dramatically affects LLM reasoning capabilities. [[reasoning-in-llms]], [[prompt-engineering-and-in-context-learning]], [[instruction-tuning-and-multi-task-learning]] |

## Optimization and Training

| Person | Contributions |
|--------|---------------|
| **Sergey Ioffe & Christian Szegedy** | Batch Normalization (2015) — stabilizing training by normalizing activations, enabling higher learning rates and deeper networks. [[normalization-techniques]], [[regularization]] |
| **Jimmy Lei Ba** | Layer Normalization (2016, with Hinton) — the normalization variant that became standard in Transformers, applied per-example rather than per-batch. [[normalization-techniques]], [[attention-and-transformers]] |
| **Xavier Glorot** | Xavier initialization (2010, with Bengio) — variance-preserving initialization that enabled training of deeper networks before batch norm. [[neural-network-initialization]] |
| **Jared Kaplan et al.** | Neural scaling laws (2020) — empirical power-law relationships between model size, data, compute, and loss that guide training decisions at scale. [[scaling-laws]] |
| **Jordan Hoffmann et al.** | Chinchilla scaling (2022) — showed that most LLMs were undertrained relative to their size, establishing compute-optimal data-to-parameter ratios. [[scaling-laws]], [[language-model-pretraining]] |

## Efficient Architectures and Inference

| Person | Contributions |
|--------|---------------|
| **Tri Dao** | Flash Attention (2022-2024) — hardware-aware exact attention algorithm exploiting GPU memory hierarchy for 2-4x speedup, enabling long-context models. [[efficient-attention-variants]], [[hardware-software-co-design]], [[inference-optimization]] |
| **Mingxing Tan & Quoc V. Le** | EfficientNet (2019) — compound scaling via NAS, establishing the principle of balanced depth/width/resolution scaling. [[neural-architecture-search]], [[image-classification-milestones]] |
| **Noam Shazeer** | Multi-query attention, Mixture of Experts routing innovations (Switch Transformer), SwiGLU activation, and co-authored the original Transformer paper. [[efficient-attention-variants]], [[mixture-of-experts]], [[activation-functions]], [[attention-and-transformers]] |

## State Space Models

| Person | Contributions |
|--------|---------------|
| **Albert Gu** | S4 (2021) and Mamba (2023, with Tri Dao) — structured state space models that process sequences in linear time while maintaining parallelism, the primary Transformer challenger. [[state-space-models]], [[efficient-attention-variants]] |

## Self-Supervised and Contrastive Learning

| Person | Contributions |
|--------|---------------|
| **Ting Chen** | SimCLR (2020) — simple contrastive learning framework demonstrating that data augmentation and projection heads are key ingredients for visual self-supervised learning. [[self-supervised-learning]], [[energy-based-models-and-contrastive-learning]], [[data-augmentation]] |
| **Mathilde Caron** | DINO and DINOv2 — self-supervised Vision Transformer training via self-distillation, producing features that rival or exceed supervised pre-training. [[self-supervised-learning]], [[knowledge-distillation]] |

## Reinforcement Learning and Alignment

| Person | Contributions |
|--------|---------------|
| **Richard Sutton** | Co-author of the foundational RL textbook; formulated the "bitter lesson" — that general methods leveraging computation outperform methods leveraging human knowledge. [[reinforcement-learning]] |
| **David Silver** | Lead on AlphaGo, AlphaZero, and MuZero at DeepMind — demonstrating superhuman game play through deep RL and self-play. [[reinforcement-learning]], [[world-models-and-predictive-learning]] |
| **Volodymyr Mnih** | DQN (2013) — deep Q-networks playing Atari from pixels, launching the deep reinforcement learning era. [[reinforcement-learning]] |
| **John Schulman** | PPO (2017) — the workhorse RL algorithm for both game-playing agents and RLHF alignment of language models. [[reinforcement-learning]], [[reward-modeling-and-rlhf]], [[ai-safety-and-alignment]] |
| **Rafael Rafailov** | DPO (2023) — Direct Preference Optimization, eliminating the need for an explicit reward model in RLHF by reparameterizing the objective. [[reward-modeling-and-rlhf]], [[ai-safety-and-alignment]] |

## Scientific Applications

| Person | Contributions |
|--------|---------------|
| **John Jumper & Demis Hassabis** | AlphaFold2 (2021) — solved the protein structure prediction problem with the Evoformer architecture, winning the 2024 Nobel Prize in Chemistry. [[protein-and-molecular-deep-learning]], [[attention-and-transformers]] |

## Interpretability

| Person | Contributions |
|--------|---------------|
| **Chris Olah** | Pioneered feature visualization, circuits-based interpretability, and the mechanistic interpretability research program (induction heads, superposition). [[interpretability]], [[mechanistic-interpretability]] |

## Information Theory Foundations

| Person | Contributions |
|--------|---------------|
| **Claude Shannon** | Founded information theory (1948) — entropy, mutual information, channel capacity — providing the mathematical language for cross-entropy loss, KL divergence, and compression-based generalization theory. [[information-theory]], [[loss-functions]] |

---

*~40 entries across 14 areas | Names that shaped the field from McCulloch-Pitts neurons (1943) to Mamba (2023)*
