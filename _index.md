# Deep Learning — Knowledge Base Index

> A structured knowledge base on deep learning, seeded from François Fleuret's *The Little Book of Deep Learning* (2023) and supplemented with broader context.

## Foundations

| Article | Summary |
|---------|---------|
| [[tensors]] | Multi-dimensional arrays — the universal data structure storing values, parameters, and gradients in deep learning frameworks |
| [[gradient-descent]] | The core optimization algorithm: iteratively update parameters by stepping opposite to the gradient of the loss |
| [[backpropagation]] | Efficient gradient computation via the chain rule applied layer-by-layer from output to input (reverse-mode autodiff) |
| [[loss-functions]] | Functions quantifying prediction error — cross-entropy for classification, MSE for regression, contrastive loss for embeddings |
| [[activation-functions]] | Non-linear functions (ReLU, GELU, tanh) applied element-wise between layers, giving networks expressive power beyond linear transforms |

## Architecture Components

| Article | Summary |
|---------|---------|
| [[multilayer-perceptrons]] | The simplest deep architecture — stacked fully connected layers with activations — and the basis of the universal approximation theorem |
| [[convolutional-neural-networks]] | Architectures using local, shared filters for spatial/temporal data — from LeNet to ResNet, the standard for image processing |
| [[recurrent-neural-networks]] | Sequential architectures with internal memory (LSTM, GRU) — historically dominant for sequences, now largely superseded by Transformers |
| [[attention-and-transformers]] | The attention mechanism (data-dependent weighted averaging) and the Transformer architecture built on it — dominant for language, vision, and beyond |
| [[state-space-models]] | Linear recurrence architectures (S4, Mamba) that process sequences in linear time — the main Transformer challenger, combining RNN efficiency with parallelism |
| [[graph-neural-networks]] | Message-passing networks for graph-structured data (molecules, social networks, knowledge graphs) — GCN, GAT, GIN, and graph transformers |
| [[skip-connections]] | Shortcut paths that bypass layers, enabling gradient flow and training of networks with hundreds of layers (residual and concatenative variants) |
| [[regularization]] | Techniques preventing overfitting: dropout, batch normalization, layer normalization, weight decay, data augmentation, early stopping |

## Training and Scaling

| Article | Summary |
|---------|---------|
| [[autoregressive-models]] | Models that factor joint probability as a product of conditionals, predicting sequences one token at a time — the basis of language modeling |
| [[scaling-laws]] | Empirical power-law relationships between model size, data, compute, and performance — including compute-optimal (Chinchilla) scaling |
| [[training-techniques]] | Practical methods: pre-training/fine-tuning, RLHF alignment, LoRA adapters, mixed precision, learning rate schedules, model merging |
| [[distributed-training]] | Splitting training across multiple GPUs — data, model, and pipeline parallelism; ZeRO, FSDP, 3D parallelism |
| [[reinforcement-learning]] | Learning from rewards through environment interaction — MDPs, DQN, PPO, and RLHF for LLM alignment |
| [[knowledge-distillation]] | Compressing large teacher models into smaller students via soft label training — DistilBERT, Alpaca, progressive distillation for diffusion |
| [[generalization-theory]] | Why overparameterized networks generalize — double descent, grokking, implicit regularization by SGD, lottery ticket hypothesis |
| [[federated-learning]] | Distributed training across devices/institutions without centralizing data — FedAvg, non-IID challenges, differential privacy, healthcare and mobile deployments |
| [[neural-architecture-search]] | Automated architecture design via RL, evolution, or differentiable search (DARTS) — EfficientNet, hardware-aware NAS, compound scaling |
| [[meta-learning]] | Learning to learn from few examples — MAML, prototypical networks, metric-based and optimization-based approaches, and the connection to in-context learning in LLMs |
| [[curriculum-learning]] | Training on examples ordered easy-to-hard — self-paced learning, competence-based curricula, connections to continuation methods and loss landscape smoothing |
| [[continual-learning]] | Learning sequentially without catastrophic forgetting — EWC, experience replay, progressive networks, and the plasticity-stability trade-off |

