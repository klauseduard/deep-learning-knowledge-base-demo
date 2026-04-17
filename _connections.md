# Deep Learning — Connections and Themes

This document maps the cross-cutting themes and relationships between concepts in the knowledge base.

## The Training Loop

The central feedback loop of deep learning connects four concepts tightly:

1. **[[loss-functions]]** define what "good" means — the objective to minimize
2. **[[backpropagation]]** computes how each parameter affects the loss — the gradient
3. **[[gradient-descent]]** uses those gradients to update parameters — the optimization step
4. The network's architecture (everything else) determines the function class being searched

Everything in deep learning exists in service of this loop. Architectures determine what functions are representable. Regularization prevents the loop from overfitting. Scaling laws predict how performance improves as the loop runs longer on more data.

## The Depth Problem and Its Solutions

A recurring theme is the tension between depth (more layers = more expressive power) and trainability (deeper networks are harder to optimize):

- **[[backpropagation]]** reveals the vanishing/exploding gradient problem — gradients degrade exponentially through many layers
- **[[activation-functions]]** partially solve it: ReLU's gradient is exactly 1 for positive inputs, avoiding saturation that plagued sigmoid/tanh
- **[[skip-connections]]** solve it architecturally: the identity shortcut guarantees gradient flow regardless of what happens in the transformation branch
- **[[regularization]]** (batch norm, layer norm) stabilizes activations, keeping gradients well-conditioned

These solutions are complementary and typically used together: a ResNet block combines convolutions, batch norm, ReLU, and a residual connection.

## Inductive Biases: From Strong to Weak

Architectures encode different assumptions about data structure:

- **[[convolutional-neural-networks]]** encode the strongest bias: locality (patterns are local) and translation equivariance (patterns can appear anywhere). This is perfect for images but limits global reasoning.
- **[[graph-neural-networks]]** encode a structural bias: local message passing respects graph topology, making them natural for molecules, social networks, and knowledge graphs. But the 1-WL expressiveness limit means some structures are indistinguishable.
- **[[attention-and-transformers]]** encode weaker bias: they can attend to any position, but need positional encoding because the mechanism is inherently permutation-invariant. This flexibility allows them to work across modalities. Graph transformers apply this to graphs, trading the GNN's structural bias for expressiveness.
- **[[multilayer-perceptrons]]** encode the weakest bias: every input element can affect every output element. Maximum flexibility but no structural assumptions, making them inefficient for large structured inputs.

The trend in deep learning has been toward weaker inductive biases + more data. Vision Transformers (weaker bias than CNNs) now match or exceed CNNs when trained on enough data, echoing Sutton's "bitter lesson."

## The Autoregressive Paradigm

A major thread connects sequential prediction to modern AI:

- **[[autoregressive-models]]** define the mathematical framework: model $P(x_t | x_{<t})$
- **[[attention-and-transformers]]** provide the architecture: causal self-attention with masking
- **[[loss-functions]]** provide the training objective: cross-entropy summed over positions
- **[[large-language-models]]** are the result: GPT-scale models trained on this paradigm exhibit emergent capabilities
- **[[scaling-laws]]** predict how performance improves with scale
- **[[training-techniques]]** (RLHF, LoRA) adapt pre-trained LLMs for specific uses

This chain — from mathematical principle to world-changing application — is perhaps the most important narrative in modern AI.

## Generation: A Family of Approaches

Deep learning generates new content through several distinct paradigms:

1. **Autoregressive generation** ([[autoregressive-models]], [[large-language-models]]): generate one token at a time, feeding each output back as input. Dominates for text.

2. **Diffusion** ([[diffusion-models]]): start from noise and iteratively denoise. Dominates for images since ~2022, operating in the latent space of a pre-trained [[autoencoders|VAE]].

3. **Adversarial generation** ([[generative-adversarial-networks]]): generator vs. discriminator competition produces sharp images. Dominated image generation 2016–2021, now largely superseded by diffusion but still relevant for speed.

4. **Variational generation** ([[autoencoders]]): VAEs encode data as distributions and decode samples. Less sharp than GANs or diffusion alone, but provide the latent space backbone for latent diffusion.

The generative model timeline — autoencoders (2013) → GANs (2014) → diffusion (2020) → latent diffusion (2022) — shows increasing stability and quality. Each generation built on the previous: latent diffusion uses VAE encoders, and GAN-style adversarial losses sometimes appear as auxiliary objectives in diffusion training.

## The Compute Schism

A tension runs through the field between training and inference:

- **Training** requires massive compute: [[scaling-laws]] show that performance improves as a power law with compute, incentivizing ever-larger training runs. Only large organizations can afford this.
- **Inference** can be made efficient: [[training-techniques]] (quantization, LoRA adapters, model merging) and hardware advances enable running large models locally.

This creates a two-tier ecosystem: a few organizations pre-train foundation models, and many others fine-tune and deploy them. **[[knowledge-distillation]]** bridges the gap — large teacher models transfer their knowledge to smaller students, enabling deployment on constrained hardware. **[[generalization-theory]]** asks *why* this pipeline works at all — why do overparameterized models generalize rather than memorize?

**[[gpu-and-accelerator-hardware]]** is the physical foundation of this entire schism. The memory wall (compute growing faster than bandwidth) shapes which operations are bottlenecked by compute vs. memory. Mixed precision formats (BF16, FP8, FP4) exist because Tensor Cores exploit lower precision for higher throughput. The cost of GPU-hours — whether cloud or on-premise — is the economic lens through which all training and serving decisions are made.

## Component Reuse

Certain building blocks appear as sub-components across many architectures:

- **[[multilayer-perceptrons]]**: appear as the feed-forward block in Transformers, as classifier heads in CNNs, as projection layers everywhere
- **[[skip-connections]]**: used in ResNets (residual), U-Nets (concatenative), and every Transformer block (residual)
- **[[regularization]]**: batch norm in CNNs, layer norm in Transformers, dropout in both
- **[[activation-functions]]**: ReLU in CNNs, GELU in Transformers, sigmoid in gates

## The Sequence Architecture Evolution

A clear evolutionary arc runs through the sequence modeling architectures:

1. **[[recurrent-neural-networks]]** (1990s–2017): natural sequential processing but can't parallelize during training; LSTM solved vanishing gradients with gated memory
2. **[[attention-and-transformers]]** (2017–present): parallel training via all-to-all attention, but quadratic cost; dominates through scaling
3. **[[state-space-models]]** (2021–present): reclaim linear-time processing while preserving parallelism via the dual convolution/recurrence view; Mamba adds content-dependent selection

Each generation learned from the previous: LSTMs' gating inspired attention masking, attention's parallelism motivated SSM convolution mode, and the SSM-attention duality (Mamba-2) shows these aren't separate ideas but points on a spectrum.

## Training to Deployment Pipeline

The journey from a raw model to a deployed service connects several articles:

0. **[[gpu-and-accelerator-hardware]]** provides the physical substrate — GPU memory capacity constrains model size, interconnect bandwidth constrains parallelism strategy, and cost per GPU-hour constrains budgets
1. **[[distributed-training]]** enables training models too large for one GPU
2. **[[scaling-laws]]** guide how to allocate compute between model size and data
3. **[[training-techniques]]** (RLHF, LoRA) adapt the base model for specific uses
4. **[[inference-optimization]]** (quantization, KV-cache, speculative decoding) makes deployment affordable
5. **[[interpretability]]** verifies the model behaves as intended

This pipeline reflects the modern "foundation model" paradigm: train once at massive scale, then adapt and optimize for deployment. At every stage, hardware constraints are the binding reality — the memory wall determines what's feasible, and cost per FLOP determines what's economical.

## From Prediction to Action: The Agent Paradigm

A major theme connects language modeling to autonomous action:

1. **[[autoregressive-models]]** provide the mathematical basis: predict the next token
2. **[[large-language-models]]** scale this to exhibit reasoning and instruction following
3. **[[training-techniques]]** (RLHF, function calling fine-tuning) make models controllable and tool-aware
4. **[[agents-and-tool-use]]** close the loop: the LLM reasons about what to do, calls tools, observes results, and iterates

This progression — from passive prediction to active agency — represents the most consequential application trend in modern AI. The key insight from ReAct (Yao et al., 2022) is that reasoning and acting are synergistic: reasoning grounds action selection, while action results ground reasoning in reality. This connects back to **[[reinforcement-learning]]**, where the agent-environment loop is formalized as an MDP, and forward to reasoning models (o1, R1) where RL is used to train the thinking process itself.

The agent paradigm also reframes **[[inference-optimization]]** — agent workloads are latency-sensitive (many sequential LLM calls in a loop), making per-call latency more critical than throughput. And it gives new importance to **[[scaling-laws]]**: test-time compute scaling (spending more inference tokens on harder problems) may follow its own scaling laws distinct from training-time scaling.

## Understanding What We've Built

A tension between capability and understanding runs through the field:

- **[[large-language-models]]** exhibit capabilities that surprise their creators
- **[[scaling-laws]]** can predict *performance* but not *what capabilities* will emerge
- **[[interpretability]]** attempts to reverse-engineer what's actually happening inside
- **[[reinforcement-learning]]** (RLHF) aligns models based on human preferences without fully understanding the models' internals

Whether we can achieve reliable AI systems without deep understanding is perhaps the field's most important open question.

## The Pre-Training Revolution

A clear arc connects [[self-supervised-learning]] to the modern foundation model paradigm:

1. Early models required labeled data for every task — expensive and limiting
2. Self-supervised objectives (predict next token, predict masked token, match augmented views) let models learn from *unlabeled* data at massive scale
3. The "pre-train then fine-tune" paradigm ([[training-techniques]]) emerged: one expensive SSL phase, many cheap adaptations
4. [[large-language-models]] are the ultimate expression: pre-train on the internet with autoregressive SSL, then adapt via RLHF

SSL connects to almost every architecture in the knowledge base: BERT uses masked prediction ([[attention-and-transformers]]), GPT uses autoregressive prediction ([[autoregressive-models]]), SimCLR uses contrastive learning on CNN features ([[convolutional-neural-networks]]), and MAE uses masked image modeling on ViTs.

## Sparse vs. Dense Computation

[[mixture-of-experts]] introduces a fundamental design axis: not all parameters need to participate in every computation. This connects to:

- **[[scaling-laws]]**: MoE changes the relationship between total parameters and compute — a model can have 8× more knowledge capacity without 8× more cost
- **[[inference-optimization]]**: MoE models need all experts in memory but only activate a few — different optimization strategies than dense models
- **[[distributed-training]]**: expert parallelism adds a fourth dimension alongside data, tensor, and pipeline parallelism
- **[[attention-and-transformers]]**: MoE replaces the dense FFN in Transformer blocks while keeping attention dense

The sparse/dense trade-off is a recurring theme: sparse attention (in long-context models), sparse activations (MoE), and sparse representations (in [[interpretability]], where SAEs decompose dense activations into sparse features) all exploit the insight that not everything needs to be active simultaneously.

## The Modality Convergence

A striking trend is the convergence of all data types into unified models:

