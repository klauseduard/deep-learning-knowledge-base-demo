# Timeline of Deep Learning

> "Those who cannot remember the past are condemned to repeat it — including the AI winters." — loosely after George Santayana

A chronological reference of the key milestones that shaped deep learning from early theory to modern frontier models. Entries link to [[concept articles]] where relevant.

## 1940s–1960s: Foundations

| Year | Milestone | Significance |
|------|-----------|--------------|
| 1943 | **McCulloch–Pitts neuron** (Warren McCulloch, Walter Pitts) | First mathematical model of an artificial neuron, proving that networks of simple threshold units can compute any logical function. Emerged from the **cybernetics** movement — Norbert Wiener's interdisciplinary study of feedback, control, and communication in machines and biological systems, which provided the intellectual context for all early neural network research. |
| 1958 | **Perceptron** (Frank Rosenblatt) | First trainable neural network with a learning rule — demonstrated that a machine could learn from data, not just follow programmed rules. |
| 1969 | **"Perceptrons" book** (Marvin Minsky, Seymour Papert) | Proved single-layer perceptrons cannot learn XOR, triggering the first AI winter by discouraging neural network research for over a decade. |

## 1970s–1980s: The Backpropagation Era

| Year | Milestone | Significance |
|------|-----------|--------------|
| 1980 | **Neocognitron** (Kunihiko Fukushima) | Introduced the hierarchical convolutional architecture with local receptive fields — the direct ancestor of [[convolutional-neural-networks]]. |
| 1986 | **[[Backpropagation]] popularized** (David Rumelhart, Geoffrey Hinton, Ronald Williams) | Made training [[multilayer-perceptrons]] practical by showing how to efficiently compute gradients layer-by-layer via the chain rule. |
| 1989 | **Universal approximation theorem** (George Cybenko; Kurt Hornik et al.) | Proved that a single hidden-layer network with enough neurons can approximate any continuous function — the theoretical foundation for [[multilayer-perceptrons]]. |
| 1989 | **LeNet** (Yann LeCun et al.) | First successful application of backpropagation to [[convolutional-neural-networks]], deployed at scale for handwritten digit recognition at AT&T. |

## 1990s: Sequences and the Second Winter

| Year | Milestone | Significance |
|------|-----------|--------------|
| 1991 | **Vanishing gradient problem identified** (Sepp Hochreiter) | Explained why deep networks and [[recurrent-neural-networks]] fail to learn long-range dependencies — gradients shrink exponentially through layers. |
| 1997 | **Long Short-Term Memory (LSTM)** (Sepp Hochreiter, Jürgen Schmidhuber) | Gated [[recurrent-neural-networks]] architecture that solved the vanishing gradient problem for sequences, dominating sequential modeling for two decades. |
| 1998 | **LeNet-5 + MNIST benchmark** (Yann LeCun et al.) | Established the first standard benchmark for [[convolutional-neural-networks]] and the train/test evaluation paradigm still used today. |

## 2000s: The Deep Learning Precursors

| Year | Milestone | Significance |
|------|-----------|--------------|
| 2003 | **Neural language model** (Yoshua Bengio et al.) | Introduced learned word [[embeddings-and-representation-learning|embeddings]] and showed neural networks could model language — the seed of all modern [[large-language-models]]. |
| 2006 | **Deep Belief Networks** (Geoffrey Hinton et al.) | Demonstrated that deep networks could be pre-trained layer-by-layer with unsupervised learning, reigniting interest in deep architectures and ending the second AI winter. |

## 2010s: The Deep Learning Revolution