## Theory and Optimization

| Article | Summary |
|---------|---------|
| [[information-theory]] | Shannon's framework applied to deep learning — entropy, mutual information, the information bottleneck principle, cross-entropy loss, and compression-based generalization explanations |
| [[loss-landscape-geometry]] | Structure of the loss surface — saddle points dominate over local minima, mode connectivity, flat vs. sharp minima, SGD's implicit bias, and Sharpness-Aware Minimization (SAM) |
| [[normalization-techniques]] | Stabilizing activations for trainability — Batch Normalization, Layer Normalization, RMSNorm, Group Normalization, their mathematical formulations, and when to use each |
| [[optimization-beyond-sgd]] | Advanced optimizers — Adam, AdamW, AdaFactor, LARS/LAMB for large-batch training, second-order methods, and learning rate schedules (warmup, cosine, 1cycle) |
| [[bayesian-deep-learning]] | Uncertainty quantification via Bayesian inference — MC Dropout, variational inference, deep ensembles, Laplace approximation, calibration, and out-of-distribution detection |
| [[positional-encoding]] | Injecting sequence order into Transformers — sinusoidal, learned, RoPE, ALiBi, and context length extension methods (YaRN, NTK-aware scaling) |
| [[hyperparameter-optimization]] | Systematic tuning — random search, Bayesian optimization (TPE, GP), Hyperband/ASHA, population-based training, μP for hyperparameter transfer across scales |
| [[causal-inference-and-deep-learning]] | Structural causal models, treatment effect estimation (TARNet, Double ML), causal discovery (NOTEARS), causal representation learning, IRM, causality for robustness |

## Data and Preprocessing

| Article | Summary |
|---------|---------|
| [[data-engineering]] | Collecting, curating, and managing training data — web scraping pipelines, labeling (human, programmatic, active), augmentation, synthetic data (Phi, Alpaca), deduplication, data mixing |
| [[tokenization]] | Converting raw text into discrete subword tokens — BPE, WordPiece, SentencePiece, Unigram, vocabulary size trade-offs, multilingual challenges, and byte-level approaches |
| [[data-augmentation]] | Expanding training data via label-preserving transforms — geometric (flips, crops), learned policies (RandAugment), sample mixing (mixup, CutMix), and the augmentation-architecture interaction |

## Generative Models

| Article | Summary |
|---------|---------|
| [[diffusion-models]] | Generative models that learn to reverse a noise-adding process, producing high-quality images from noise — DDPM, Stable Diffusion, DALL-E |
| [[generative-adversarial-networks]] | Two-player adversarial framework (generator vs. discriminator) that produces sharp images — StyleGAN, CycleGAN — largely superseded by diffusion models |
| [[autoencoders]] | Networks that learn compressed latent representations via reconstruction — VAEs add probabilistic structure enabling generation; VQ-VAE provides discrete codes; latent diffusion builds on VAE encoders |
| [[self-supervised-learning]] | Training paradigm where the model learns from the data itself — autoregressive prediction, masked modeling (BERT), contrastive learning (SimCLR, CLIP), and masked image modeling (MAE) |

## Hardware and Infrastructure

| Article | Summary |
|---------|---------|
| [[gpu-and-accelerator-hardware]] | The physical compute substrate — NVIDIA GPUs (V100 through B200), Google TPUs, AMD MI300X, memory hierarchy, the memory wall, mixed precision, interconnects, and cluster economics |

## Applications and Deployment