- **[[convolutional-neural-networks]]** dominated vision, **[[recurrent-neural-networks]]** dominated language — separate architectures for separate modalities
- **[[attention-and-transformers]]** became the universal backbone across text, images, audio, and video
- **[[self-supervised-learning]]** (CLIP, SimCLR, BERT) enabled pre-training across modalities without labels
- **[[multimodal-models]]** unify multiple modalities in a single system — from late fusion (LLaVA) to native early fusion (Gemini, GPT-4o)

The progression reflects a deeper insight: the same computational patterns (attention, residual connections, normalization) work across very different data types. What differs is the tokenization (BPE for text, patches for images, spectrograms for audio) and the pre-training objective. [[knowledge-distillation]] plays a role here too — many open multimodal models (Alpaca, LLaVA variants) are distilled from frontier models.

**[[video-understanding-and-generation]]** extends the convergence into the temporal visual domain. Video understanding evolved from extending 2D CNNs with 3D convolutions (C3D, I3D, SlowFast) to applying transformers to spacetime patches (TimeSformer, ViViT, VideoMAE). Video generation, catalyzed by Sora (2024), combined spatial-temporal VAEs, diffusion/flow-matching, and DiT backbones into a unified paradigm that scales to minute-long 1080p video. Video-language models (Video-LLaVA, Gemini) bridge [[multimodal-models]] and temporal reasoning. The rapid 2024–2025 progress — from Sora to Veo 2, Kling, Movie Gen, and open-source alternatives (HunyuanVideo, Wan) — makes video one of the fastest-evolving subfields.

**[[speech-and-audio]]** extends this convergence into the audio domain: Whisper (ASR), VALL-E (TTS), and MusicLM all build on Transformer-based architectures. The neural codec revolution (SoundStream, EnCodec) mirrors tokenization in text — converting continuous audio waveforms into discrete token sequences that autoregressive and masked models can process. This creates a unified framework where text, images, and audio are all sequences of tokens fed through the same Transformer backbone.

## Vision Beyond Classification

**[[object-detection]]** reveals how deep learning extended from recognizing *what* to recognizing *where*:

- **[[convolutional-neural-networks]]** provide the feature extraction backbone (VGG, ResNet, EfficientNet)
- **[[skip-connections]]** enable multi-scale feature extraction via Feature Pyramid Networks (FPN) — concatenative skip connections that let detectors find both small and large objects
- **[[attention-and-transformers]]** transformed detection with DETR, replacing hand-designed components (anchors, NMS) with end-to-end learning via set prediction
- **[[neural-architecture-search]]** optimized detection architectures (EfficientDet) for deployment constraints

The detection pipeline evolution — from R-CNN's brute-force region proposals (2014) to YOLO's single-shot prediction (2016) to DETR's set-based formulation (2020) — mirrors the broader trend toward simpler, more general architectures that rely on scale rather than hand-crafted components.

**[[semantic-segmentation]]** extends detection to pixel-level understanding. The field's architecture evolution directly parallels detection's: from task-specific designs (FCN, U-Net, DeepLab) to Transformer-based unified architectures (Mask2Former) to foundation models (SAM). U-Net's encoder-decoder with concatenative skip connections became so influential that it was adopted as the backbone of [[diffusion-models]]. SAM represents the same "foundation model" paradigm shift seen in NLP — a single promptable model replacing many task-specific ones.

## Data Constraints and Privacy

**[[federated-learning]]** introduces a fundamental constraint missing from standard training: the data cannot be centralized. This connects to several themes:

- **[[distributed-training]]** assumes IID data across workers and fast interconnects — FL has neither, requiring entirely different algorithms (FedAvg, FedProx, SCAFFOLD)
- **[[gradient-descent]]** — FedAvg is distributed SGD with infrequent communication, but non-IID data causes client drift that standard SGD theory doesn't address
- **[[training-techniques]]** — LoRA adapters make federated fine-tuning of LLMs practical by reducing the communication cost from billions to millions of parameters
- **[[knowledge-distillation]]** — federated distillation shares only predictions instead of weights, entirely decoupling client and server architectures

The tension between privacy and utility is a recurring theme: differential privacy adds noise that degrades model quality, gradient inversion attacks can reconstruct training data from model updates, and the non-IID challenge means federated models often underperform centralized ones. Whether this gap is fundamental or solvable remains open.

## Architecture Design: Human vs. Machine

**[[neural-architecture-search]]** raises a meta-question about how architectures are designed:

- The most impactful architectures (ResNets, Transformers, Mamba) were designed by **humans** through insight and experimentation
- NAS has produced successful architectures (EfficientNet, NASNet) by **automating** the search, particularly for specific hardware targets
- The search space itself is human-designed — NAS can only find architectures within the space of possibilities that humans define
- **[[scaling-laws]]** interact with NAS: EfficientNet's compound scaling principle (scale depth, width, and resolution together) was arguably more influential than the NAS-discovered base architecture

The trend is toward NAS for **deployment optimization** (finding the best architecture for a specific device/latency constraint) rather than for **fundamental discovery**. As foundation models dominate, NAS shifts from designing architectures from scratch to finding optimal sub-networks and configurations within established architecture families.

## Learning to Learn

**[[meta-learning]]** addresses a fundamental question: can a model learn not just a task, but the *process* of learning from few examples?

- **Optimization-based** (MAML): meta-learn an initialization for **[[gradient-descent]]** such that a few gradient steps on new tasks produce good models. The outer loop optimizes *for* gradient descent — a striking meta-level use of the training loop.
- **Metric-based** (Prototypical Networks): learn an embedding space where **[[self-supervised-learning]]** and contrastive learning ideas reappear — classification reduces to nearest-neighbor in a learned metric space.
- **In-context learning**: **[[large-language-models]]** perform implicit meta-learning — their Transformer forward pass can implement gradient descent on in-context examples (von Oswald et al., 2023). Pre-training on diverse data effectively meta-trains the model across millions of tasks, making explicit meta-learning algorithms largely redundant at scale.

This connects the oldest aspiration of meta-learning (Schmidhuber, 1987) to the newest capabilities of foundation models, suggesting that **[[scaling-laws]]** may matter more than clever adaptation algorithms.

## The Deployment Gap

**[[model-deployment]]** reveals a substantial gap between research and production:

- **[[inference-optimization]]** provides the algorithmic toolkit (quantization, KV-cache, Flash Attention), but deployment also requires format conversion (ONNX, TensorRT), serving infrastructure (Triton, vLLM), monitoring, and lifecycle management
- **[[knowledge-distillation]]** and **[[neural-architecture-search]]** create deployment-friendly models — small enough for edge devices, fast enough for latency constraints
- **[[gpu-and-accelerator-hardware]]** determines what's feasible: on-device Neural Engines enable mobile inference, while GPU memory capacity gates which models can be served
- The LLM era has transformed deployment: autoregressive generation, massive KV-caches, and agent workloads (**[[agents-and-tool-use]]**) require specialized serving infrastructure entirely different from classification model serving

The training-to-deployment pipeline (**[[distributed-training]]** → **[[training-techniques]]** → **[[model-deployment]]**) reflects the modern reality: training is done once by a few organizations, but deployment happens everywhere on diverse hardware.

## The Information-Theoretic Lens

**[[information-theory]]** provides a unifying language that connects many concepts in the knowledge base:

- **[[loss-functions]]**: cross-entropy loss is literally the cross-entropy between the true distribution and the model's predictions — training minimizes an information-theoretic quantity. KL divergence measures the "cost" of using the wrong distribution.
- **[[autoencoders]]** and **[[self-supervised-learning]]**: the Information Bottleneck principle (Tishby, 1999) formalizes the trade-off between compression and prediction — learn representations that discard irrelevant information while preserving what's needed for the task. VAEs explicitly optimize this via $-\text{ELBO} = D_{\text{KL}} + \text{reconstruction}$.
- **[[knowledge-distillation]]**: soft labels carry more information than hard labels (in an information-theoretic sense) because they encode inter-class similarities — the "dark knowledge" that makes distillation work.
- **[[generalization-theory]]**: compression-based explanations of generalization (models that compress training data well generalize well) connect directly to minimum description length and Kolmogorov complexity.
- **[[scaling-laws]]**: the power-law relationship between data/compute and loss can be interpreted as the model gradually capturing more mutual information between inputs and targets.

Whether the information bottleneck is the *right* framework for understanding deep learning remains debated (Saxe et al., 2019 challenged the compression phase), but the information-theoretic vocabulary pervades the field.

## The Loss Landscape as Organizing Principle

**[[loss-landscape-geometry]]** connects optimization, generalization, and training practice in a unified geometric picture:

- **[[gradient-descent]]** navigates this landscape — SGD's noise (from mini-batching) acts as implicit regularization, biasing toward flat minima that generalize better. The noise scale $\eta / B$ (learning rate / batch size) controls this regularization strength.
- **[[generalization-theory]]**: flat minima generalize while sharp minima don't — this geometric insight gives physical intuition for why overparameterized models work. Double descent and grokking can be understood as the optimizer traversing different landscape regions during training.
- **[[training-techniques]]**: learning rate warmup, cosine schedules, and large batch training all interact with the loss landscape — warmup avoids sharp minima early, cosine decay refines the solution, and SAM explicitly optimizes for flatness.
- **[[curriculum-learning]]**: easy examples create a smoother loss landscape early in training (continuation methods), helping the optimizer find good basins before harder examples sharpen the landscape. This is the geometric justification for why curriculum works.
- **[[loss-landscape-geometry|Mode connectivity]]** (Garipov et al., 2018) — the finding that good solutions are connected by low-loss paths — connects to **[[training-techniques|model merging]]** (averaging weights of independently trained models works because they're in the same loss basin) and **[[distributed-training]]** (why averaging model replicas converges).

The edge of stability phenomenon (Cohen et al., 2021) — where the loss Hessian's maximum eigenvalue hovers at exactly $2/\eta$ — suggests that gradient descent self-organizes at the boundary of stability, a behavior not predicted by classical optimization theory.

## Data as the Foundation

**[[data-engineering]]** underpins everything else in the knowledge base — model quality is bounded by data quality:

- **[[scaling-laws]]**: performance scales as a power law with data quantity, but data *quality* and *mixture* can shift the scaling curve. DoReMi showed that optimal domain weighting during pre-training significantly improves downstream performance.
- **[[self-supervised-learning]]** and **[[data-engineering]]**: SSL reduces the need for labeled data but increases the importance of unlabeled data curation — the quality of Common Crawl filtering directly affects LLM capabilities.
- **[[knowledge-distillation]]**: synthetic data generation (Alpaca, Orca, Phi) is distillation in disguise — using a teacher model to generate training data for a student. The quality of this synthetic data matters more than quantity.
- **[[curriculum-learning]]**: data ordering interacts with data quality — training on clean data first (implicit quality-based curriculum) improves robustness to label noise.
- Model collapse (Shumailov et al., 2024) introduces a new constraint: training on too much model-generated data degrades quality over generations, suggesting a fundamental limit to synthetic data's role.

The "data-centric AI" movement (Ng, 2021) argues that improving data often yields more gains than improving architectures — a claim supported by Phi-1's results (1.3B model trained on "textbook-quality" data outperforming 10× larger models on raw code).

## The Plasticity-Stability Trade-Off

**[[continual-learning]]** and **[[curriculum-learning]]** address complementary aspects of how training order affects learning:

- **[[continual-learning]]** asks: how to learn new tasks without forgetting old ones? The core challenge is that **[[gradient-descent]]** optimizes for the current objective without protecting past solutions.
- **[[curriculum-learning]]** asks: in what order should examples be presented? Easy examples provide a smoother **[[loss-landscape-geometry|loss landscape]]** that guides the optimizer into good basins.
- **[[regularization]]**: EWC and SI (continual learning methods) are fundamentally regularization techniques — they add penalty terms that anchor important weights. This connects to weight decay, dropout, and all other regularizers that constrain the solution space.
- **[[meta-learning]]**: meta-continual learning combines both — MAML-style initializations may resist forgetting because they sit in broadly useful regions of parameter space. In-context learning (**[[large-language-models]]**) sidesteps the problem entirely by learning without parameter updates.
- **Experience replay** in continual learning was directly inspired by **[[reinforcement-learning]]** (DQN's replay buffer), showing how ideas flow between fields.

The foundation model era partially dissolves the continual learning problem: pre-trained models have robust, general features that resist catastrophic forgetting during fine-tuning, and RAG externalizes new knowledge without parameter updates. Whether this "solves" continual learning or just pushes the problem to the pre-training stage remains open.

## From 2D to 3D: Implicit, Explicit, and Generative Representations

**[[3d-vision-and-neural-rendering]]** reveals a fundamental paradigm shift in how deep learning represents and renders 3D scenes, connecting to many themes:

- **Implicit vs. explicit representations**: NeRF ([[3d-vision-and-neural-rendering]]) stores a scene implicitly in **[[multilayer-perceptrons]]** weights — a continuous function mapping coordinates to color and density. 3D Gaussian Splatting flips this to explicit Gaussian primitives. This mirrors the broader tension between compact implicit models (neural networks) and explicit data structures (hash tables, voxels, point clouds) that recurs throughout deep learning.

- **The rendering equation bridges vision and graphics**: NeRF's volume rendering equation and 3DGS's differentiable rasterization both make the rendering process differentiable, enabling **[[backpropagation]]** from photometric losses through physics-based rendering to 3D scene parameters. This is a striking application of the training loop (loss → gradients → updates) to a problem traditionally solved without learning.

- **Diffusion models for 3D generation**: DreamFusion's Score Distillation Sampling repurposes pre-trained 2D **[[diffusion-models]]** as 3D priors, generating 3D content without 3D training data. This demonstrates the power of 2D generative models as a source of geometric knowledge — the diffusion model implicitly "knows" about 3D structure from seeing millions of photographs.

- **Point cloud networks as 3D transformers**: PointNet's per-point MLP + max pooling architecture introduced permutation-invariant processing of unordered sets — a design pattern that directly influenced set-based architectures in **[[attention-and-transformers]]** (DETR uses a similar paradigm for object detection). Point Transformer later brought attention itself to point clouds, completing the circle.

- **Hardware determines representation choice**: 3DGS's real-time performance comes from aligning with GPU rasterization pipelines (**[[gpu-and-accelerator-hardware]]**), while NeRF's ray marching fights against GPU architecture. The same hardware-algorithm co-design principle that drives **[[inference-optimization]]** (Flash Attention, PagedAttention) also drove the shift from NeRF to Gaussians.

- **Applications across domains**: 3D vision connects to **[[object-detection]]** (3D bounding boxes for autonomous driving), **[[multimodal-models]]** (text-to-3D generation), and **[[self-supervised-learning]]** (CLIP/DINO features embedded in 3D for open-vocabulary scene understanding).

## The Alignment Challenge

**[[ai-safety-and-alignment]]** introduces the most consequential meta-question in the knowledge base: can we ensure that increasingly capable models remain aligned with human intentions?

- **[[reinforcement-learning]]** provides the primary alignment mechanism (RLHF/DPO), but also the failure modes — reward hacking is the alignment version of Goodhart's Law, where optimizing a proxy reward degrades the true objective
- **[[interpretability]]** is the diagnostic tool — mechanistic understanding of model internals could provide safety guarantees that behavioral testing cannot. Representation engineering allows steering model behavior by manipulating activation directions.
- **[[large-language-models]]** and **[[agents-and-tool-use]]** create the urgency — models that can reason, plan, and take real-world actions through tools amplify alignment failures from "generates bad text" to "takes harmful actions"
- **[[scaling-laws]]** pose the open question: does alignment difficulty scale with capability? Weak-to-strong generalization experiments suggest the alignment tax may be reducible, but the answer at frontier scale remains unknown.
- **[[knowledge-distillation]]** and constitutional AI create a scalable alignment pathway — using AI feedback instead of human feedback, and distilling aligned behavior from larger to smaller models

The cat-and-mouse dynamic between jailbreakers and safety teams — and the fundamental tension between the alignment tax and model capability — shapes the practical reality of deploying AI systems.

## Embeddings as the Universal Interface

**[[embeddings-and-representation-learning]]** provides the geometric substrate on which many other systems operate:

- **[[self-supervised-learning]]** learns embeddings without labels — contrastive learning (SimCLR, MoCo), masked prediction (BERT, MAE), and CLIP's text-image alignment all produce embeddings as their primary output
- **[[multimodal-models]]** depend on shared embedding spaces where text, images, and audio are geometrically comparable — CLIP's embedding space is the foundation for LLaVA, Stable Diffusion's text conditioning, and zero-shot classification
- **[[large-language-models]]** use embeddings at every level: token embeddings as input, hidden state embeddings as intermediate representations, and the entire model can be viewed as learning a hierarchical embedding of language
- **[[text-to-image-generation]]** relies on CLIP embeddings for text conditioning and IP-Adapter's image embeddings for visual conditioning — the quality of these embeddings directly determines generation fidelity
- **Vector databases and RAG** connect embeddings to deployment — **[[model-deployment]]** increasingly involves embedding models alongside generative models, with ANN algorithms (HNSW, IVF) enabling retrieval at scale

The progression from word2vec's 300-dimensional static vectors (2013) to CLIP's multimodal embeddings to Matryoshka representations reflects the field's growing understanding of what makes representations useful.

## The Optimization Stack

**[[optimization-beyond-sgd]]** and **[[normalization-techniques]]** together form the practical toolkit that makes modern training work:

- **[[gradient-descent]]** provides the theoretical foundation, but raw SGD doesn't train Transformers effectively. Adam's per-parameter adaptive learning rates handle the highly non-uniform gradient distributions in attention mechanisms.
- **[[normalization-techniques]]** reshape the **[[loss-landscape-geometry|loss landscape]]** — Santurkar et al. (2018) showed BN makes the landscape smoother, enabling larger learning rates. RMSNorm's adoption in modern LLMs (**[[large-language-models]]**) reflects the continuing importance of normalization.
- **[[distributed-training]]** creates new optimization challenges — large-batch optimizers (LARS, LAMB) exist because naively scaling batch size degrades quality; AdaFactor exists because Adam's optimizer states consume more memory than the model itself at scale.
- **Learning rate schedules** interact with everything: warmup prevents early training instability, cosine decay provides the gradual refinement, and the WSD schedule's long stable phase changes how **[[scaling-laws]]** translate to training recipes.
- **The SGD vs. Adam debate** connects to **[[generalization-theory]]**: SGD's noise may provide implicit regularization that Adam lacks, but this matters less as models scale and the gap narrows.

## From Diffusion to Creation: The Text-to-Image Pipeline

**[[text-to-image-generation]]** integrates many knowledge base concepts into a single, complex pipeline:

- **[[diffusion-models]]** provide the generative backbone — the denoising process that turns noise into images
- **[[autoencoders]]** (VAE) provide the latent space compression that makes diffusion computationally feasible — a 512×512 image becomes a 64×64 latent
- **[[embeddings-and-representation-learning]]** (CLIP) provides the text-image alignment — cross-attention between text embeddings and image features is where language becomes visual
- **[[attention-and-transformers]]** appear at multiple levels: cross-attention for text conditioning, self-attention for spatial coherence, and DiT replaces the entire U-Net with a Transformer
- **[[semantic-segmentation]]**: U-Net originated as a segmentation architecture before becoming the diffusion backbone; ControlNet uses segmentation maps for spatial control
- **[[training-techniques]]**: LoRA enables community fine-tuning; DreamBooth personalizes with few images; classifier-free guidance is a training-time technique for inference-time control
- **[[data-engineering]]**: LAION-5B's quality directly affects generation quality; DALL-E 3's synthetic recaptioning demonstrates that better data (captions) matters more than more data

## Position: The Missing Ingredient

**[[positional-encoding]]** solves a problem unique to the Transformer paradigm and connects to the long-context revolution:

- **[[attention-and-transformers]]** are permutation-invariant by design — they see bags of tokens, not sequences. Positional encoding is what makes them sequence models. The choice between absolute (sinusoidal, learned) and relative (RoPE, ALiBi) encoding determines whether the model can generalize to unseen sequence lengths.
- **[[recurrent-neural-networks]]** and **[[state-space-models]]** don't need explicit positional encoding — their sequential processing inherently encodes position. This is one advantage RNNs/SSMs retain over Transformers.
- **[[large-language-models]]** critically depend on position encoding for long-context capabilities. The jump from 2K (GPT-3) to 128K+ (GPT-4, Claude) tokens was enabled by RoPE + extension methods (YaRN, NTK-aware scaling) — a purely positional encoding innovation.
- **[[scaling-laws]]** for context length: longer context enables new capabilities (many-shot ICL, document understanding) but increases compute quadratically with attention. Position encoding determines the efficiency of this trade-off.

## Quantization: Making Scale Accessible

**[[quantization]]** is the bridge between the models that frontier labs train and the models that everyone else can run:

- **[[inference-optimization]]** provides the algorithmic techniques (KV-cache, Flash Attention), but quantization provides the memory reduction that makes large models fit on smaller hardware. INT4 quantization turns a 140GB model into a 35GB one — the difference between needing a cluster and running on a single GPU.
- **[[gpu-and-accelerator-hardware]]** co-evolves with quantization: NVIDIA's progression from FP32 → FP16 → INT8 → FP8 → FP4 reflects the hardware adopting lower precisions that quantization research validates. The hardware precision floor determines how aggressive quantization can be.
- **[[training-techniques]]** (QLoRA) combines quantization with adaptation — quantize the base model to 4-bit, fine-tune with LoRA in higher precision. This made 65B model fine-tuning possible on a single 48GB GPU.
- **[[knowledge-distillation]]** and quantization are complementary compression paths: distill a large model to a smaller one, then quantize the student for maximum efficiency. Together they can reduce serving cost by 10-100×.
- **[[information-theory]]** provides the theoretical framework — quantization is lossy compression, and the rate-distortion trade-off predicts the fundamental limit on how much precision can be removed before quality degrades.

## Knowing What You Don't Know

**[[bayesian-deep-learning]]** addresses a critical gap in standard deep learning — uncertainty quantification:

- **[[regularization]]** has a Bayesian interpretation: weight decay is a Gaussian prior, dropout is approximate variational inference (Gal & Ghahramani, 2016). This means every regularized network is implicitly Bayesian.
- **[[generalization-theory]]**: the marginal likelihood (Bayesian model evidence) naturally penalizes model complexity via Occam's razor, providing a principled alternative to cross-validation for model selection.
- **[[loss-landscape-geometry]]**: deep ensemble diversity comes from different local minima; the Laplace approximation uses the loss curvature (Hessian) to estimate uncertainty. Flat minima correspond to broad posteriors, sharp minima to narrow ones — connecting geometric intuition to Bayesian uncertainty.
- **[[ai-safety-and-alignment]]**: reliable uncertainty is a prerequisite for safe deployment. Models that know what they don't know can abstain, flag uncertain cases for human review, and detect out-of-distribution inputs.
- **[[large-language-models]]**: verbal confidence estimates, token entropy, and semantic uncertainty (multiple generation sampling) are practical Bayesian-inspired techniques for LLM uncertainty.

## The In-Context Learning Revolution

**[[prompt-engineering-and-in-context-learning]]** represents a fundamental shift in how models are used:

- **[[meta-learning]]**: in-context learning IS implicit meta-learning — pre-training on diverse data meta-trains the model to learn from context. Von Oswald et al. (2023) showed Transformers implement gradient descent in their forward pass, making explicit meta-learning algorithms (MAML) largely redundant at scale.
- **[[attention-and-transformers]]**: induction heads (Olsson et al., 2022) are specific attention circuits that enable ICL — a two-layer pattern-matching mechanism that generalizes from in-context examples. ICL is not magic; it's a learned computation in the attention mechanism.
- **[[ai-safety-and-alignment]]**: prompt injection and jailbreaking exploit ICL adversarially. Many-shot jailbreaking uses the same ICL mechanism for harmful purposes, creating a fundamental tension between capability and safety.
- **[[agents-and-tool-use]]**: ReAct prompting bridges reasoning and action. The entire agent paradigm is built on prompt engineering — system prompts, tool descriptions, and observation formatting are all prompt design decisions.
- **[[scaling-laws]]**: ICL capability improves with scale (GPT-3 was the first model large enough for reliable ICL). Test-time compute scaling (reasoning models like o1/R1) extends the scaling paradigm from training to inference via chain-of-thought.

## The ImageNet Arc: From Engineering to Scale

**[[image-classification-milestones]]** tells the story of deep learning's core methodology through one task:

- Each milestone introduced ideas that became universal: **ReLU** ([[activation-functions]], AlexNet), **dropout** ([[regularization]], AlexNet), **batch normalization** ([[normalization-techniques]], Inception/ResNet), **skip connections** ([[skip-connections]], ResNet), **NAS** ([[neural-architecture-search]], EfficientNet), and **vision attention** ([[attention-and-transformers]], ViT).
- The progression from strong inductive biases (CNNs: locality, translation equivariance) to weak inductive biases (ViT: permutation-invariant attention + patches) mirrors the broader field trend and validates Sutton's "bitter lesson."
- **[[scaling-laws]]** are implicit throughout: ViT only outperforms CNNs with massive data (JFT-300M), and EfficientNet's compound scaling formalized the depth-width-resolution relationship. Model quality scales predictably with compute.
- The classification backbone feeds downstream tasks: ResNet and Swin Transformer features power **[[object-detection]]** (Faster R-CNN, DETR), **[[semantic-segmentation]]** (FCN, Mask2Former), and **[[3d-vision-and-neural-rendering]]** (PointNet++ hierarchies). Classification architectures are the foundation of computer vision.

## The Text-to-Tokens Pipeline

**[[tokenization]]** is the hidden first layer of every language model — decisions made here propagate through the entire system:

- **[[large-language-models]]** are fundamentally token-prediction machines. The tokenizer determines what "atoms" the model reasons over: whether "strawberry" is one token or three, whether code indentation consumes precious context, and whether Hindi gets 3× fewer effective tokens than English for the same context window.
- **[[scaling-laws]]** measure performance in tokens — but a token's information content depends entirely on the tokenizer. Larger vocabularies (GPT-4o's ~200K) compress text more efficiently, effectively giving the model more "information per token" and stretching the context window.
- **[[positional-encoding]]** interacts with tokenization: context length limits are in *tokens*, so tokenizer efficiency directly affects how much text fits in the context window. Languages with high fertility (many tokens per word) are systematically disadvantaged.
- **[[multimodal-models]]** extend tokenization beyond text: VQ-VAE discretizes images into visual tokens, SoundStream/EnCodec produce audio tokens, creating the unified token sequences that enable models like Gemini to process text, images, and audio in one stream.
- **[[embeddings-and-representation-learning]]**: the embedding matrix ($V \times d$) is shaped by vocabulary size — larger vocabularies increase memory but improve compression. Rare tokens have undertrained embeddings, creating a long tail of poorly represented inputs.

## Transfer Learning: The Foundation Model Paradigm

**[[transfer-learning]]** is arguably the most practically important idea in the knowledge base — virtually nothing is trained from scratch:

- **[[self-supervised-learning]]** provides the pre-training objectives that make transfer possible. The arc from ImageNet supervised pre-training to BERT/GPT self-supervised pre-training to CLIP multimodal pre-training represents an expanding scope of what knowledge can be transferred.
- **[[training-techniques]]**: LoRA, adapters, and prompt tuning are all parameter-efficient transfer methods — they answer the question "how do we adapt a foundation model without the cost of full fine-tuning?" QLoRA (**[[quantization]]**) combines quantized storage with efficient adaptation.
- **[[continual-learning]]**: catastrophic forgetting during fine-tuning is the transfer learning version of the plasticity-stability trade-off. Why do pre-trained models resist forgetting? Possibly because they occupy flat, general regions of the **[[loss-landscape-geometry|loss landscape]]**.
- **[[meta-learning]]**: MAML explicitly optimizes for transferability — finding initializations from which a few gradient steps reach good solutions. In-context learning (**[[prompt-engineering-and-in-context-learning]]**) is transfer without weight updates — the ultimate parameter-efficient adaptation.
- **[[knowledge-distillation]]** is an alternative transfer mechanism: instead of sharing weights, share knowledge through soft labels. This enables transfer across different architectures (teacher and student can have different designs).
- **Task arithmetic** connects to **[[loss-landscape-geometry]]**: the ability to add and subtract task vectors ($\theta_{\text{ft}} - \theta_{\text{pre}}$) suggests that fine-tuning moves weights in interpretable directions in a well-structured parameter space.

## Adversarial Vulnerability as a Window into Representations

**[[adversarial-robustness]]** reveals fundamental properties of what neural networks learn:

- **[[ai-safety-and-alignment]]**: adversarial attacks on LLMs (jailbreaks, prompt injection) are conceptually similar to adversarial examples on classifiers — both exploit the gap between the model's learned decision boundary and human intent. The defense landscape is similarly cat-and-mouse.
- **[[generalization-theory]]**: the robustness-accuracy trade-off (Tsipras et al., 2019) suggests that standard and robust generalization require fundamentally different features. This connects to the "features not bugs" perspective — standard training learns non-robust but predictive features.
- **[[interpretability]]**: adversarially robust models learn more human-interpretable features. Their gradients are meaningful, and feature visualizations look natural — suggesting that adversarial training forces the model to rely on the same features humans use.
- **[[loss-landscape-geometry]]**: adversarial training and SAM both seek flat minima — adversarial perturbation of inputs (AT) and adversarial perturbation of weights (SAM) are two sides of the same coin.
- **[[diffusion-models]]**: diffusion-based purification is an emerging defense — denoise adversarial inputs before classification, leveraging the generative model's prior over natural images.

## From Discrete Layers to Continuous Dynamics

**[[neural-odes-and-continuous-models]]** provides a unifying mathematical framework connecting several architectures:

- **[[skip-connections]]** are what make the ODE interpretation possible: the ResNet update $h_{t+1} = h_t + f(h_t)$ is an Euler discretization of $dh/dt = f(h)$. Without the residual connection, there's no continuous-time analogue.
- **[[state-space-models]]** are linear ODEs — S4 and Mamba restrict the dynamics to $dx/dt = Ax + Bu$, gaining parallelizability at the cost of requiring nonlinearity to be injected between layers rather than within the dynamics.
- **[[diffusion-models]]** are Neural SDEs — the forward noising is a stochastic differential equation, and the reverse denoising can be formulated as either an SDE or a probability flow ODE. **Flow matching** (from Neural ODE theory) directly powers Stable Diffusion 3 and Flux.
- **[[text-to-image-generation]]**: the shift from DDPM-style discrete schedules to rectified flow / flow matching in SD3/Flux represents the continuous-time perspective winning in practice — simpler training, fewer sampling steps, straighter paths from noise to data.
- **[[recurrent-neural-networks]]**: Neural ODEs are continuous-time RNNs, handling irregular time series that discrete-step RNNs struggle with. The ODE-RNN hybrid evolves state continuously between observations and discretely at observation times.

## The Attention Efficiency Revolution

**[[efficient-attention-variants]]** is the engineering layer that makes the Transformer's theoretical capabilities practically realizable:

- **[[attention-and-transformers]]**: Flash Attention doesn't change the math of attention — it changes the *implementation*, exploiting the GPU memory hierarchy to achieve 2–4× speedup while computing bit-identical results. This is a pure systems optimization, not an approximation.
- **[[gpu-and-accelerator-hardware]]**: Flash Attention is designed around the A100/H100 memory hierarchy (SRAM vs. HBM). Each Flash Attention version is co-designed with the latest GPU architecture — FA3 for Hopper's TMA and FP8 cores. Hardware and algorithm co-evolve.
- **[[inference-optimization]]**: GQA reduces KV-cache by sharing key-value heads across query heads, directly enabling larger batch sizes and longer contexts during serving. PagedAttention manages KV-cache like virtual memory pages. These are the practical techniques that make 100K+ context windows affordable.
- **[[state-space-models]]**: SSMs offer $O(n)$ as an alternative to attention's $O(n^2)$. The practical question isn't whether linear is better than quadratic in theory — it's whether Flash Attention + GQA makes quadratic attention fast enough that SSMs' quality gap matters more than their efficiency advantage.
- **[[large-language-models]]**: the jump from 4K (GPT-3) to 1M+ (Gemini) context was enabled by the combination of Flash Attention, GQA, RoPE extension (**[[positional-encoding]]**), and ring attention (**[[distributed-training]]**). No single innovation — a stack of efficiency gains.
- **Streaming LLM and attention sinks** reveal a surprising property: initial tokens receive disproportionate attention regardless of content. This "attention sink" phenomenon connects to **[[interpretability]]** — understanding *why* attention flows this way could reveal fundamental properties of Transformer computation.

## Augmentation as the Universal Regularizer

**[[data-augmentation]]** is the most consistently effective technique across the knowledge base, touching virtually every application domain:

- **[[regularization]]**: augmentation is the most effective regularizer in practice — more impactful than dropout or weight decay for most vision tasks. Cutout and dropout share the principle of forcing redundant representations.
- **[[self-supervised-learning]]**: contrastive learning (SimCLR, MoCo, BYOL) is fundamentally *augmentation-driven* — the entire learning objective is to produce invariant representations across augmented views. The choice of augmentation defines what invariances the model learns.
- **[[image-classification-milestones]]**: DeiT showed that heavy augmentation (RandAugment + mixup + CutMix + random erasing) can substitute for massive pre-training data — a ViT trained on ImageNet-1K with aggressive augmentation nearly matches ViT trained on JFT-300M.
- **[[generalization-theory]]**: augmentation can be formalized as vicinal risk minimization (mixup) or as adding an implicit regularization term. The theory predicts that weaker architectural bias requires stronger augmentation — exactly what we observe with ViTs vs. CNNs.
- **[[adversarial-robustness]]**: adversarial training is a form of worst-case augmentation. Milder augmentations (mixup, CutMix) provide partial robustness improvements without the full cost of adversarial training.

## Predicting the Future: World Models and Intelligence

**[[world-models-and-predictive-learning]]** connects the aspiration of understanding intelligence to concrete architectures:

- **[[reinforcement-learning]]**: world models enable model-based RL — Dreamer and MuZero learn environment dynamics, enabling planning in imagination rather than expensive real-world interaction. This is orders of magnitude more sample-efficient than model-free RL.
- **[[self-supervised-learning]]**: JEPA (I-JEPA, V-JEPA) proposes that the right SSL objective is prediction in representation space, not pixel space. This challenges masked image modeling (MAE) and connects SSL to the broader goal of learning world dynamics.
- **[[video-understanding-and-generation]]**: Sora was described as a "world simulator" — video generation implicitly learns physical dynamics, object permanence, and 3D consistency. The boundary between video generation and world modeling is dissolving.
- **[[autoencoders]]**: VAEs and VQ-VAEs provide the perception component of world models (compress observations to latent space). IRIS tokenizes observations with VQ-VAE, connecting world modeling to the autoregressive paradigm of **[[large-language-models]]**.
- **[[diffusion-models]]**: diffusion-based world models (UniSim) use the generative model as a universal simulator. The connection flows both ways — diffusion training can be viewed as learning to model the dynamics of a noise process.

## The Reasoning Revolution

**[[reasoning-in-llms]]** represents the most significant capability shift since in-context learning:

- **[[prompt-engineering-and-in-context-learning]]**: CoT prompting showed that reasoning capabilities are latent in pre-trained models — they just need to be elicited. Reasoning models (o1, R1) internalize this through RL training, making explicit prompting unnecessary.
- **[[reinforcement-learning]]**: RL (PPO, GRPO) is the primary training method for reasoning models. The key insight from R1-Zero: RL can discover reasoning strategies (self-verification, backtracking, approach switching) without human-written examples.
- **[[scaling-laws]]**: test-time compute scaling introduces a second axis — performance improves not just with larger models but with more inference tokens. The interaction between training and inference scaling is the new frontier of scaling law research.
- **[[ai-safety-and-alignment]]**: hidden reasoning chains raise new safety concerns — models that reason internally about how to appear aligned while pursuing misaligned goals. Process reward models (PRMs) offer a potential solution by supervising intermediate steps.
- **[[knowledge-distillation]]**: reasoning capabilities can be distilled from large reasoning models to small ones via trace-based training — R1's distilled models show that even 1.5B models can learn effective reasoning from 671B model traces.

## Post-Training Composition

**[[model-merging-and-editing]]** introduces a new paradigm for creating capable models without training:

- **[[loss-landscape-geometry]]**: model merging works because fine-tuned models remain in the same loss basin as the pre-trained base. Linear mode connectivity, flat minima, and the structure of the loss landscape determine whether merging succeeds.
- **[[transfer-learning]]**: task arithmetic ($\tau = \theta_{\text{ft}} - \theta_{\text{pre}}$) formalizes the "knowledge gained during fine-tuning" as a vector. Adding, subtracting, and combining these vectors is a form of transfer without retraining.
- **[[interpretability]]**: ROME's causal tracing reveals that factual knowledge is stored in MLP layers, validating the "MLP as key-value memory" interpretation. Knowledge editing is both a practical tool and an interpretability probe.
- **[[continual-learning]]**: MEMIT (mass editing) addresses the same challenge — updating specific knowledge without catastrophic forgetting. The constrained least-squares formulation is a precision tool where EWC is a blunt one.
- **[[training-techniques]]**: model merging is an alternative to multi-task fine-tuning — combine separately fine-tuned models instead of training on all tasks jointly. The open-source community has shown this can be surprisingly effective.

## Adaptation at Every Stage

**[[test-time-adaptation]]** completes a spectrum of adaptation approaches across the ML lifecycle:

- **Pre-training** (**[[self-supervised-learning]]**): learn general representations from unlabeled data
- **Fine-tuning** (**[[transfer-learning]]**): adapt to the target task with labeled data
- **In-context learning** (**[[prompt-engineering-and-in-context-learning]]**): adapt via examples in the prompt (no weight updates)
- **Test-time adaptation** (**[[test-time-adaptation]]**): adapt to the specific test distribution during inference

This spectrum reveals a deep connection: attention, SSMs, and TTT layers are all mechanisms for processing context, differing in how they adapt to new information:
- **Attention** (**[[attention-and-transformers]]**): data-dependent weighted average (no parameter updates)
- **SSMs** (**[[state-space-models]]**): linear state update (fixed dynamics, data-dependent selection in Mamba)
- **TTT layers**: gradient-based parameter updates (most expressive adaptation)

The unifying principle is that intelligence requires adaptation at multiple timescales — from the long timescale of pre-training to the short timescale of processing each token.

## Opening the Black Box: Mechanistic Understanding

**[[mechanistic-interpretability]]** provides the microscope for examining what models actually compute:

- **[[interpretability]]**: mechanistic interpretability goes deeper than attribution methods or probing classifiers — it aims to reverse-engineer the *algorithm*, not just measure *what information is present*. The residual stream framework decomposes Transformer computation into additive contributions from individual heads and MLPs.
- **[[attention-and-transformers]]**: induction heads (a two-head circuit for in-context copying) and the IOI circuit (26 heads for indirect object identification) are concrete examples of algorithms discovered inside Transformers. These circuits provide ground truth for what attention heads do.
- **[[ai-safety-and-alignment]]**: sparse autoencoders applied to Claude 3 Sonnet found features for "deception," "sycophancy," and "power-seeking" — safety-relevant concepts that could enable automated monitoring. Representation engineering allows steering model behavior by adding/subtracting learned concept directions.
- **[[model-merging-and-editing]]**: ROME's causal tracing is mechanistic interpretability applied to knowledge editing — locating where factual associations are stored (MLP layers) and surgically modifying them. This validates the "MLP as key-value memory" hypothesis.
- **[[generalization-theory]]**: grokking was first explained mechanistically — Nanda et al. showed that the transition from memorization to generalization corresponds to the formation of generalizing circuits, with weight decay driving the shift.
- **Superposition** is the central obstacle: networks represent more features than they have dimensions, making individual neurons polysemantic. Sparse autoencoders are the primary tool for disentangling superposed features, but the decomposition may not be unique.

## The Pre-Training Foundation

**[[language-model-pretraining]]** is the most expensive and consequential decision in the LLM pipeline:

- **[[self-supervised-learning]]**: masked language modeling (BERT) and causal language modeling (GPT) are SSL objectives for text. The convergence to CLM/decoder-only reflects that generation capability is more versatile than bidirectional understanding alone.
- **[[scaling-laws]]**: the compute-optimal balance between model size and training tokens (Chinchilla scaling) is a pre-training design decision. The "data wall" (~10T high-quality English tokens) constrains scaling, pushing toward synthetic data and multilingual sources.
- **[[tokenization]]**: the tokenizer is fixed before pre-training and determines how efficiently the model processes text. Vocabulary size, subword algorithm, and multilingual coverage are pre-training-time decisions.
- **[[embeddings-and-representation-learning]]**: encoder-only models (BERT, DeBERTa) remain dominant for embeddings/retrieval on the MTEB benchmark, even as decoder-only models dominate generation. The architecture choice determines the model's suitability for different representation tasks.
- **[[reward-modeling-and-rlhf]]**: pre-training determines the capability ceiling; RLHF/DPO shapes how those capabilities are expressed. The quality of pre-training fundamentally limits what post-training can achieve.

## The Theory-Practice Dialogue

**[[optimization-theory-for-deep-learning]]** attempts to explain the empirical success of SGD on non-convex landscapes:

- **[[gradient-descent]]** and **[[loss-landscape-geometry]]**: the edge of stability shows that training dynamics self-organize to the stability boundary ($\lambda_{\max} \approx 2/\eta$). Progressive sharpening followed by stabilization is not predicted by classical convergence theory.
- **[[generalization-theory]]**: implicit bias explains *which* solution SGD finds (minimum norm, max margin), connecting optimization to generalization. The NTK vs. feature learning distinction may explain why depth and scale help — richer feature learning, not just better kernel approximation.
- **[[normalization-techniques]]** and **[[optimization-beyond-sgd]]**: practical techniques (BN, Adam, warmup, SAM) are designed based on partial theoretical understanding. SAM explicitly targets flat minima — the same geometry that SGD's implicit bias converges to naturally.
- **[[scaling-laws]]**: the $\mu$P parameterization (Yang & Hu) ensures that hyperparameters transfer across model scales, directly applying optimization theory to practical scaling. Understanding the feature-learning regime is key to understanding why scaling works.

## Perception in the Physical World

**[[autonomous-driving-perception]]** is deep learning's most demanding real-world deployment:

- **[[object-detection]]**: 3D object detection extends 2D detection to bounding boxes with depth, rotation, and velocity. CenterPoint applies the anchor-free paradigm to 3D, while BEVFormer brings Transformer attention to spatial reasoning in bird's-eye view.
- **[[3d-vision-and-neural-rendering]]**: point cloud processing (PointNet → PointPillars), voxel representations, and depth estimation are core to the perception stack. The BEV paradigm unifies 2D camera features and 3D LiDAR data in a common representation.
- **[[multimodal-models]]**: sensor fusion (LiDAR + cameras + radar) is fundamentally multimodal. BEVFusion creates modality-specific BEV representations and fuses them — analogous to how multimodal LLMs fuse text and image features.
- **[[world-models-and-predictive-learning]]**: end-to-end driving increasingly uses learned world models for planning. UniAD jointly trains perception, prediction, and planning — the most complete end-to-end driving system in the literature.

## Deep Learning Meets Biology

**[[protein-and-molecular-deep-learning]]** demonstrates deep learning's transformative impact on science:

- **[[attention-and-transformers]]**: AlphaFold2's Evoformer is a specialized Transformer with triangle attention enforcing geometric consistency. Protein language models (ESM) are standard Transformers applied to amino acid sequences — the same architecture that powers LLMs powers protein structure prediction.
- **[[graph-neural-networks]]**: molecular property prediction uses GNNs on molecular graphs. Equivariant GNNs (EGNN, SchNet, DimeNet) respect 3D symmetries that standard GNNs ignore, dramatically improving molecular modeling.
- **[[diffusion-models]]**: RFdiffusion applies diffusion to protein backbone design — generating novel proteins from noise. AlphaFold3 uses a diffusion module for structure generation. Equivariant diffusion models (EDM) generate 3D molecules.
- **[[self-supervised-learning]]**: protein LMs learn evolutionary and structural information solely from sequences, paralleling how NLP language models learn linguistic structure from text. The success validates the pre-training paradigm beyond human language.
- **[[language-model-pretraining]]**: the BERT/GPT paradigm transfers directly to biological sequences — ESM uses masked prediction on amino acids, ProtGPT2 uses autoregressive generation, and genomic models (Enformer, Evo) pre-train on DNA sequences.

## Deep Learning in the Clinic

**[[medical-imaging]]** is where deep learning meets the highest stakes — clinical deployment with safety-critical consequences:

- **[[semantic-segmentation]]**: U-Net was designed for biomedical segmentation and remains the dominant architecture. nnU-Net (self-configuring U-Net) consistently outperforms task-specific architectures across 23+ medical segmentation challenges — validating the principle that careful engineering beats novel architecture design.
- **[[federated-learning]]**: the primary solution for the fundamental tension between data-hungry models and patient privacy. FL enables training across hospitals without sharing data, but introduces communication costs, non-IID challenges, and questions about whether privacy truly holds against sophisticated attacks.
- **[[self-supervised-learning]]**: addresses annotation scarcity — expert radiologist labels cost $50–500 per image. Medical foundation models (BiomedCLIP, MedSAM) use contrastive and masked pre-training on unlabeled medical images, then fine-tune with limited labels.
- **[[bayesian-deep-learning]]**: uncertainty quantification is not optional in clinical AI — models must flag uncertain predictions for human review. Calibrated confidence estimates can determine the boundary between AI-automated screening and cases requiring radiologist attention.
- **[[data-augmentation]]**: critical for small medical datasets. Domain-specific augmentations (elastic deformation for histopathology, intensity jittering for MRI) supplement standard geometric transforms.

## The NLP Task Landscape

**[[nlp-tasks]]** maps the territory that language models have progressively unified:

- **[[language-model-pretraining]]**: the shift from task-specific architectures (BiLSTM-CRF for NER, seq2seq for MT) to a single pre-trained model (BERT/T5/GPT) fine-tuned per task, to a single model handling all tasks via prompting, is the central arc of modern NLP.
- **[[attention-and-transformers]]**: the Transformer was designed for machine translation ("Attention Is All You Need") and became the universal NLP architecture. The attention mechanism replaced recurrence entirely — seq2seq attention (Bahdanau, 2015) was the direct precursor.
- **[[retrieval-augmented-generation]]**: open-domain QA — once requiring dedicated retrieval + reading comprehension pipelines — is now solved by RAG (retrieve relevant passages, generate answers). The task drove the architecture.
- **[[embeddings-and-representation-learning]]**: NER, classification, and semantic search still benefit from encoder models (BERT-class) that produce fixed-size representations. Task-specific fine-tuned small models remain 100× faster and cheaper than LLM inference.
- **[[prompt-engineering-and-in-context-learning]]**: the paradigm shift from fine-tuning to prompting means that "NLP engineering" increasingly means "prompt engineering" — designing inputs rather than architectures.

## The Energy Landscape of Learning

**[[energy-based-models-and-contrastive-learning]]** provides the theoretical backbone of self-supervised learning:

- **[[self-supervised-learning]]**: contrastive learning (SimCLR, MoCo) is the practical application of energy-based principles — the InfoNCE loss sculpts an energy landscape where positive pairs sit in low-energy valleys and negatives on high-energy peaks. Non-contrastive methods (BYOL, VICReg, Barlow Twins) prevent collapse through architectural asymmetry or explicit regularization rather than negative samples.
- **[[diffusion-models]]**: score-based diffusion IS energy-based modeling via denoising score matching. The connection: $\nabla_x \log p(x) = -\nabla_x E(x)$ — the denoising network estimates the gradient of the energy function. This unifies generative modeling and representation learning under the EBM umbrella.
- **[[loss-functions]]**: InfoNCE is a $(N)$-way softmax cross-entropy loss with information-theoretic properties. Temperature $\tau$ controls the effective hardness of negative mining. The uniformity-alignment decomposition (Wang & Isola) connects the loss to geometric properties of the embedding space.
- **[[data-augmentation]]**: augmentation *defines* contrastive learning — it determines which pairs are "positive" (similar) and thus what invariances the representation learns. The spectral theory (HaoChen et al.) formalizes this: augmentations define a graph, and contrastive learning computes its spectral decomposition.

## The First Weight: Initialization

**[[neural-network-initialization]]** determines whether training succeeds or fails before a single gradient step:

- **[[backpropagation]]**: initialization directly determines gradient magnitudes. Too-small weights → vanishing gradients; too-large → exploding gradients. Xavier and He initialization calculate the "just right" scale for signal propagation.
- **[[activation-functions]]**: the activation function determines the correct variance factor — ReLU halves the variance (requiring the factor of 2 in He init), while linear/tanh activations preserve variance (Xavier). GELU, SiLU, and others have their own corrections.
- **[[normalization-techniques]]**: normalization layers (BN, LN) partially compensate for bad initialization by rescaling activations. Fixup and T-Fixup show that proper initialization can *replace* normalization entirely — the two are partially redundant.
- **[[optimization-theory-for-deep-learning]]**: $\mu$P connects initialization to the NTK vs. feature learning distinction. Standard parameterization pushes wide networks toward lazy training; $\mu$P ensures feature learning persists at any width, enabling hyperparameter transfer from small to large models.
- **[[skip-connections]]**: residual connections accumulate variance across layers ($\text{Var} \approx L \cdot \text{Var}(f)$). Zero initialization of residual branches (fixup-style) makes the network start as the identity, enabling very deep training.

## Physical Intelligence

**[[robotics-and-embodied-ai]]** extends deep learning from virtual to physical domains:

- **[[reinforcement-learning]]**: RL (PPO, SAC) is the primary training paradigm for robotic control, but sample efficiency is the bottleneck — real-world RL accumulates only ~36K steps per hour. Sim-to-real transfer and offline RL address this.
- **[[world-models-and-predictive-learning]]**: Dreamer-style model-based RL learns environment dynamics for sample-efficient robot learning. World models enable planning in imagination before acting in the real world.
- **[[multimodal-models]]**: RT-2 demonstrates that vision-language models can directly output robot actions — the VLM's understanding of objects, spatial relations, and language transfers to physical manipulation. This is the multimodal paradigm applied to control.
- **[[agents-and-tool-use]]**: LLM-based robot planning (SayCan, Code as Policies) uses LLMs as high-level planners with robot skills as "tools." The agent paradigm maps directly to robotics: observe → reason → plan → act → observe.
- **[[diffusion-models]]**: diffusion policies represent multimodal action distributions — multiple valid ways to grasp an object, different paths to a goal. This is a natural application of diffusion's ability to model complex distributions.
- **[[data-augmentation]]**: domain randomization IS augmentation for sim-to-real — randomly varying visual and physical simulation parameters makes policies robust to real-world variation, just as image augmentation makes classifiers robust to visual variation.

## Temporal Prediction: From Statistics to Foundation Models

**[[time-series-forecasting]]** reveals the persistent tension between classical simplicity and deep learning complexity:

- **[[autoregressive-models]]**: DeepAR and Chronos are autoregressive models for time series — the same next-token prediction paradigm that powers LLMs, applied to continuous-valued sequences. Chronos literally tokenizes real numbers into bins and trains a T5 language model.
- **[[attention-and-transformers]]**: PatchTST adapts the ViT recipe (patch → token → Transformer) from images to time series. The "DLinear controversy" — a single linear layer outperforming Transformers — forced the field to reconsider whether attention is genuinely beneficial for temporal data.
- **[[scaling-laws]]**: time series foundation models (TimesFM, Chronos, Moirai) test whether the pre-training scaling paradigm transfers from text to temporal data. Early evidence is positive, but the heterogeneity of time series (finance vs. weather vs. retail) may limit universal scaling.
- **[[self-supervised-learning]]**: PatchTST's masked patch prediction mirrors MAE for images. Foundation models pre-train via next-value prediction on diverse corpora — the same self-supervised principle across modalities.
- **[[bayesian-deep-learning]]**: probabilistic forecasting (DeepAR, Chronos) naturally connects to Bayesian uncertainty — calibrated prediction intervals are essential for real-world decision-making under uncertainty.

## The Recommendation Pipeline

**[[recommender-systems]]** is the highest-scale deployment of deep learning, serving billions of users at millisecond latency:

- **[[embeddings-and-representation-learning]]**: user and item embeddings are the core data structure. The two-tower architecture — pre-compute item embeddings, retrieve via ANN search — is the same pattern used in semantic search and RAG.
- **[[autoregressive-models]]**: SASRec applies GPT-style causal attention to item sequences — next-item prediction IS next-token prediction. The user's interaction history is a "sentence" of items, and recommendation is language modeling over a vocabulary of products.
- **[[attention-and-transformers]]**: DIN (Deep Interest Network) uses attention over user history to weight relevant past interactions for each candidate item. BERT4Rec applies bidirectional attention with masked item prediction — the BERT paradigm for items instead of words.
- **[[inference-optimization]]**: serving recommendations at millions of QPS requires extreme optimization — DLRM's embedding tables exceed 1TB, demanding distributed serving, quantization, and efficient ANN search (FAISS, ScaNN).
- **[[large-language-models]]**: LLMs as recommendation engines leverage world knowledge about items but lack collaborative signal and face latency/cost barriers for real-time serving. The practical path is LLMs enriching features rather than replacing the pipeline.

## Audio as Language

**[[audio-generation]]** demonstrates the convergence of generation paradigms across modalities:

- **[[autoencoders]]**: neural codecs (SoundStream, EnCodec) are VQ-VAEs for audio — encoder compresses 24kHz waveform to 75Hz discrete tokens via residual vector quantization. These codecs bridge continuous audio and discrete language modeling.
- **[[autoregressive-models]]**: VALL-E and MusicGen treat audio generation as language modeling over codec tokens. The same Transformer architecture that generates text generates speech and music — unified by the token abstraction.
- **[[diffusion-models]]**: AudioLDM and Stable Audio apply latent diffusion to audio, mirroring the Stable Diffusion pipeline — VAE for compression, diffusion in latent space, text conditioning via CLAP (the audio equivalent of CLIP).
- **[[generative-adversarial-networks]]**: HiFi-GAN remains the de facto standard vocoder — GAN-based waveform generation is 100× faster than WaveNet with comparable quality. Adversarial training is also central to neural codec training.
- **[[tokenization]]**: audio codecs ARE tokenizers for audio. RVQ (residual vector quantization) creates a hierarchical token vocabulary — coarse tokens capture structure, fine tokens add acoustic detail. This mirrors BPE's variable-granularity tokenization for text.

## The Fairness-Accuracy Tension

**[[fairness-and-bias]]** introduces unavoidable trade-offs that affect every application domain:

- **[[ai-safety-and-alignment]]**: bias is a core safety concern. RLHF and Constitutional AI aim to reduce harmful outputs, but the alignment tax may disproportionately affect performance on minority-group queries. Fairness and alignment are deeply intertwined.
- **[[data-engineering]]**: bias enters primarily through data — historical bias, representation bias, measurement bias, sampling bias. Data curation, filtering, and augmentation are the first line of defense, but can't fully compensate for societal inequities reflected in training data.
- **[[medical-imaging]]**: Gichoya et al. (2022) showed AI models can predict patient race from X-rays even when radiologists cannot — raising concerns about shortcut features with direct clinical consequences. Fairness auditing is particularly high-stakes in healthcare.
- **[[text-to-image-generation]]**: image generation amplifies training data stereotypes — "CEO" generates predominantly white men, "nurse" predominantly white women. Debiasing generation models requires intervention at data, model, and deployment levels.
- **[[recommender-systems]]**: recommendation algorithms amplify popularity bias and can discriminate in exposure and opportunity. Fairness-aware ranking and diversity constraints are increasingly required by regulation (EU AI Act, NYC LL144).

## The Hardware-Algorithm Co-Evolution

**[[hardware-software-co-design]]** reveals that deep learning performance is fundamentally a systems engineering challenge:

- **[[gpu-and-accelerator-hardware]]**: the memory hierarchy (registers → SRAM → L2 → HBM) determines which operations are compute-bound vs. memory-bound. The arithmetic intensity threshold (156 FLOP/byte on A100) is the fundamental metric — most element-wise operations are memory-bound, driving the need for kernel fusion.
- **[[efficient-attention-variants]]**: Flash Attention is the canonical co-design example — same mathematical operation, 2–4× speedup through hardware-aware memory access patterns. Flash Attention 3 exploits H100's FP8 tensor cores and asynchronous compute for further gains.
- **[[inference-optimization]]**: production serving (vLLM, TensorRT, llama.cpp) heavily relies on fused kernels, quantization-hardware alignment, and memory management. The actual speedup from INT4 quantization depends entirely on whether the hardware has INT4 compute units.
- **[[neural-network-compression]]**: NVIDIA's 2:4 structured sparsity provides guaranteed 2× hardware-accelerated speedup — but ONLY when pruning follows the exact 2-of-4 pattern. The hardware constraint dictates the pruning algorithm.
- **[[quantization]]**: quantization is only useful when the target precision is hardware-accelerated. INT4 quantization + INT4 tensor cores = actual speedup. INT4 quantization on hardware without INT4 support = no speedup. The precision-hardware matrix determines what's practical.

## From 2D to 3D: Lifting Generative Models

**[[3d-generation-deep-dive]]** shows how 2D generative knowledge transfers to 3D content creation:

- **[[diffusion-models]]**: Score Distillation Sampling (SDS) is the key bridge — a 2D diffusion model's score function provides gradients that optimize a 3D representation, bypassing the need for 3D training data entirely. VSD (ProlificDreamer) improves on SDS by modeling the rendered distribution explicitly.
- **[[3d-vision-and-neural-rendering]]**: NeRF variants (Instant-NGP, Zip-NeRF) and 3DGS provide the 3D representations that text-to-3D optimizes. The shift from NeRF to 3DGS parallels the broader shift from implicit to explicit representations — explicit representations are faster and easier to manipulate.
- **[[text-to-image-generation]]**: text-to-3D pipelines build directly on text-to-image models. Multi-view diffusion (MVDream, Wonder3D) generates consistent views, sidestepping SDS's mode-seeking artifacts. The quality of 3D generation is bounded by 2D generation quality.
- **[[gpu-and-accelerator-hardware]]**: 3DGS's real-time rendering exploits GPU rasterization pipelines, while NeRF's ray marching fights GPU architecture. Hardware alignment determines which 3D representation is practical.

## The Instruction-Following Bridge

**[[instruction-tuning-and-multi-task-learning]]** is the critical middle step in modern LLM development:

- **[[language-model-pretraining]]**: pre-training provides raw capability; instruction tuning teaches the model to express that capability on demand. The quality of pre-training determines the ceiling of what instruction tuning can unlock.
- **[[reward-modeling-and-rlhf]]**: the modern pipeline is pre-training → SFT (instruction tuning) → RLHF/DPO. SFT provides the supervised foundation; RLHF polishes output quality. LIMA showed that just 1,000 high-quality SFT examples can produce strong results.
- **[[synthetic-data-generation]]**: Self-Instruct, Alpaca, and Evol-Instruct generate instruction data synthetically. The instruction tuning stage is increasingly powered by AI-generated data, with GPT-4/Claude generating training data for smaller models.
- **[[nlp-tasks]]**: the traditional NLP task zoo (NER, MT, QA, summarization) provides the training tasks for FLAN-style instruction tuning. Training on diverse NLP tasks enables zero-shot generalization to unseen tasks.
- **[[scaling-laws]]**: instruction tuning has its own scaling laws — benefits increase with model size and task diversity, with diminishing returns beyond ~1,000 tasks.

## Correlation vs. Causation

**[[causal-inference-and-deep-learning]]** provides the theoretical framework for understanding *why* models fail under distribution shift:

- **[[generalization-theory]]**: causal features generalize across environments while spurious correlations don't. IRM formalizes this — learn representations where the optimal classifier is invariant across environments. Shortcut learning (Geirhos et al.) is the failure to learn causal features.
- **[[fairness-and-bias]]**: counterfactual fairness defines fairness through causal models — would the prediction change if the protected attribute were different? Causal reasoning distinguishes legitimate from illegitimate use of demographic features.
- **[[adversarial-robustness]]**: adversarial examples exploit non-causal features. Models relying on causal features should be more robust to perturbations that change spurious correlations while preserving causal structure.
- **[[data-augmentation]]**: augmentation breaks spurious correlations by creating artificial environments. CutMix destroys background context (spurious), forcing reliance on object features (causal). The causal perspective explains why augmentation improves out-of-distribution generalization.
- **[[interpretability]]**: causal models are inherently interpretable (the DAG shows why). Mechanistic interpretability (**[[mechanistic-interpretability]]**) seeks causal circuits inside neural networks — activation patching IS causal intervention.

## Measuring Progress: The Evaluation Challenge

**[[evaluation-and-benchmarking]]** reveals that how we measure models is as important as how we build them:

- **[[scaling-laws]]**: benchmarks are how we validate that scaling delivers capability. The Chinchilla scaling law was measured through benchmark performance. But the evaluation gap — the difference between benchmark scores and real-world utility — challenges whether these gains are meaningful.
- **[[reasoning-in-llms]]**: reasoning is the hardest capability to evaluate. GSM8K is nearly saturated, but models still fail on slightly rephrased versions. Process reward models provide step-level evaluation, but verifying reasoning faithfulness remains open.
- **[[nlp-tasks]]**: the shift from task-specific benchmarks (GLUE, SQuAD) to unified LLM benchmarks (MMLU, MT-Bench, Chatbot Arena) mirrors the shift from task-specific to general models. Benchmark contamination threatens the validity of all text-based benchmarks.
- **[[prompt-engineering-and-in-context-learning]]**: benchmark scores depend heavily on prompt format — zero-shot vs. few-shot, chain-of-thought, multiple-choice ordering all affect results. "Fair" comparison between models requires careful prompt standardization.
- **[[fairness-and-bias]]**: disaggregated evaluation across demographic groups is essential. High average accuracy can mask poor performance on minority subgroups. BBQ and WinoBias specifically test for social biases.

## Privacy as a Fundamental Constraint

**[[privacy-preserving-ml]]** imposes hard constraints on what data can be used and how:

- **[[federated-learning]]**: FL keeps data decentralized but alone doesn't provide formal privacy guarantees. FL + differential privacy provides stronger protection; secure aggregation (MPC) prevents the server from seeing individual gradients.
- **[[large-language-models]]**: LLMs memorize and can regurgitate training data (Carlini et al.). Training data extraction is a demonstrated attack. DP pre-training is impractical at LLM scale; DP fine-tuning on private data + public pre-training is the current best practice.
- **[[medical-imaging]]**: patient privacy (HIPAA, GDPR) is a binding legal constraint. DP fine-tuning and federated learning enable training on medical data while (approximately) preserving patient privacy.
- **[[fairness-and-bias]]**: differential privacy adds uniform noise, but minority groups (with fewer examples) suffer disproportionate utility loss. The privacy-fairness tension is a concrete instance of how privacy protections can inadvertently amplify bias.
- **[[transfer-learning]]**: pre-train on public data + DP fine-tune on private data is the dominant privacy paradigm. LoRA + DP reduces the noise dimension, making private fine-tuning more practical.

## The Tuning Tax

**[[hyperparameter-optimization]]** addresses the hidden cost behind every deep learning result:

- **[[optimization-beyond-sgd]]**: learning rate is almost always the most important hyperparameter. The interplay between learning rate, batch size, and weight decay determines whether training converges, oscillates, or diverges. HPO automates finding these critical values.
- **[[optimization-theory-for-deep-learning]]**: μP provides theoretical hyperparameter transfer — tune on a small proxy model, transfer to the full-scale model. This directly applies optimization theory to make HPO practical at frontier scale.
- **[[neural-architecture-search]]**: NAS is HPO for architecture. The search methods overlap (Bayesian optimization, evolutionary, multi-fidelity), and joint architecture + hyperparameter search is increasingly common.
- **[[scaling-laws]]**: HPO cost scales with model training cost. For a 100B model where each training run costs millions, efficient HPO (BOHB, μP transfer) isn't optional — it's the difference between practical and infeasible development.

## Structured vs. Parametric Knowledge

**[[knowledge-graphs-and-structured-knowledge]]** provides the structured counterpart to parametric knowledge stored in neural network weights:

- **[[retrieval-augmented-generation]]**: Graph RAG retrieves structured KG triples instead of flat text chunks, providing the LLM with entity relationships, not just relevant passages. KG-grounded generation reduces hallucination through verifiable facts.
- **[[graph-neural-networks]]**: R-GCN and CompGCN apply GNN message passing over KG structure — learning entity representations that incorporate multi-hop relational context. NBFNet generalizes shortest-path algorithms with learned operators.
- **[[large-language-models]]**: the tension between parametric knowledge (LLM weights) and explicit knowledge (KG triples) is central. LLMs hallucinate when parametric knowledge is wrong; KGs provide ground truth but lack natural language understanding. Integration of both is the practical solution.
- **[[model-merging-and-editing]]**: ROME and MEMIT edit factual knowledge in MLP layers — the parametric analogue of updating a KG triple. KGs provide the ground truth for which facts should be edited.

## Understanding Speech

**[[speech-recognition-deep-dive]]** shows how the Transformer paradigm conquered yet another modality:

- **[[speech-and-audio]]**: ASR is the input understanding complement to TTS/audio generation. Neural codecs (SoundStream, EnCodec) provide shared discrete representations for both ASR and generation, enabling unified speech models.
- **[[self-supervised-learning]]**: wav2vec 2.0 and HuBERT learn speech representations from unlabeled audio via contrastive and masked prediction objectives — directly paralleling BERT for text and MAE for images. Pre-training on 60K hours of unlabeled speech enables fine-tuning with just 10 minutes of labels.
- **[[attention-and-transformers]]**: Whisper's Transformer encoder-decoder and the Conformer's attention+convolution hybrid demonstrate that Transformers dominate speech just as they dominate text and vision. The same architecture generates and understands speech.
- **[[data-augmentation]]**: SpecAugment (masking frequency bands and time steps) is the universal ASR augmentation — simple, effective, and directly analogous to cutout/masking in vision.

## Learning from Few

**[[few-shot-and-zero-shot-learning]]** reveals a convergence: dedicated few-shot methods are being subsumed by foundation model capabilities:

- **[[meta-learning]]**: prototypical networks, MAML, and episodic training were the classical approaches — learn a metric space or an adaptable initialization. These remain relevant when foundation models aren't available, but increasingly foundation model + linear probe outperforms them.
- **[[self-supervised-learning]]**: CLIP's contrastive training on 400M image-text pairs enables zero-shot image classification — matching supervised baselines without any task-specific training. DINOv2 features provide strong few-shot representations. SSL is now the best few-shot feature extractor.
- **[[prompt-engineering-and-in-context-learning]]**: in-context learning IS few-shot learning via the prompt. GPT-3's demonstration that examples in the prompt enable task generalization blurred the boundary between few-shot learning and inference-time adaptation.
- **[[embeddings-and-representation-learning]]**: the quality of the embedding space determines few-shot performance. CLIP's text-image alignment enables zero-shot via natural language class descriptions. The geometric properties of the embedding (alignment, uniformity) predict few-shot accuracy.

## Processing the 3D World

**[[point-cloud-and-lidar-deep-learning]]** provides the geometric backbone for physical AI:

- **[[autonomous-driving-perception]]**: PointPillars, CenterPoint, and BEVFormer build on point cloud architectures for 3D detection and segmentation. The entire driving perception stack depends on efficient, accurate point cloud processing.
- **[[3d-vision-and-neural-rendering]]**: point clouds are the bridge between raw sensor data and 3D scene representations. PointNet features can seed NeRF/3DGS initialization; point cloud segmentation provides the geometric understanding that rendering builds upon.
- **[[attention-and-transformers]]**: Point Transformer brings self-attention to 3D, paralleling the CNN→ViT trajectory in 2D. Space-filling curve serialization enables efficient attention on unordered point sets.
- **[[graph-neural-networks]]**: point clouds viewed as k-NN graphs can be processed with graph convolutions (DGCNN). The local grouping in PointNet++ is a form of graph neighborhood aggregation.
- **[[self-supervised-learning]]**: Point-MAE applies masked autoencoding to point clouds; CLIP-aligned 3D features (OpenScene, Uni3D) enable zero-shot 3D understanding — querying 3D scenes with natural language.

## The Synthetic Data Bootstrap

**[[synthetic-data-generation]]** reveals how models create training data for other models — and potentially for themselves:

- **[[knowledge-distillation]]**: synthetic data generation IS distillation at scale. Alpaca distills GPT-3.5's instruction-following into LLaMA-7B for $500. Orca distills GPT-4's *reasoning process* (not just answers) into a 13B model. The Phi series takes this further — distilling "textbook-quality knowledge" from strong models into pre-training data for small ones.
- **[[data-engineering]]**: synthetic data is the fastest-growing data source, 100–1000× cheaper than human annotation. But it introduces new failure modes: model collapse (Shumailov et al., 2024) shows that recursive training on synthetic data degrades quality as distributional tails are progressively lost.
- **[[reasoning-in-llms]]**: reasoning models bootstrap their own training data through RL exploration (R1-Zero discovers reasoning strategies) and rejection sampling (generate many solutions, keep correct ones). STaR iteratively bootstraps reasoning chains. The boundary between synthetic data and RL exploration is dissolving.
- **[[scaling-laws]]**: Phi models suggest data *quality* can substitute for model *scale* — a 1.3B model trained on synthetic "textbook" data outperforms 10× larger models. This potentially shifts the compute-optimal frontier: instead of scaling the model, scale the data quality through stronger teacher models.
- **[[ai-safety-and-alignment]]**: Constitutional AI and RLAIF replace human preference labels with AI-generated preferences. The alignment pipeline increasingly relies on synthetic data at every stage — SFT examples, preference pairs, and red-team prompts.

## Compression: Making Scale Accessible

**[[neural-network-compression]]** bridges the gap between frontier model sizes and practical deployment constraints:

- **[[quantization]]**: pruning and quantization are multiplicatively complementary — a 70B model pruned 50% and quantized to INT4 fits in ~17GB (8× reduction). The combination enables consumer-GPU deployment of models that require clusters in their original form.
- **[[generalization-theory]]**: the lottery ticket hypothesis connects pruning to fundamental questions about overparameterization — networks are 80–95% redundant, and the "winning ticket" (sparse subnetwork) exists from random initialization. This partially explains *why* overparameterization helps: more parameters = more lottery tickets during training.
- **[[gpu-and-accelerator-hardware]]**: NVIDIA's 2:4 structured sparsity support on A100/H100 creates a hardware-algorithm co-design opportunity — prune exactly 2 of every 4 weights for guaranteed 2× hardware-accelerated speedup. SparseGPT and Wanda can target this pattern.
- **[[inference-optimization]]**: SparseGPT achieves 50% sparsity on 175B models in ~4 hours on a single GPU — one-shot pruning without retraining. Wanda is even simpler: score by weight magnitude × input activation, prune lowest, no weight updates needed. These make compression practical at the foundation model scale.
- **[[knowledge-distillation]]**: compression combines pruning, quantization, AND distillation for maximum effect (10–50× size reduction at ~3–5% quality loss). The distilled + pruned + quantized model pipeline is the standard path from frontier research to edge deployment.

## The Alignment Mechanics

**[[reward-modeling-and-rlhf]]** provides the technical depth behind the alignment pipeline introduced in [[ai-safety-and-alignment]]:

- **[[reinforcement-learning]]**: PPO is the workhorse but operationally painful (4 models in memory, hyperparameter-sensitive, unstable). GRPO (DeepSeek) simplifies by eliminating the value function — use group statistics as the baseline instead. The RL approach enables exploration beyond the preference data, which DPO cannot do.
- **[[loss-functions]]**: the Bradley-Terry model ($P(y_w \succ y_l) = \sigma(r_w - r_l)$) compresses human preferences into a scalar. DPO's reparameterization trick eliminates the explicit reward model entirely — the policy IS the implicit reward model. The mathematical relationship between DPO, KTO, IPO, and SimPO is one of loss function design choices.
- **[[scaling-laws]]**: Gao et al.'s reward overoptimization scaling law ($\text{Gold} = d\sqrt{\text{KL}} - c \cdot \text{KL}$) shows that proxy reward optimization has diminishing returns — at low KL, optimization helps; at high KL, the policy hacks the reward model. The $\beta$ parameter controls where on this curve training stops.
- **[[synthetic-data-generation]]**: RLAIF replaces human annotators with AI judges for preference data. The quality of synthetic preference data determines alignment quality — but introduces the teacher model's biases.
- **[[reasoning-in-llms]]**: process reward models (PRMs) provide step-level supervision for reasoning tasks, enabling much denser reward signal than outcome-level reward models. GRPO trains R1's reasoning through RL — the reward signal comes from verifiable correctness rather than human preferences.

## Retrieval as the Knowledge Interface

**[[retrieval-augmented-generation]]** provides LLMs with external knowledge, creating a fundamentally different architecture from pure parametric models:

- **[[embeddings-and-representation-learning]]**: embedding quality directly determines retrieval quality. The entire RAG pipeline depends on the geometric properties of the embedding space — semantic similarity must correspond to topical relevance. Hybrid retrieval (dense + sparse/BM25) consistently outperforms either alone.
- **[[large-language-models]]**: RAG addresses the three core limitations of parametric models: knowledge cutoff (retrieved docs are current), hallucination (answers are grounded in sources), and attribution (citations to specific chunks). The RAG vs. fine-tuning vs. long-context trade-off is the central architectural decision for enterprise AI.
- **[[long-context-and-memory-architectures]]**: as context windows grow (1M+ tokens), the RAG vs. long-context debate intensifies. For small document collections (<100K tokens), long context often outperforms RAG. For millions of documents, RAG is necessary. The boundary shifts as context windows expand.
- **[[prompt-engineering-and-in-context-learning]]**: RAG fundamentally relies on ICL — retrieved documents are presented as context that the model learns from at inference time. Query transformation (HyDE, multi-query, decomposition) applies prompt engineering to the retrieval stage.
- **[[agents-and-tool-use]]**: agentic RAG combines retrieval with reasoning — the agent decides when to retrieve, what queries to formulate, whether results are relevant, and when to re-retrieve. Self-RAG and CRAG formalize this decision-making with special tokens and corrective mechanisms.

## The Long-Context Revolution

**[[long-context-and-memory-architectures]]** represents the engineering frontier of making Transformers handle book-length and beyond:

- **[[positional-encoding]]**: position interpolation (rescale positions for longer sequences) and YaRN (frequency-band-aware scaling) are the foundation for context extension. The jump from 2K to 128K+ context was primarily a positional encoding innovation, requiring only ~1000 fine-tuning steps.
- **[[efficient-attention-variants]]**: Flash Attention makes long context computationally feasible, GQA keeps KV-cache manageable, and PagedAttention/H2O/Streaming LLM manage memory at inference time. Without these, million-token context is computationally impossible.
- **[[state-space-models]]**: SSMs offer $O(n)$ processing with $O(1)$ memory — the ultimate long-context architecture. Hybrid models (Jamba: 7:1 Mamba-to-attention ratio) combine SSM efficiency for most processing with occasional attention for precise retrieval, getting near-perfect recall at near-linear cost.
- **[[distributed-training]]**: ring attention distributes long sequences across devices in a ring topology, enabling context lengths proportional to device count. Combined with sequence parallelism, this enables training on 1M+ token sequences.
- **[[inference-optimization]]**: KV-cache management IS the long-context inference problem. For a 70B model at 128K context, KV-cache alone is ~100GB+ in FP16. Token dropping (keep "heavy hitter" tokens + recent window), quantization, and multi-scale compression make this practical.