| Year | Milestone | Significance |
|------|-----------|--------------|
| 2012 | **AlexNet wins ImageNet** (Alex Krizhevsky, Ilya Sutskever, Geoffrey Hinton) | [[Convolutional-neural-networks]] trained on GPUs crushed traditional computer vision by 10+ percentage points — the moment deep learning went mainstream. See [[image-classification-milestones]]. |
| 2013 | **Word2Vec** (Tomas Mikolov et al.) | Efficient training of word [[embeddings-and-representation-learning|embeddings]] that captured semantic relationships ("king − man + woman = queen"), making distributed representations practical for NLP. |
| 2013 | **Variational Autoencoders (VAEs)** (Diederik Kingma, Max Welling) | Combined deep learning with Bayesian inference for principled generative modeling — the first practical deep [[autoencoders|generative model]] with a latent space. |
| 2014 | **Generative Adversarial Networks** (Ian Goodfellow et al.) | Introduced adversarial training where a generator and discriminator compete, producing strikingly realistic images — launched the field of deep generative modeling. See [[generative-adversarial-networks]]. |
| 2014 | **Sequence-to-sequence + attention** (Ilya Sutskever et al.; Dzmitry Bahdanau et al.) | Encoder-decoder [[recurrent-neural-networks]] with attention enabled neural machine translation to surpass phrase-based systems — attention became the key primitive for [[attention-and-transformers]]. |
| 2014 | **Dropout** (Nitish Srivastava et al.) | Simple [[regularization]] technique — randomly zeroing neurons during training — that dramatically reduced overfitting and became standard practice. |
| 2015 | **ResNet** (Kaiming He et al.) | [[Skip-connections]] enabled training of 152-layer networks, winning ImageNet with superhuman accuracy — proved that depth matters when gradient flow is preserved. See [[image-classification-milestones]]. |
| 2015 | **Batch Normalization** (Sergey Ioffe, Christian Szegedy) | Normalizing activations between layers stabilized training and allowed much higher learning rates — a key [[normalization-techniques|normalization technique]] that accelerated the entire field. |
| 2015 | **Deep Q-Network (DQN) plays Atari** (Volodymyr Mnih et al., DeepMind) | Combined deep [[convolutional-neural-networks]] with [[reinforcement-learning]], learning to play 49 Atari games from raw pixels at superhuman level. |
| 2016 | **AlphaGo defeats Lee Sedol** (David Silver et al., DeepMind) | Deep [[reinforcement-learning]] with Monte Carlo tree search beat a world champion at Go — a game long considered too complex for AI, catalyzing massive investment in the field. |
| 2017 | **Transformer architecture** (Ashish Vaswani et al., Google) | "Attention Is All You Need" replaced recurrence with self-[[attention-and-transformers|attention]], enabling full parallelism — became the dominant architecture for language, vision, and beyond. |
| 2018 | **BERT** (Jacob Devlin et al., Google) | Masked [[language-model-pretraining|language model pretraining]] on unlabeled text, then fine-tuning on downstream tasks — established the pretrain/fine-tune paradigm for NLP. See [[self-supervised-learning]]. |
| 2018 | **GPT-1** (Alec Radford et al., OpenAI) | Demonstrated that [[autoregressive-models|autoregressive]] language model pretraining on a large corpus produces useful representations, laying the groundwork for the GPT lineage. |
| 2019 | **GPT-2** (Alec Radford et al., OpenAI) | A 1.5B parameter language model that generated remarkably coherent text — OpenAI initially withheld the full model, sparking the first public debate on [[ai-safety-and-alignment|AI safety]] for language models. |

## 2020s: Scaling, Generation, and Frontier Models