| Article | Summary |
|---------|---------|
| [[large-language-models]] | Large-scale autoregressive transformers (GPT, Claude, LLaMA) exhibiting in-context learning, reasoning, and broad language capabilities |
| [[agents-and-tool-use]] | LLM-based agents that reason, plan, and call external tools in a loop — ReAct, function calling, agent frameworks, and the path from AutoGPT to production coding agents |
| [[multimodal-models]] | Models processing text, images, audio, and video in unified architectures — CLIP, LLaVA, Gemini, GPT-4o, and the early fusion vs. late fusion debate |
| [[mixture-of-experts]] | Sparse activation architecture where a router selects a subset of expert FFNs per token — enabling much larger models at fixed compute (Mixtral, Switch Transformer) |
| [[inference-optimization]] | Techniques for fast/efficient model serving — KV-cache, Flash Attention, speculative decoding, quantization, PagedAttention, vLLM |
| [[interpretability]] | Understanding what models learn internally — feature visualization, attribution methods, mechanistic interpretability, sparse autoencoders |
| [[object-detection]] | Locating and classifying objects in images — R-CNN family, YOLO (v1–v10), DETR, anchor-based vs. anchor-free, FPN multi-scale features |
| [[speech-and-audio]] | Neural audio processing — ASR (Whisper, wav2vec), TTS (VALL-E, Voicebox), neural codecs (SoundStream, EnCodec), music generation (MusicLM, MusicGen) |
| [[video-understanding-and-generation]] | Video deep learning — 3D CNNs (C3D, I3D, SlowFast), Video Transformers (TimeSformer, ViViT, VideoMAE), video generation (Sora, Veo, Kling), video-language models |
| [[3d-vision-and-neural-rendering]] | 3D scene reconstruction and rendering — PointNet for point clouds, NeRF for neural radiance fields, 3D Gaussian Splatting for real-time rendering, diffusion-based 3D generation |
| [[semantic-segmentation]] | Classifying every pixel — FCN, U-Net, DeepLab (dilated convolutions, ASPP), Mask R-CNN for instances, Segment Anything (SAM) as a foundation model |
| [[model-deployment]] | From training to production — ONNX, TensorRT, serving infrastructure (Triton, vLLM), edge/mobile deployment, MLOps lifecycle, cost optimization |
| [[ai-safety-and-alignment]] | Ensuring AI behaves as intended — RLHF failure modes, reward hacking, DPO, constitutional AI, red teaming, scalable oversight, and the alignment-capability trade-off |
| [[embeddings-and-representation-learning]] | Dense vector representations capturing semantic relationships — word2vec, sentence transformers, CLIP, contrastive learning, vector databases, and RAG retrieval |
| [[text-to-image-generation]] | Generating images from text — Stable Diffusion pipeline (VAE + U-Net/DiT + text encoder), classifier-free guidance, ControlNet, IP-Adapter, DreamBooth, and the open-source ecosystem |
| [[quantization]] | Reducing numerical precision for efficient inference — INT8/INT4 weight quantization, GPTQ, AWQ, GGUF formats, QLoRA, SmoothQuant, and the quality-compression trade-off |
| [[prompt-engineering-and-in-context-learning]] | Eliciting LLM behavior through crafted inputs — chain-of-thought, few-shot/many-shot, system prompts, structured outputs, and the theory of in-context learning as implicit meta-learning |
| [[image-classification-milestones]] | The architecture timeline from LeNet to ViT — AlexNet (GPU + ReLU), VGG (3×3 depth), GoogLeNet (multi-scale), ResNet (skip connections), EfficientNet (NAS), ViT (attention replaces convolution) |
| [[transfer-learning]] | Reusing pre-trained model knowledge for new tasks — feature extraction vs. fine-tuning, domain adaptation, LoRA/adapters/prompt tuning, the foundation model paradigm |
| [[adversarial-robustness]] | Crafted perturbations that fool neural networks — FGSM, PGD, adversarial training, certified defenses, the robustness-accuracy trade-off, and the "features not bugs" perspective |
| [[neural-odes-and-continuous-models]] | Neural networks as continuous dynamical systems — Neural ODEs, continuous normalizing flows, flow matching, connections to diffusion models and state space models |
| [[efficient-attention-variants]] | Reducing Transformer attention's quadratic cost — Flash Attention, multi-query/grouped-query attention, sparse/sliding window patterns, linear attention, KV-cache compression |
| [[world-models-and-predictive-learning]] | Learning internal models of environment dynamics — Ha & Schmidhuber's World Models, Dreamer, MuZero, JEPA, video prediction as world modeling, the predictive learning hypothesis |
| [[reasoning-in-llms]] | Multi-step reasoning in language models — chain-of-thought, self-consistency, process reward models, reasoning models (o1, R1), test-time compute scaling, and faithfulness of reasoning traces |
| [[model-merging-and-editing]] | Combining model weights without retraining (task arithmetic, TIES, model soups, SLERP) and surgically editing factual knowledge (ROME, MEMIT) — post-training model composition |
| [[test-time-adaptation]] | Adapting models during inference to handle distribution shifts — BN adaptation, TENT, test-time training (TTT), TTT layers as attention alternatives, prompt-based adaptation |
| [[synthetic-data-generation]] | Using models to generate training data — Alpaca, Orca, Phi's textbook-quality pre-training, self-play for reasoning, model collapse from recursive generation |
| [[neural-network-compression]] | Reducing model size via pruning (magnitude, structured, lottery tickets), SparseGPT/Wanda for LLMs, 2:4 hardware sparsity, combined compression strategies |
| [[reward-modeling-and-rlhf]] | Training reward models from preferences and optimizing against them — PPO, GRPO, DPO, KTO, reward hacking scaling laws, the alignment tax |
| [[retrieval-augmented-generation]] | Grounding LLM generation in retrieved documents — chunking, hybrid retrieval, reranking, Self-RAG, CRAG, Graph RAG, production pipeline design |
| [[long-context-and-memory-architectures]] | Extending Transformer context beyond training limits — position interpolation, Infini-attention, RETRO, ring attention, KV-cache management, memory tokens |
| [[mechanistic-interpretability]] | Reverse-engineering neural network circuits — superposition, sparse autoencoders, activation patching, induction heads, and scaling to frontier models |
| [[language-model-pretraining]] | Pre-training objectives (MLM, CLM, span corruption), encoder/decoder/encoder-decoder architectures (BERT, GPT, T5), and why decoder-only won |
| [[optimization-theory-for-deep-learning]] | Why SGD works in non-convex landscapes — implicit bias, edge of stability, NTK vs. feature learning, grokking, and the theory-practice gap |
| [[autonomous-driving-perception]] | 3D object detection (PointPillars, CenterPoint, BEVFormer), sensor fusion, BEV representations, occupancy networks, end-to-end driving |
| [[protein-and-molecular-deep-learning]] | AlphaFold for protein structure, protein language models (ESM), geometric/equivariant networks for molecules, drug discovery, RFdiffusion |
| [[medical-imaging]] | Radiology AI (chest X-ray, CT, mammography), pathology, U-Net/nnU-Net, FDA-approved models, privacy/federated learning, clinical deployment patterns |
| [[nlp-tasks]] | Core NLP tasks (NER, translation, summarization, QA, sentiment) and the paradigm shift from task-specific models to unified LLMs |
| [[energy-based-models-and-contrastive-learning]] | EBMs, noise contrastive estimation, InfoNCE loss, contrastive learning theory, collapse prevention, spectral graph theory of representations |
| [[neural-network-initialization]] | Xavier/He initialization, signal propagation, fixup for deep ResNets, $\mu$P for hyperparameter transfer, Transformer initialization schemes |
| [[robotics-and-embodied-ai]] | Robot manipulation (RT-2, Octo), locomotion, sim-to-real transfer, imitation learning, diffusion policies, LLM-based planning for robots |
| [[time-series-forecasting]] | Temporal prediction from RNN/LSTM through PatchTST, foundation models (TimesFM, Chronos), the DLinear controversy, and anomaly detection |
| [[recommender-systems]] | Collaborative filtering, neural CF, two-tower retrieval, sequential recommendation (SASRec), feature-rich ranking (DLRM), and LLMs for recommendation |
| [[audio-generation]] | Neural audio synthesis — WaveNet, HiFi-GAN vocoders, codec language models (VALL-E, MusicGen), audio diffusion, zero-shot voice cloning |
| [[fairness-and-bias]] | Sources of bias (data, annotation, model, deployment), fairness definitions and their impossibility theorem, debiasing techniques, algorithmic auditing |
| [[hardware-software-co-design]] | GPU memory hierarchy exploitation, kernel fusion, Triton/TVM/torch.compile, tensor core alignment, structured sparsity, the co-design feedback loop |
| [[3d-generation-deep-dive]] | NeRF variants (Instant-NGP, Zip-NeRF), 3D Gaussian Splatting, text-to-3D via Score Distillation (DreamFusion, ProlificDreamer), feed-forward 3D, 4D generation |
| [[instruction-tuning-and-multi-task-learning]] | Multi-task training with natural language instructions (T0, FLAN, FLAN-T5), cross-task generalization, Self-Instruct, task interference, the SFT stage of modern LLM training |
| [[causal-inference-and-deep-learning]] | Structural causal models, treatment effect estimation (TARNet, Double ML), causal discovery (NOTEARS), causal representation learning, IRM, causality for robustness |
| [[evaluation-and-benchmarking]] | Benchmark design and contamination, Goodhart's law, human evaluation (Chatbot Arena), LLM-as-judge, metric reliability, the evaluation-utility gap |
| [[privacy-preserving-ml]] | Differential privacy (DP-SGD), membership inference attacks, training data extraction, secure computation (MPC, HE), machine unlearning, privacy-fairness trade-offs |
| [[knowledge-graphs-and-structured-knowledge]] | KG embeddings (TransE, RotatE, ComplEx), GNN-based KG reasoning, KG-enhanced LLMs, neuro-symbolic reasoning, Graph RAG, parametric vs. explicit knowledge |
| [[speech-recognition-deep-dive]] | CTC alignment, RNN-Transducer for streaming, Whisper's supervised scaling, self-supervised speech (wav2vec 2.0, HuBERT), Conformer, multilingual ASR (MMS) |
| [[few-shot-and-zero-shot-learning]] | Prototypical networks, MAML, CLIP zero-shot transfer, in-context learning as few-shot, foundation models vs. dedicated few-shot methods |
| [[point-cloud-and-lidar-deep-learning]] | PointNet permutation invariance, PointNet++ hierarchical features, sparse 3D convolutions (MinkowskiNet), Point Transformer, LiDAR 3D detection and segmentation |

## Tools & Frameworks

| Entry | Summary |
|-------|---------|
| [[pytorch]] | The dominant deep learning framework — imperative, Python-first, dynamic computational graphs, autograd |
| [[tensorflow]] | Google's framework — static-graph origins, Keras API, strong deployment story (TF Lite, TF.js), JAX as successor for research |
| [[numpy]] | Foundational numerical computing library — the ndarray and array programming paradigm that all DL frameworks mirror |
| [[cuda]] | NVIDIA's parallel computing platform — cuBLAS, cuDNN, NCCL, TensorRT; the software moat behind GPU dominance |
| [[hugging-face]] | Central hub for pre-trained models and datasets — Transformers library, Hub, PEFT, TRL, the "GitHub of ML" |

## Reference

| Entry | Summary |
|-------|---------|
| [[reference/notation\|notation]] | Mathematical symbols and conventions used throughout the knowledge base — variables, derivatives, probability notation, and common conventions like $\hat{y}$ = predicted |
| [[reference/glossary\|glossary]] | Quick definitions for jargon that appears across articles but doesn't warrant its own concept — logits, epoch, backbone, ablation study, SOTA, etc. |
| [[reference/timeline\|timeline]] | Chronological milestones from McCulloch-Pitts (1943) to frontier models (2025) — 42 entries across six eras |
| [[reference/key-people\|key people]] | Major researchers and their contributions, organized by area — from Rosenblatt and Hinton to Vaswani and Gu |

---

*95 concept articles, 5 tool entries, 4 references | Seeded 2026-04-12 | Primary source: Fleuret, "The Little Book of Deep Learning" (2023)*