| Year | Milestone | Significance |
|------|-----------|--------------|
| 2020 | **GPT-3 and in-context learning** (Tom Brown et al., OpenAI) | 175B parameters demonstrated that [[large-language-models]] can perform tasks from examples in the prompt without fine-tuning — the emergence of [[prompt-engineering-and-in-context-learning|in-context learning]]. |
| 2020 | **Scaling laws for neural language models** (Jared Kaplan et al., OpenAI) | Empirical [[scaling-laws]] showing power-law relationships between model size, data, compute, and loss — gave the field a principled framework for allocating resources. |
| 2020 | **Vision Transformer (ViT)** (Alexei Dosovitskiy et al., Google) | Applied the Transformer directly to image patches, proving [[attention-and-transformers]] could match or beat CNNs for vision — unified architectures across modalities. See [[image-classification-milestones]]. |
| 2020 | **AlphaFold 2** (John Jumper et al., DeepMind) | Solved the 50-year-old protein structure prediction problem with attention-based architecture — deep learning's most celebrated scientific application. See [[protein-and-molecular-deep-learning]]. |
| 2020 | **DDPM — Denoising Diffusion Probabilistic Models** (Jonathan Ho et al.) | Established the modern [[diffusion-models]] framework — iteratively denoising random noise to generate high-quality images, eventually surpassing GANs. |
| 2021 | **CLIP** (Alec Radford et al., OpenAI) | Contrastive [[self-supervised-learning]] aligning images and text in a shared embedding space — enabled zero-shot image classification and became the text encoder backbone for [[text-to-image-generation]]. |
| 2021 | **Chinchilla scaling laws** (Jordan Hoffmann et al., DeepMind, published 2022) | Showed that compute-optimal training requires scaling data and parameters equally — most existing LLMs were significantly undertrained on data. See [[scaling-laws]]. |
| 2022 | **ChatGPT launched** (OpenAI) | GPT-3.5 fine-tuned with [[reward-modeling-and-rlhf|RLHF]] and released as a conversational product — reached 100M users in two months, making LLMs a mainstream technology. |
| 2022 | **Stable Diffusion** (Robin Rombach et al., Stability AI / CompVis) | Open-source latent [[diffusion-models|diffusion model]] for [[text-to-image-generation]] — democratized high-quality image generation by running on consumer GPUs. |
| 2023 | **GPT-4** (OpenAI) | [[Multimodal-models|Multimodal]] [[large-language-models|LLM]] accepting text and images, demonstrating broad expert-level reasoning — raised the bar for what frontier models can do. |
| 2023 | **LLaMA and the open-weight movement** (Hugo Touvron et al., Meta) | Released competitive open-weight LLMs, spawning an ecosystem of fine-tuned variants (Alpaca, Vicuna) and establishing that smaller, well-trained models can rival closed ones. See [[scaling-laws]]. |
| 2023 | **Mamba** (Albert Gu, Tri Dao) | Selective [[state-space-models|state space model]] achieving Transformer-quality with linear-time sequence processing — the leading alternative to attention for long sequences. |
| 2023 | **Flash Attention** (Tri Dao et al., first version 2022) | IO-aware attention algorithm that is 2–4x faster with much less memory — made long-context Transformers practical. See [[efficient-attention-variants]] and [[hardware-software-co-design]]. |
| 2024 | **Reasoning models (o1, R1)** (OpenAI; DeepSeek) | Models trained to perform extended chain-of-thought [[reasoning-in-llms|reasoning]] at test time, trading compute for accuracy — introduced [[scaling-laws|test-time compute scaling]] as a new axis. |
| 2024 | **Mixture-of-Experts at scale (Mixtral, DeepSeek-V2/V3)** (Mistral AI; DeepSeek) | Sparse [[mixture-of-experts]] models matching dense model quality at a fraction of the inference cost — made efficient scaling the industry default. |
| 2024 | **Video generation (Sora)** (OpenAI) | Diffusion Transformer generating minute-long coherent videos from text — demonstrated that [[diffusion-models]] scale to temporal data. See [[video-understanding-and-generation]]. |
| 2025 | **Frontier multimodal agents** (Anthropic, Google, OpenAI) | [[Agents-and-tool-use|Agentic]] [[multimodal-models]] that reason over text, images, and code while using tools — closing the loop from perception to action in open-ended tasks. |

## See Also

- [[image-classification-milestones]] — detailed architecture evolution from LeNet to ViT
- [[scaling-laws]] — the empirical laws governing model scaling
- [[attention-and-transformers]] — the architecture behind the modern era
- [[large-language-models]] — the current frontier
