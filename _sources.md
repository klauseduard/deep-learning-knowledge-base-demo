# Deep Learning — Sources

References consulted during the creation of this knowledge base, organized by type.

## Primary Source

- **Fleuret, François (2023). *The Little Book of Deep Learning*.** Self-published, freely available at https://fleuret.org/francois/lbdl.html. A concise yet technically rigorous survey of the field in ~160 pages. Used as the structural backbone for this knowledge base — the concept selection and many technical details draw from this book.

## Landmark Papers

### Foundations
- Rosenblatt, F. (1958). "The Perceptron: A Probabilistic Model for Information Storage and Organization in the Brain." *Psychological Review*.
- Rumelhart, D., Hinton, G. & Williams, R. (1986). "Learning representations by back-propagating errors." *Nature*, 323, 533–536.
- Cybenko, G. (1989). "Approximation by Superpositions of a Sigmoidal Function." *Mathematics of Control, Signals and Systems*.
- Hornik, K., Stinchcombe, M. & White, H. (1989). "Multilayer Feedforward Networks are Universal Approximators." *Neural Networks*.

### Optimization
- Robbins, H. & Monro, S. (1951). "A Stochastic Approximation Method." *Annals of Mathematical Statistics*.
- Glorot, X. & Bengio, Y. (2010). "Understanding the difficulty of training deep feedforward neural networks." *AISTATS*.
- Kingma, D. & Ba, J. (2015). "Adam: A Method for Stochastic Optimization." *ICLR*.

### Activation Functions
- Glorot, X., Bordes, A. & Bengio, Y. (2011). "Deep Sparse Rectifier Neural Networks." *AISTATS*.
- Maas, A., Hannun, A. & Ng, A. (2013). "Rectifier Nonlinearities Improve Neural Network Acoustic Models." *ICML Workshop*.
- Hendrycks, D. & Gimpel, K. (2016). "Gaussian Error Linear Units (GELUs)." arXiv:1606.08415.

### Regularization
- Srivastava, N. et al. (2014). "Dropout: A Simple Way to Prevent Neural Networks from Overfitting." *JMLR*.
- Ioffe, S. & Szegedy, C. (2015). "Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift." *ICML*.
- Ba, J.L., Kiros, J. & Hinton, G. (2016). "Layer Normalization." arXiv:1607.06450.

### Convolutional Networks
- LeCun, Y. et al. (1998). "Gradient-Based Learning Applied to Document Recognition." *Proc. IEEE*.
- Krizhevsky, A., Sutskever, I. & Hinton, G. (2012). "ImageNet Classification with Deep Convolutional Neural Networks." *NeurIPS*.
- Simonyan, K. & Zisserman, A. (2014). "Very Deep Convolutional Networks for Large-Scale Image Recognition." *ICLR 2015*.
- He, K. et al. (2015). "Deep Residual Learning for Image Recognition." *CVPR 2016*.

### Attention and Transformers
- Bahdanau, D., Cho, K. & Bengio, Y. (2014). "Neural Machine Translation by Jointly Learning to Align and Translate." *ICLR 2015*.
- Vaswani, A. et al. (2017). "Attention Is All You Need." *NeurIPS*.
- Radford, A. et al. (2018). "Improving Language Understanding by Generative Pre-Training." OpenAI.
- Dosovitskiy, A. et al. (2020). "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale." *ICLR 2021*.

### Language Models
- Radford, A. et al. (2019). "Language Models are Unsupervised Multitask Learners." OpenAI.
- Brown, T. et al. (2020). "Language Models are Few-Shot Learners." *NeurIPS*. (GPT-3)
- Touvron, H. et al. (2023). "LLaMA: Open and Efficient Foundation Language Models." arXiv.

### Scaling Laws
- Kaplan, J. et al. (2020). "Scaling Laws for Neural Language Models." arXiv.
- Hoffmann, J. et al. (2022). "Training Compute-Optimal Large Language Models." *NeurIPS*. (Chinchilla)

### Alignment and Fine-tuning
- Ouyang, L. et al. (2022). "Training language models to follow instructions with human feedback." *NeurIPS*. (InstructGPT / RLHF)
- Hu, E. et al. (2021). "LoRA: Low-Rank Adaptation of Large Language Models." *ICLR 2022*.
- Dettmers, T. et al. (2023). "QLoRA: Efficient Finetuning of Quantized Language Models." *NeurIPS*.

### Diffusion Models
- Ho, J., Jain, A. & Abbeel, P. (2020). "Denoising Diffusion Probabilistic Models." *NeurIPS*.
- Nichol, A. et al. (2021). "GLIDE: Towards Photorealistic Image Generation and Editing with Text-Guided Diffusion Models." *ICML*.
- Rombach, R. et al. (2022). "High-Resolution Image Synthesis with Latent Diffusion Models." *CVPR*. (Stable Diffusion)

### Multimodal
- Radford, A. et al. (2021). "Learning Transferable Visual Models From Natural Language Supervision." *ICML*. (CLIP)
- Radford, A. et al. (2022). "Robust Speech Recognition via Large-Scale Weak Supervision." arXiv. (Whisper)

### Skip Connections
- Ronneberger, O., Fischer, P. & Brox, T. (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation." *MICCAI*.
- Srivastava, R., Greff, K. & Schmidhuber, J. (2015). "Highway Networks." *ICML Deep Learning Workshop*.

### Recurrent Networks
- Elman, J. (1990). "Finding Structure in Time." *Cognitive Science*.
- Hochreiter, S. & Schmidhuber, J. (1997). "Long Short-Term Memory." *Neural Computation*.
- Cho, K. et al. (2014). "Learning Phrase Representations using RNN Encoder-Decoder." *EMNLP*.
- Sutskever, I., Vinyals, O. & Le, Q. (2014). "Sequence to Sequence Learning with Neural Networks." *NeurIPS*.

### State Space Models
- Gu, A. et al. (2020). "HiPPO: Recurrent Memory with Optimal Polynomial Projections." *NeurIPS*.
- Gu, A., Goel, K. & Re, C. (2021). "Efficiently Modeling Long Sequences with Structured State Spaces." *ICLR 2022*. (S4)
- Gu, A. & Dao, T. (2023). "Mamba: Linear-Time Sequence Modeling with Selective State Spaces." arXiv:2312.00752.
- Dao, T. & Gu, A. (2024). "Transformers are SSMs: Generalized Models and Efficient Algorithms through Structured State Space Duality." *ICML 2024*. (Mamba-2)
- Lieber, O. et al. (2024). "Jamba: A Hybrid Transformer-Mamba Language Model." arXiv:2403.19887.

### Reinforcement Learning
- Sutton, R. & Barto, A. (2018). *Reinforcement Learning: An Introduction*. 2nd ed. MIT Press.
- Mnih, V. et al. (2015). "Human-level control through deep reinforcement learning." *Nature*.
- Silver, D. et al. (2016). "Mastering the game of Go with deep neural networks and tree search." *Nature*.
- Schulman, J. et al. (2017). "Proximal Policy Optimization Algorithms." arXiv:1707.06347.
- Rafailov, R. et al. (2023). "Direct Preference Optimization." *NeurIPS*.

### Inference Optimization
- Dao, T. et al. (2022). "FlashAttention: Fast and Memory-Efficient Exact Attention." *NeurIPS*.
- Kwon, W. et al. (2023). "Efficient Memory Management for LLM Serving with PagedAttention." *SOSP*.
- Leviathan, Y. et al. (2022). "Fast Inference from Transformers via Speculative Decoding." *ICML 2023*.
- Ainslie, J. et al. (2023). "GQA: Training Generalized Multi-Query Transformer Models." *EMNLP*.
- Frantar, E. et al. (2022). "GPTQ: Accurate Post-Training Quantization." *ICLR 2023*.
- Lin, J. et al. (2023). "AWQ: Activation-Aware Weight Quantization." *MLSys 2024*.

### Interpretability
- Olah, C. et al. (2020). "Zoom In: An Introduction to Circuits." *Distill*.
- Meng, K. et al. (2022). "Locating and Editing Factual Associations in GPT." *NeurIPS*.
- Bricken, T. et al. (2023). "Towards Monosemanticity: Decomposing Language Models With Dictionary Learning." Anthropic.
- Elhage, N. et al. (2022). "Toy Models of Superposition." Anthropic.
- Sundararajan, M. et al. (2017). "Axiomatic Attribution for Deep Networks." *ICML*.
- Lundberg, S. & Lee, S. (2017). "A Unified Approach to Interpreting Model Predictions." *NeurIPS*. (SHAP)

### Distributed Training
- Rajbhandari, S. et al. (2020). "ZeRO: Memory Optimizations Toward Training Trillion Parameter Models." *SC*.
- Shoeybi, M. et al. (2019). "Megatron-LM: Training Multi-Billion Parameter Language Models." arXiv:1909.08053.
- Huang, Y. et al. (2019). "GPipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism." *NeurIPS*.
- Narayanan, D. et al. (2021). "Efficient Large-Scale Language Model Training on GPU Clusters." *SC*.

### Generative Adversarial Networks
- Goodfellow, I. et al. (2014). "Generative Adversarial Nets." *NeurIPS*.
- Radford, A., Metz, L. & Chintala, S. (2015). "Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks." *ICLR 2016*. (DCGAN)
- Arjovsky, M., Chintala, S. & Bottou, L. (2017). "Wasserstein GAN." *ICML*.
- Karras, T., Laine, S. & Aila, T. (2019). "A Style-Based Generator Architecture for Generative Adversarial Networks." *CVPR*. (StyleGAN)
- Zhu, J.-Y. et al. (2017). "Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks." *ICCV*. (CycleGAN)

### Autoencoders and VAEs
- Hinton, G. & Salakhutdinov, R. (2006). "Reducing the Dimensionality of Data with Neural Networks." *Science*.
- Kingma, D. & Welling, M. (2013). "Auto-Encoding Variational Bayes." *ICLR 2014*.
- Rezende, D., Mohamed, S. & Wierstra, D. (2014). "Stochastic Backpropagation and Approximate Inference in Deep Generative Models." *ICML*.
- van den Oord, A., Vinyals, O. & Kavukcuoglu, K. (2017). "Neural Discrete Representation Learning." *NeurIPS*. (VQ-VAE)

### Mixture of Experts
- Jacobs, R., Jordan, M., Nowlan, S. & Hinton, G. (1991). "Adaptive Mixtures of Local Experts." *Neural Computation*.
- Shazeer, N. et al. (2017). "Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer." *ICLR*.
- Fedus, W., Zoph, B. & Shazeer, N. (2022). "Switch Transformers: Scaling to Trillion Parameter Models." *JMLR*.
- Jiang, A. et al. (2024). "Mixtral of Experts." arXiv:2401.04088.
- Lepikhin, D. et al. (2021). "GShard: Scaling Giant Models with Conditional Computation." *ICLR*.

### Self-Supervised Learning
- Mikolov, T. et al. (2013). "Efficient Estimation of Word Representations in Vector Space." *ICLR Workshop*. (word2vec)
- Devlin, J. et al. (2018). "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding." *NAACL 2019*.
- Chen, T. et al. (2020). "A Simple Framework for Contrastive Learning of Visual Representations." *ICML*. (SimCLR)
- He, K. et al. (2020). "Momentum Contrast for Unsupervised Visual Representation Learning." *CVPR*. (MoCo)
- Grill, J.-B. et al. (2020). "Bootstrap Your Own Latent." *NeurIPS*. (BYOL)
- He, K. et al. (2022). "Masked Autoencoders Are Scalable Self-Supervised Learners." *CVPR*. (MAE)
- Caron, M. et al. (2021). "Emerging Properties in Self-Supervised Vision Transformers." *ICCV*. (DINO)

### Graph Neural Networks
- Scarselli, F. et al. (2009). "The Graph Neural Network Model." *IEEE Transactions on Neural Networks*.
- Kipf, T. & Welling, M. (2017). "Semi-Supervised Classification with Graph Convolutional Networks." *ICLR*. (GCN)
- Gilmer, J. et al. (2017). "Neural Message Passing for Quantum Chemistry." *ICML*. (MPNN)
- Velickovic, P. et al. (2018). "Graph Attention Networks." *ICLR*. (GAT)
- Hamilton, W., Ying, Z. & Leskovec, J. (2017). "Inductive Representation Learning on Large Graphs." *NeurIPS*. (GraphSAGE)
- Xu, K. et al. (2019). "How Powerful are Graph Neural Networks?" *ICLR*. (GIN)
- Ying, C. et al. (2021). "Do Transformers Really Perform Bad for Graph Representation?" *NeurIPS*. (Graphormer)

### Knowledge Distillation
- Bucilua, C., Caruana, R. & Niculescu-Mizil, A. (2006). "Model Compression." *KDD*.
- Hinton, G., Vinyals, O. & Dean, J. (2015). "Distilling the Knowledge in a Neural Network." *NeurIPS Workshop*.
- Romero, A. et al. (2015). "FitNets: Hints for Thin Deep Nets." *ICLR*.
- Sanh, V. et al. (2019). "DistilBERT, a distilled version of BERT." *NeurIPS Workshop*.
- Salimans, T. & Ho, J. (2022). "Progressive Distillation for Fast Sampling of Diffusion Models." *ICLR*.
- Song, Y. et al. (2023). "Consistency Models." *ICML*.

### Generalization Theory
- Zhang, C. et al. (2017). "Understanding Deep Learning Requires Rethinking Generalization." *ICLR*.
- Belkin, M. et al. (2019). "Reconciling modern machine-learning practice and the classical bias-variance trade-off." *PNAS*. (Double descent)
- Power, A. et al. (2022). "Grokking: Generalization Beyond Overfitting on Small Algorithmic Datasets." *ICML Workshop*.
- Frankle, J. & Carlin, M. (2019). "The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks." *ICLR*.
- Jacot, A., Gabriel, F. & Hongler, C. (2018). "Neural Tangent Kernel: Convergence and Generalization in Neural Networks." *NeurIPS*.
- Nakkiran, P. et al. (2021). "Deep Double Descent: Where Bigger Models and More Data Can Hurt." *JMLR*.

### Multimodal Models
- Liu, H. et al. (2023). "Visual Instruction Tuning." *NeurIPS*. (LLaVA)
- Zhai, X. et al. (2023). "Sigmoid Loss for Language Image Pre-Training." *ICCV*. (SigLIP)
- Alayrac, J.-B. et al. (2022). "Flamingo: a Visual Language Model for Few-Shot Learning." *NeurIPS*.
- Saharia, C. et al. (2022). "Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding." *NeurIPS*. (Imagen)
- Girdhar, R. et al. (2023). "ImageBind: One Embedding Space To Bind Them All." *CVPR*.
- Gemini Team, Google (2023). "Gemini: A Family of Highly Capable Multimodal Models." arXiv:2312.11805.
- Chameleon Team, Meta (2024). "Chameleon: Mixed-Modal Early-Fusion Foundation Models." arXiv:2405.09818.
- Wu, S. et al. (2023). "NExT-GPT: Any-to-Any Multimodal LLM." *ICML 2024*.

### Agents and Tool Use
- Yao, S. et al. (2022). "ReAct: Synergizing Reasoning and Acting in Language Models." *ICLR 2023*. arXiv:2210.03629.
- Schick, T. et al. (2023). "Toolformer: Language Models Can Teach Themselves to Use Tools." *NeurIPS 2023*. arXiv:2302.04761.
- Nakano, R. et al. (2022). "WebGPT: Browser-assisted question-answering with human feedback." arXiv:2112.09332.
- Yao, S. et al. (2023). "Tree of Thoughts: Deliberate Problem Solving with Large Language Models." *NeurIPS 2023*. arXiv:2305.10601.
- Besta, M. et al. (2023). "Graph of Thoughts: Solving Elaborate Problems with Large Language Models." arXiv:2308.09687.
- Shinn, N. et al. (2023). "Reflexion: Language Agents with Verbal Reinforcement Learning." *NeurIPS 2023*. arXiv:2303.11366.
- Wang, L. et al. (2023). "A Survey on Large Language Model based Autonomous Agents." arXiv:2308.11432.
- Xi, Z. et al. (2023). "The Rise and Potential of Large Language Model Based Agents: A Survey." arXiv:2309.07864.
- Park, J.S. et al. (2023). "Generative Agents: Interactive Simulacra of Human Behavior." *UIST 2023*. arXiv:2304.03442.
- Li, G. et al. (2023). "CAMEL: Communicative Agents for 'Mind' Exploration of Large Language Model Society." *NeurIPS 2023*. arXiv:2303.17760.
- Jimenez, C.E. et al. (2024). "SWE-bench: Can Language Models Resolve Real-World GitHub Issues?" *ICLR 2024*. arXiv:2310.06770.
- Zhou, S. et al. (2024). "WebArena: A Realistic Web Environment for Building Autonomous Agents." *ICLR 2024*. arXiv:2307.13854.
- Packer, C. et al. (2023). "MemGPT: Towards LLMs as Operating Systems." arXiv:2310.08560.
- Shen, Y. et al. (2023). "HuggingGPT: Solving AI Tasks with ChatGPT and its Friends in Hugging Face." *NeurIPS 2023*. arXiv:2303.17580.
- Qian, C. et al. (2023). "ChatDev: Communicative Agents for Software Development." arXiv:2307.07924.
- Hong, S. et al. (2023). "MetaGPT: Meta Programming for Multi-Agent Collaborative Framework." arXiv:2308.00352.
- DeepSeek-AI (2025). "DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning." arXiv:2501.12948.

### GPU and Accelerator Hardware
- Jouppi, N. et al. (2017). "In-Datacenter Performance Analysis of a Tensor Processing Unit." *ISCA*. (TPU v1)
- Jouppi, N. et al. (2023). "TPU v4: An Optically Reconfigurable Supercomputer for Machine Learning with Hardware Support for Embeddings." *ISCA*.
- Micikevicius, P. et al. (2018). "Mixed Precision Training." *ICLR*.
- Williams, S., Waterman, A. & Patterson, D. (2009). "Roofline: An Insightful Visual Performance Model for Multicore Architectures." *Communications of the ACM*.
- NVIDIA (2022). "NVIDIA H100 Tensor Core GPU Architecture." Whitepaper.
- NVIDIA (2024). "NVIDIA Blackwell Architecture." Technical Brief.
- AMD (2023). "AMD Instinct MI300X Accelerator." Datasheet.

### Object Detection
- Girshick, R. et al. (2014). "Rich feature hierarchies for accurate object detection and semantic segmentation." *CVPR*. (R-CNN)
- Girshick, R. (2015). "Fast R-CNN." *ICCV*.
- Ren, S. et al. (2015). "Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks." *NeurIPS*.
- Lin, T.-Y. et al. (2017). "Feature Pyramid Networks for Object Detection." *CVPR*. (FPN)
- Redmon, J. et al. (2016). "You Only Look Once: Unified, Real-Time Object Detection." *CVPR*. (YOLO)
- Carion, N. et al. (2020). "End-to-End Object Detection with Transformers." *ECCV*. (DETR)
- Zhu, X. et al. (2021). "Deformable DETR: Deformable Transformers for End-to-End Object Detection." *ICLR*.

### Speech and Audio
- van den Oord, A. et al. (2016). "WaveNet: A Generative Model for Raw Audio." arXiv:1609.03499.
- Baevski, A. et al. (2020). "wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations." *NeurIPS*.
- Radford, A. et al. (2022). "Robust Speech Recognition via Large-Scale Weak Supervision." arXiv. (Whisper)
- Wang, C. et al. (2023). "Neural Codec Language Models are Zero-Shot Text to Speech Synthesizers." arXiv. (VALL-E)
- Le Roux, J. et al. (2023). "Voicebox: Text-Guided Multilingual Universal Speech Generation at Scale." *NeurIPS*.
- Zeghidour, N. et al. (2021). "SoundStream: An End-to-End Neural Audio Codec." *IEEE/ACM TASLP*.
- Défossez, A. et al. (2022). "High Fidelity Neural Audio Compression." arXiv. (EnCodec)
- Agostinelli, A. et al. (2023). "MusicLM: Generating Music From Text." arXiv.
- Copet, J. et al. (2023). "Simple and Controllable Music Generation." *NeurIPS*. (MusicGen)

### Video Understanding and Generation
- Tran, D. et al. (2015). "Learning Spatiotemporal Features with 3D Convolutional Networks." *ICCV*. (C3D)
- Carreira, J. & Zisserman, A. (2017). "Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset." *CVPR*. (I3D)
- Feichtenhofer, C. et al. (2019). "SlowFast Networks for Video Recognition." *ICCV*.
- Tran, D. et al. (2018). "A Closer Look at Spatiotemporal Convolutions for Action Recognition." *CVPR*. (R(2+1)D)
- Simonyan, K. & Zisserman, A. (2014). "Two-Stream Convolutional Networks for Action Recognition in Videos." *NeurIPS*.
- Bertasius, G., Wang, H. & Torresani, L. (2021). "Is Space-Time Attention All You Need for Video Understanding?" *ICML*. (TimeSformer)
- Arnab, A. et al. (2021). "ViViT: A Video Vision Transformer." *ICCV*.
- Tong, Z. et al. (2022). "VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training." *NeurIPS*.
- OpenAI (2024). "Video generation models as world simulators." Technical report. (Sora)
- Singer, U. et al. (2022). "Make-A-Video: Text-to-Video Generation without Text-Video Data." *ICLR 2023*. (Meta)
- Ho, J. et al. (2022). "Video Diffusion Models." *NeurIPS Workshop*.
- Ho, J. et al. (2022b). "Imagen Video: High Definition Video Generation with Diffusion Models." arXiv:2210.02303.
- Blattmann, A. et al. (2023). "Stable Video Diffusion: Scaling Latent Video Diffusion Models to Large Datasets." arXiv:2311.15127.
- Meta (2024). "Movie Gen: A Cast of Media Foundation Models." arXiv:2410.13720.
- Kong, W. et al. (2024). "HunyuanVideo: A Systematic Framework For Large Video Generative Models." arXiv:2412.03603.
- Wan Team, Alibaba (2025). "Wan: Open and Advanced Large-Scale Video Generative Models." arXiv:2503.20314.
- Kay, W. et al. (2017). "The Kinetics Human Action Video Dataset." arXiv:1705.06950.
- Goyal, R. et al. (2017). "The 'Something Something' Video Database." *ICCV*.
- Unterthiner, T. et al. (2019). "FVD: A new Metric for Video Generation." *ICLR Workshop*.
- Huang, Z. et al. (2024). "VBench: Comprehensive Benchmark Suite for Video Generative Models." *CVPR*.

### 3D Vision and Neural Rendering
- Qi, C.R., Su, H., Mo, K. & Guibas, L. (2017). "PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation." *CVPR*. arXiv:1612.00593.
- Qi, C.R., Yi, L., Su, H. & Guibas, L. (2017b). "PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space." *NeurIPS*. arXiv:1706.02413.
- Wang, Y. et al. (2019). "Dynamic Graph CNN for Learning on Point Clouds." *ACM TOG*. (DGCNN)
- Zhao, H. et al. (2021). "Point Transformer." *ICCV*.
- Mildenhall, B. et al. (2020). "NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis." *ECCV / CACM 2022*. arXiv:2003.08934.
- Tancik, M. et al. (2020). "Fourier Features Let Networks Learn High Frequency Functions in Low Dimensional Domains." *NeurIPS*.
- Mueller, T. et al. (2022). "Instant Neural Graphics Primitives with a Multiresolution Hash Encoding." *ACM TOG (SIGGRAPH)*. arXiv:2201.05989. (Instant-NGP)
- Barron, J.T. et al. (2021). "Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields." *ICCV*. arXiv:2103.13415.
- Barron, J.T. et al. (2022). "Mip-NeRF 360: Unbounded Anti-Aliased Neural Radiance Fields." *CVPR*. arXiv:2111.12077.
- Barron, J.T. et al. (2023). "Zip-NeRF: Anti-Aliased Grid-Based Neural Radiance Fields." *ICCV*. arXiv:2304.06706.
- Martin-Brualla, R. et al. (2021). "NeRF in the Wild: Neural Radiance Fields for Unconstrained Photo Collections." *CVPR*. arXiv:2008.02268.
- Tancik, M. et al. (2022). "Block-NeRF: Scalable Large Scene Neural View Synthesis." *CVPR*. arXiv:2202.05263.
- Chen, A. et al. (2022). "TensoRF: Tensorial Radiance Fields." *ECCV*. arXiv:2203.09517.
- Fridovich-Keil, S. et al. (2022). "Plenoxels: Radiance Fields without Neural Networks." *CVPR*. arXiv:2112.05131.
- Kerbl, B. et al. (2023). "3D Gaussian Splatting for Real-Time Radiance Field Rendering." *ACM TOG (SIGGRAPH)*. arXiv:2308.14737.
- Yu, Z. et al. (2024). "Mip-Splatting: Alias-free 3D Gaussian Splatting." *CVPR*. arXiv:2311.16493.
- Luiten, J. et al. (2024). "Dynamic 3D Gaussians: Tracking by Persistent Dynamic View Synthesis." *3DV*. arXiv:2308.09713.
- Charatan, D. et al. (2024). "pixelSplat: 3D Gaussian Splats from Image Pairs for Scalable Generalizable 3D Reconstruction." *CVPR*. arXiv:2312.12337.
- Kerbl, B. et al. (2024). "A Hierarchical 3D Gaussian Representation for Real-Time Rendering of Very Large Datasets." *ACM TOG (SIGGRAPH)*. arXiv:2406.12080.
- Tang, J. et al. (2024). "DreamGaussian: Generative Gaussian Splatting for Efficient 3D Content Creation." *ICLR*. arXiv:2309.16653.
- Poole, B. et al. (2022). "DreamFusion: Text-to-3D using 2D Diffusion." *ICLR 2023*. arXiv:2209.14988.
- Wang, Z. et al. (2023). "ProlificDreamer: High-Fidelity and Diverse Text-to-3D Generation with Variational Score Distillation." *NeurIPS*. arXiv:2305.16213.
- Lin, C.-H. et al. (2023). "Magic3D: High-Resolution Text-to-3D Content Creation." *CVPR*. arXiv:2211.10440.
- Liu, R. et al. (2023). "Zero-1-to-3: Zero-shot One Image to 3D Object." *ICCV*. arXiv:2303.11328.
- Hong, Y. et al. (2024). "LRM: Large Reconstruction Model for Single Image to 3D." *ICLR*. arXiv:2311.04400.
- Tochilkin, D. et al. (2024). "TripoSR: Fast 3D Object Reconstruction from a Single Image." arXiv:2403.02151.

### Federated Learning
- McMahan, B. et al. (2017). "Communication-Efficient Learning of Deep Networks from Decentralized Data." *AISTATS*. (FedAvg)
- Bonawitz, K. et al. (2019). "Towards Federated Learning at Scale: A System Design." *MLSys*.
- Li, T. et al. (2020). "Federated Optimization in Heterogeneous Networks." *MLSys*. (FedProx)
- Karimireddy, S.P. et al. (2020). "SCAFFOLD: Stochastic Controlled Averaging for Federated Learning." *ICML*.
- Zhu, L., Liu, Z. & Han, S. (2019). "Deep Leakage from Gradients." *NeurIPS*.

### Neural Architecture Search
- Zoph, B. & Le, Q. (2017). "Neural Architecture Search with Reinforcement Learning." *ICLR*.
- Liu, H., Simonyan, K. & Yang, Y. (2019). "DARTS: Differentiable Architecture Search." *ICLR*.
- Tan, M. & Le, Q. (2019). "EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks." *ICML*.
- Tan, M. et al. (2019). "MnasNet: Platform-Aware Neural Architecture Search for Mobile." *CVPR*.
- Real, E. et al. (2019). "Regularized Evolution for Image Classifier Architecture Search." *AAAI*. (AmoebaNet)
- Cai, H. et al. (2020). "Once-for-All: Train One Network and Specialize it for Efficient Deployment." *ICLR*.

### Semantic Segmentation
- Long, J., Shelhamer, E. & Darrell, T. (2015). "Fully Convolutional Networks for Semantic Segmentation." *CVPR*.
- Ronneberger, O., Fischer, P. & Brox, T. (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation." *MICCAI*.
- Chen, L.-C. et al. (2017). "Rethinking Atrous Convolution for Semantic Image Segmentation." arXiv. (DeepLab v3)
- Chen, L.-C. et al. (2018). "Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation." *ECCV*. (DeepLab v3+)
- He, K. et al. (2017). "Mask R-CNN." *ICCV*.
- Kirillov, A. et al. (2019). "Panoptic Segmentation." *CVPR*.
- Xie, E. et al. (2021). "SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers." *NeurIPS*.
- Cheng, B. et al. (2022). "Masked-attention Mask Transformer for Universal Image Segmentation." *CVPR*. (Mask2Former)
- Kirillov, A. et al. (2023). "Segment Anything." *ICCV*. (SAM)

### Meta-Learning
- Finn, C., Abbeel, P. & Levine, S. (2017). "Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks." *ICML*. (MAML)
- Vinyals, O. et al. (2016). "Matching Networks for One Shot Learning." *NeurIPS*.
- Snell, J., Swersky, K. & Zemel, R. (2017). "Prototypical Networks for Few-Shot Learning." *NeurIPS*.
- Nichol, A., Achiam, J. & Schulman, J. (2018). "On First-Order Meta-Learning Algorithms." arXiv. (Reptile)
- von Oswald, J. et al. (2023). "Transformers Learn In-Context by Gradient Descent." *ICML*.
- Hospedales, T. et al. (2022). "Meta-Learning in Neural Networks: A Survey." *IEEE TPAMI*.

### Model Deployment
- ONNX Consortium (2017). "ONNX: Open Neural Network Exchange." https://onnx.ai
- NVIDIA (2023). "TensorRT Developer Guide." https://developer.nvidia.com/tensorrt
- Kwon, W. et al. (2023). "Efficient Memory Management for LLM Serving with PagedAttention." *SOSP*. (vLLM)
- Howard, A. et al. (2017). "MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications." arXiv.
- Sculley, D. et al. (2015). "Hidden Technical Debt in Machine Learning Systems." *NeurIPS*.
- Paleyes, A., Urma, R.-G. & Lawrence, N. (2022). "Challenges in Deploying Machine Learning: A Survey of Case Studies." *ACM Computing Surveys*.

### Information Theory
- Shannon, C. (1948). "A Mathematical Theory of Communication." *Bell System Technical Journal*.
- Cover, T. & Thomas, J. (2006). *Elements of Information Theory*. 2nd ed. Wiley.
- Tishby, N., Pereira, F. & Bialek, W. (1999). "The Information Bottleneck Method." *Allerton Conference*.
- Shwartz-Ziv, R. & Tishby, N. (2017). "Opening the Black Box of Deep Neural Networks via Information." arXiv:1703.00810.
- Saxe, A. et al. (2019). "On the Information Bottleneck Theory of Deep Learning." *JMLR*.
- van den Oord, A. et al. (2018). "Representation Learning with Contrastive Predictive Coding." arXiv. (InfoNCE)
- Alemi, A. et al. (2017). "Deep Variational Information Bottleneck." *ICLR*.

### Loss Landscape Geometry
- Dauphin, Y. et al. (2014). "Identifying and Attacking the Saddle Point Problem in High-Dimensional Non-Convex Optimization." *NeurIPS*.
- Garipov, T. et al. (2018). "Loss Surfaces, Mode Connectivity, and Fast Ensembling of DNNs." *NeurIPS*.
- Li, H. et al. (2018). "Visualizing the Loss Landscape of Neural Nets." *NeurIPS*.
- Foret, P. et al. (2021). "Sharpness-Aware Minimization for Efficiently Improving Generalization." *ICLR*. (SAM)
- Cohen, J. et al. (2021). "Gradient Descent on Neural Networks Typically Occurs at the Edge of Stability." *ICLR*.
- Frankle, J. et al. (2020). "Linear Mode Connectivity and the Lottery Ticket Hypothesis." *ICML*.
- Ainsworth, S. et al. (2023). "Git Re-Basin: Merging Models Modulo Permutation Symmetries." *ICLR*.
- Hochreiter, S. & Schmidhuber, J. (1997). "Flat Minima." *Neural Computation*.

### Data Engineering
- Raffel, C. et al. (2020). "Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer." *JMLR*. (T5 / C4)
- Gao, L. et al. (2020). "The Pile: An 800GB Dataset of Diverse Text for Language Modeling." arXiv.
- Ratner, A. et al. (2017). "Snorkel: Rapid Training Data Creation with Weak Supervision." *VLDB*.
- Gunasekar, S. et al. (2023). "Textbooks Are All You Need." arXiv. (Phi-1)
- Zhou, C. et al. (2023). "LIMA: Less Is More for Alignment." *NeurIPS*.
- Shumailov, I. et al. (2024). "The Curse of Recursion: Training on Generated Data Makes Models Forget." *Nature*. (Model collapse)
- Lee, K. et al. (2022). "Deduplicating Training Data Makes Language Models Better." *ACL*.
- Xie, S. et al. (2023). "DoReMi: Optimizing Data Mixtures Speeds Up Language Model Pretraining." *NeurIPS*.
- Gebru, T. et al. (2021). "Datasheets for Datasets." *Communications of the ACM*.
- Cubuk, E. et al. (2020). "RandAugment: Practical Automated Data Augmentation with a Reduced Search Space." *NeurIPS*.

### Curriculum Learning
- Bengio, Y. et al. (2009). "Curriculum Learning." *ICML*.
- Kumar, M.P., Packer, B. & Koller, D. (2010). "Self-Paced Learning for Latent Variable Models." *NeurIPS*.
- Elman, J. (1993). "Learning and Development in Neural Networks: The Importance of Starting Small." *Cognition*.
- Platanios, E. et al. (2019). "Competence-Based Curriculum Learning for Neural Machine Translation." *NAACL*.
- Hacohen, G. & Weinshall, D. (2019). "On the Power of Curriculum Learning in Training Deep Networks." *ICML*.
- Soviany, P. et al. (2022). "Curriculum Learning: A Survey." *IJCV*.

### Continual Learning
- McCloskey, M. & Cohen, N. (1989). "Catastrophic Interference in Connectionist Networks." *Psychology of Learning and Motivation*.
- Kirkpatrick, J. et al. (2017). "Overcoming Catastrophic Forgetting in Neural Networks." *PNAS*. (EWC)
- Rusu, A. et al. (2016). "Progressive Neural Networks." arXiv:1606.04671.
- Zenke, F., Poole, B. & Ganguli, S. (2017). "Continual Learning Through Synaptic Intelligence." *ICML*. (SI)
- Li, Z. & Hoiem, D. (2017). "Learning Without Forgetting." *IEEE TPAMI*. (LwF)
- Buzzega, P. et al. (2020). "Dark Experience for General Continual Learning: a Strong, Simple Baseline." *NeurIPS*. (DER++)
- De Lange, M. et al. (2021). "A Continual Learning Survey: Defying Forgetting in Classification Tasks." *IEEE TPAMI*.

### AI Safety and Alignment
- Christiano, P. et al. (2017). "Deep Reinforcement Learning from Human Preferences." *NeurIPS*.
- Bai, Y. et al. (2022). "Constitutional AI: Harmlessness from AI Feedback." arXiv:2212.08073. (Anthropic)
- Rafailov, R. et al. (2023). "Direct Preference Optimization." *NeurIPS*. (DPO)
- Amodei, D. et al. (2016). "Concrete Problems in AI Safety." arXiv:1606.06565.
- Hubinger, E. et al. (2019). "Risks from Learned Optimization in Advanced ML Systems." arXiv:1906.01820.
- Gao, L. et al. (2022). "Scaling Laws for Reward Model Overoptimization." *ICML 2023*.
- Zou, A. et al. (2023). "Universal and Transferable Adversarial Attacks on Aligned Language Models." arXiv:2307.15043.
- Ganguli, D. et al. (2022). "Red Teaming Language Models to Reduce Harms." arXiv. (Anthropic)
- Burns, C. et al. (2023). "Weak-to-Strong Generalization." arXiv. (OpenAI)
- Lightman, H. et al. (2023). "Let's Verify Step by Step." arXiv:2305.20050. (Process reward models)
- Russell, S. (2019). *Human Compatible: AI and the Problem of Control*. Viking.

### Embeddings and Representation Learning
- Mikolov, T. et al. (2013). "Efficient Estimation of Word Representations in Vector Space." *ICLR Workshop*. (word2vec)
- Pennington, J., Socher, R. & Manning, C. (2014). "GloVe: Global Vectors for Word Representation." *EMNLP*.
- Bojanowski, P. et al. (2017). "Enriching Word Vectors with Subword Information." *TACL*. (FastText)
- Peters, M. et al. (2018). "Deep Contextualized Word Representations." *NAACL*. (ELMo)
- Reimers, N. & Gurevsky, I. (2019). "Sentence-BERT." *EMNLP*.
- Muennighoff, N. et al. (2023). "MTEB: Massive Text Embedding Benchmark." *EACL*.
- Wang, T. & Isola, P. (2020). "Understanding Contrastive Representation Learning through Alignment and Uniformity." *ICML*.
- Johnson, J., Douze, M. & Jégou, H. (2019). "Billion-Scale Similarity Search with GPUs." *IEEE TBD*. (FAISS)
- Kusupati, A. et al. (2022). "Matryoshka Representation Learning." *NeurIPS*.

### Normalization Techniques
- Ioffe, S. & Szegedy, C. (2015). "Batch Normalization." *ICML*.
- Ba, J.L., Kiros, J. & Hinton, G. (2016). "Layer Normalization." arXiv:1607.06450.
- Zhang, B. & Sennrich, R. (2019). "Root Mean Square Layer Normalization." *NeurIPS*. (RMSNorm)
- Wu, Y. & He, K. (2018). "Group Normalization." *ECCV*.
- Santurkar, S. et al. (2018). "How Does Batch Normalization Help Optimization?" *NeurIPS*.
- Wang, H. et al. (2022). "DeepNet: Scaling Transformers to 1,000 Layers." arXiv.

### Optimization Beyond SGD
- Kingma, D. & Ba, J. (2015). "Adam: A Method for Stochastic Optimization." *ICLR*.
- Loshchilov, I. & Hutter, F. (2019). "Decoupled Weight Decay Regularization." *ICLR*. (AdamW)
- Duchi, J., Hazan, E. & Singer, Y. (2011). "Adaptive Subgradient Methods." *JMLR*. (AdaGrad)
- Shazeer, N. & Stern, M. (2018). "Adafactor: Adaptive Learning Rates with Sublinear Memory Cost." *ICML*.
- You, Y. et al. (2017). "Large Batch Training of Convolutional Networks." arXiv. (LARS)
- You, Y. et al. (2020). "Large Batch Optimization for Deep Learning: Training BERT in 76 Minutes." *ICLR*. (LAMB)
- Loshchilov, I. & Hutter, F. (2017). "SGDR: Stochastic Gradient Descent with Warm Restarts." *ICLR*.
- Martens, J. & Grosse, R. (2015). "Optimizing Neural Networks with Kronecker-Factored Approximate Curvature." *ICML*. (K-FAC)

### Text-to-Image Generation
- Rombach, R. et al. (2022). "High-Resolution Image Synthesis with Latent Diffusion Models." *CVPR*. (Stable Diffusion)
- Ramesh, A. et al. (2022). "Hierarchical Text-Conditional Image Generation with CLIP Latents." arXiv. (DALL-E 2)
- Ho, J. & Salimans, T. (2022). "Classifier-Free Diffusion Guidance." *NeurIPS Workshop*.
- Peebles, W. & Xie, S. (2023). "Scalable Diffusion Models with Transformers." *ICCV*. (DiT)
- Zhang, L., Rao, A. & Agrawala, M. (2023). "Adding Conditional Control to Text-to-Image Diffusion Models." *ICCV*. (ControlNet)
- Ye, H. et al. (2023). "IP-Adapter: Text Compatible Image Prompt Adapter." arXiv.
- Ruiz, N. et al. (2023). "DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation." *CVPR*.
- Esser, P. et al. (2024). "Scaling Rectified Flow Transformers for High-Resolution Image Synthesis." *ICML*. (SD3)
- Schuhmann, C. et al. (2022). "LAION-5B." *NeurIPS*.

### Positional Encoding
- Su, J. et al. (2021). "RoFormer: Enhanced Transformer with Rotary Position Embedding." arXiv:2104.09864. (RoPE)
- Press, O., Smith, N. & Lewis, M. (2022). "Train Short, Test Long: Attention with Linear Biases." *ICLR*. (ALiBi)
- Shaw, P., Uszkoreit, J. & Vaswani, A. (2018). "Self-Attention with Relative Position Representations." *NAACL*.
- Chen, S. et al. (2023). "Extending Context Window of LLMs via Positional Interpolation." arXiv.
- Peng, B. et al. (2023). "YaRN: Efficient Context Window Extension of Large Language Models." arXiv.

### Quantization
- Frantar, E. et al. (2022). "GPTQ: Accurate Post-Training Quantization for Generative Pre-Trained Transformers." *ICLR 2023*.
- Lin, J. et al. (2023). "AWQ: Activation-Aware Weight Quantization." *MLSys 2024*.
- Dettmers, T. et al. (2022). "LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale." *NeurIPS*.
- Dettmers, T. et al. (2023). "QLoRA: Efficient Finetuning of Quantized Language Models." *NeurIPS*.
- Xiao, G. et al. (2023). "SmoothQuant: Accurate and Efficient Post-Training Quantization." *ICML*.
- Wang, H. et al. (2023). "BitNet: Scaling 1-bit Transformers for Large Language Models." arXiv.
- Ma, S. et al. (2024). "The Era of 1-bit LLMs: All Large Language Models are in 1.58 Bits." arXiv.

### Prompt Engineering and In-Context Learning
- Brown, T. et al. (2020). "Language Models are Few-Shot Learners." *NeurIPS*. (GPT-3 / ICL)
- Wei, J. et al. (2022). "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models." *NeurIPS*.
- Kojima, T. et al. (2022). "Large Language Models are Zero-Shot Reasoners." *NeurIPS*.
- Wang, X. et al. (2023). "Self-Consistency Improves Chain of Thought Reasoning." *ICLR*.
- von Oswald, J. et al. (2023). "Transformers Learn In-Context by Gradient Descent." *ICML*.
- Olsson, C. et al. (2022). "In-context Learning and Induction Heads." Anthropic.
- Xie, S. et al. (2022). "An Explanation of In-context Learning as Implicit Bayesian Inference." *ICLR*.

### Bayesian Deep Learning
- MacKay, D. (1992). "A Practical Bayesian Framework for Backpropagation Networks." *Neural Computation*.
- Gal, Y. & Ghahramani, Z. (2016). "Dropout as a Bayesian Approximation." *ICML*.
- Blundell, C. et al. (2015). "Weight Uncertainty in Neural Networks." *ICML*. (Bayes by Backprop)
- Lakshminarayanan, B. et al. (2017). "Simple and Scalable Predictive Uncertainty Estimation using Deep Ensembles." *NeurIPS*.
- Guo, C. et al. (2017). "On Calibration of Modern Neural Networks." *ICML*.
- Daxberger, E. et al. (2021). "Laplace Redux — Effortless Bayesian Deep Learning." *NeurIPS*.
- Wilson, A.G. & Izmailov, P. (2020). "Bayesian Deep Learning and a Probabilistic Perspective of Generalization." *NeurIPS*.

### Image Classification Milestones
- Krizhevsky, A., Sutskever, I. & Hinton, G. (2012). "ImageNet Classification with Deep CNNs." *NeurIPS*. (AlexNet)
- Simonyan, K. & Zisserman, A. (2014). "Very Deep Convolutional Networks." *ICLR 2015*. (VGG)
- Szegedy, C. et al. (2015). "Going Deeper with Convolutions." *CVPR*. (GoogLeNet/Inception)
- He, K. et al. (2016). "Deep Residual Learning for Image Recognition." *CVPR*. (ResNet)
- Huang, G. et al. (2017). "Densely Connected Convolutional Networks." *CVPR*. (DenseNet)
- Tan, M. & Le, Q. (2019). "EfficientNet: Rethinking Model Scaling." *ICML*.
- Dosovitskiy, A. et al. (2020). "An Image is Worth 16x16 Words." *ICLR 2021*. (ViT)
- Liu, Z. et al. (2021). "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows." *ICCV*.
- Touvron, H. et al. (2021). "Training Data-Efficient Image Transformers." *ICML*. (DeiT)
- Russakovsky, O. et al. (2015). "ImageNet Large Scale Visual Recognition Challenge." *IJCV*.

### Tokenization
- Gage, P. (1994). "A New Algorithm for Data Compression." *C Users Journal*, 12(2).
- Sennrich, R., Haddow, B. & Birch, A. (2016). "Neural Machine Translation of Rare Words with Subword Units." *ACL*.
- Kudo, T. & Richardson, J. (2018). "SentencePiece: A simple and language independent subword tokenizer." *EMNLP*.
- Kudo, T. (2018). "Subword Regularization: Improving Neural Network Translation Models with Multiple Subword Candidates." *ACL*.
- Schuster, M. & Nakajima, K. (2012). "Japanese and Korean voice search." *ICASSP*. (WordPiece)
- Petrov, A. et al. (2023). "Language Model Tokenizers Introduce Unfairness Between Languages." arXiv:2305.15425.
- OpenAI (2022). tiktoken. https://github.com/openai/tiktoken.

### Transfer Learning
- Donahue, J. et al. (2014). "DeCAF: A Deep Convolutional Activation Feature for Generic Visual Recognition." *ICML*.
- Howard, J. & Ruder, S. (2018). "Universal Language Model Fine-tuning for Text Classification." *ACL*. (ULMFiT)
- Kornblith, S. et al. (2019). "Do Better ImageNet Models Transfer Better?" *CVPR*.
- Houlsby, N. et al. (2019). "Parameter-Efficient Transfer Learning for NLP." *ICML*. (Adapters)
- Ganin, Y. et al. (2016). "Domain-Adversarial Training of Neural Networks." *JMLR*. (DANN)
- Bommasani, R. et al. (2021). "On the Opportunities and Risks of Foundation Models." arXiv:2108.07258.
- Ilharco, G. et al. (2023). "Editing Models with Task Arithmetic." *ICLR*.
- Chung, H.W. et al. (2022). "Scaling Instruction-Finetuned Language Models." arXiv. (FLAN-T5)
- Li, X.L. & Liang, P. (2021). "Prefix-Tuning: Optimizing Continuous Prompts for Generation." *ACL*.
- Lester, B., Al-Rfou, R. & Constant, N. (2021). "The Power of Scale for Parameter-Efficient Prompt Tuning." *EMNLP*.

### Adversarial Robustness
- Szegedy, C. et al. (2014). "Intriguing Properties of Neural Networks." *ICLR*.
- Goodfellow, I.J., Shlens, J. & Szegedy, C. (2015). "Explaining and Harnessing Adversarial Examples." *ICLR*. (FGSM)
- Madry, A. et al. (2018). "Towards Deep Learning Models Resistant to Adversarial Attacks." *ICLR*. (PGD)
- Carlini, N. & Wagner, D. (2017). "Towards Evaluating the Robustness of Neural Networks." *IEEE S&P*. (C&W)
- Croce, F. & Hein, M. (2020). "Reliable Evaluation of Adversarial Robustness with an Ensemble of Attacks." *ICML*. (AutoAttack)
- Cohen, J., Rosenfeld, E. & Kolter, J.Z. (2019). "Certified Adversarial Robustness via Randomized Smoothing." *ICML*.
- Tsipras, D. et al. (2019). "Robustness May Be at Odds with Accuracy." *ICLR*.
- Ilyas, A. et al. (2019). "Adversarial Examples Are Not Bugs, They Are Features." *NeurIPS*.
- Zhang, H. et al. (2019). "Theoretically Principled Trade-off between Robustness and Accuracy." *ICML*. (TRADES)

### Neural ODEs and Continuous Models
- Chen, R.T.Q. et al. (2018). "Neural Ordinary Differential Equations." *NeurIPS*. (Best Paper)
- Grathwohl, W. et al. (2019). "FFJORD: Free-form Continuous Dynamics for Scalable Reversible Generative Models." *ICLR*.
- Dupont, E., Doucet, A. & Teh, Y.W. (2019). "Augmented Neural ODEs." *NeurIPS*.
- Rubanova, Y., Chen, R.T.Q. & Duvenaud, D. (2019). "Latent ODEs for Irregularly-Sampled Time Series." *NeurIPS*.
- Lipman, Y. et al. (2023). "Flow Matching for Generative Modeling." *ICLR*.
- Liu, X. et al. (2023). "Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow." *ICLR*.
- Song, Y. et al. (2021). "Score-Based Generative Modeling through Stochastic Differential Equations." *ICLR*.
- Kidger, P. (2022). "On Neural Differential Equations." PhD Thesis, University of Oxford.

### Efficient Attention Variants
- Dao, T. et al. (2022). "FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness." *NeurIPS*.
- Dao, T. (2023). "FlashAttention-2: Faster Attention with Better Parallelism and Work Partitioning." *ICLR 2024*.
- Shah, J. et al. (2024). "FlashAttention-3: Fast and Accurate Attention with Asynchrony and Low-precision." arXiv:2407.08691.
- Shazeer, N. (2019). "Fast Transformer Decoding: One Write-Head is All You Need." arXiv:1911.02150. (MQA)
- Ainslie, J. et al. (2023). "GQA: Training Generalized Multi-Query Transformer Models." *EMNLP*.
- Beltagy, I. et al. (2020). "Longformer: The Long-Document Transformer." arXiv:2004.05150.
- Zaheer, M. et al. (2020). "Big Bird: Transformers for Longer Sequences." *NeurIPS*.
- Child, R. et al. (2019). "Generating Long Sequences with Sparse Transformers." arXiv:1904.10509.
- Katharopoulos, A. et al. (2020). "Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention." *ICML*.
- Choromanski, K. et al. (2021). "Rethinking Attention with Performers." *ICLR*.
- Kwon, W. et al. (2023). "Efficient Memory Management for LLM Serving with PagedAttention." *SOSP*.
- Xiao, G. et al. (2023). "Efficient Streaming Language Models with Attention Sinks." *ICLR 2024*.

### Data Augmentation
- Zhang, H. et al. (2018). "mixup: Beyond Empirical Risk Minimization." *ICLR*.
- Yun, S. et al. (2019). "CutMix: Regularization Strategy to Train Strong Classifiers." *ICCV*.
- DeVries, T. & Taylor, G.W. (2017). "Improved Regularization of CNNs with Cutout." arXiv:1708.04552.
- Cubuk, E. et al. (2019). "AutoAugment: Learning Augmentation Strategies from Data." *CVPR*.
- Cubuk, E. et al. (2020). "RandAugment: Practical Automated Data Augmentation." *NeurIPS*.
- Müller, S. & Hutter, F. (2021). "TrivialAugment: Tuning-free Yet State-of-the-Art Data Augmentation." *ICCV*.
- Park, D.S. et al. (2019). "SpecAugment: A Simple Data Augmentation Method for ASR." *Interspeech*.
- Verma, V. et al. (2019). "Manifold Mixup: Better Representations by Interpolating Hidden States." *ICML*.

### World Models and Predictive Learning
- Ha, D. & Schmidhuber, J. (2018). "World Models." arXiv:1803.10122.
- Hafner, D. et al. (2020). "Dream to Control: Learning Behaviors by Latent Imagination." *ICLR*. (Dreamer v1)
- Hafner, D. et al. (2023). "Mastering Diverse Domains through World Models." arXiv. (DreamerV3)
- Schrittwieser, J. et al. (2020). "Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model." *Nature*. (MuZero)
- LeCun, Y. (2022). "A Path Towards Autonomous Machine Intelligence." OpenReview.
- Assran, M. et al. (2023). "Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture." *CVPR*. (I-JEPA)
- Bardes, A. et al. (2024). "V-JEPA: Revisiting Feature Prediction for Learning Visual Representations from Video." arXiv.
- Micheli, V. et al. (2023). "Transformers are Sample-Efficient World Learners." *ICLR*. (IRIS)
- Bruce, J. et al. (2024). "Genie: Generative Interactive Environments." *ICML*.

### Reasoning in LLMs
- Wei, J. et al. (2022). "Chain-of-Thought Prompting Elicits Reasoning." *NeurIPS*.
- Wang, X. et al. (2023). "Self-Consistency Improves Chain of Thought Reasoning." *ICLR*.
- Yao, S. et al. (2023). "Tree of Thoughts: Deliberate Problem Solving with LLMs." *NeurIPS*.
- Lightman, H. et al. (2023). "Let's Verify Step by Step." arXiv. (PRM)
- DeepSeek-AI (2025). "DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via RL." arXiv:2501.12948.
- Snell, C. et al. (2024). "Scaling LLM Test-Time Compute Optimally." arXiv.
- Zelikman, E. et al. (2022). "STaR: Bootstrapping Reasoning With Reasoning." *NeurIPS*.
- Lanham, T. et al. (2023). "Measuring Faithfulness in Chain-of-Thought Reasoning." arXiv.

### Model Merging and Editing
- Ilharco, G. et al. (2023). "Editing Models with Task Arithmetic." *ICLR*.
- Wortsman, M. et al. (2022). "Model Soups: Averaging Weights of Multiple Fine-tuned Models." *ICML*.
- Yadav, P. et al. (2023). "TIES-Merging: Resolving Interference When Merging Models." *NeurIPS*.
- Yu, L. et al. (2024). "Language Models are Super Mario: Absorbing Abilities from Homologous Models." *ICML*. (DARE)
- Meng, K. et al. (2022). "Locating and Editing Factual Associations in GPT." *NeurIPS*. (ROME)
- Meng, K. et al. (2023). "Mass-Editing Memory in a Transformer." *ICLR*. (MEMIT)
- Ainsworth, S. et al. (2023). "Git Re-Basin: Merging Models Modulo Permutation Symmetries." *ICLR*.
- Akiba, T. et al. (2024). "Evolutionary Optimization of Model Merging Recipes." arXiv. (Sakana AI)

### Test-Time Adaptation
- Wang, D. et al. (2021). "Tent: Fully Test-Time Adaptation by Entropy Minimization." *ICLR*.
- Sun, Y. et al. (2020). "Test-Time Training with Self-Supervision for Generalization under Distribution Shifts." *ICML*.
- Sun, Y. et al. (2024). "Learning to (Learn at Test Time): RNNs with Expressive Hidden States." arXiv. (TTT layers)
- Wang, Q. et al. (2022). "Continual Test-Time Domain Adaptation." *CVPR*. (CoTTA)
- Niu, S. et al. (2022). "Efficient Test-Time Model Adaptation without Forgetting." *ICML*. (EATA)
- Shu, M. et al. (2022). "Test-Time Prompt Tuning for Zero-Shot Generalization." *NeurIPS*. (TPT)
- Liang, J. et al. (2023). "A Comprehensive Survey on Test-Time Adaptation under Distribution Shifts." arXiv.

### Synthetic Data Generation
- Wang, Y. et al. (2023). "Self-Instruct: Aligning Language Models with Self-Generated Instructions." *ACL*.
- Taori, R. et al. (2023). "Stanford Alpaca: An Instruction-following LLaMA Model." GitHub.
- Mukherjee, S. et al. (2023). "Orca: Progressive Learning from Complex Explanation Traces of GPT-4." arXiv.
- Gunasekar, S. et al. (2023). "Textbooks Are All You Need." arXiv. (Phi-1)
- Li, Y. et al. (2023). "Textbooks Are All You Need II: phi-1.5 technical report." arXiv.
- Shumailov, I. et al. (2024). "The Curse of Recursion: Training on Generated Data Makes Models Forget." *Nature*.
- Xu, C. et al. (2023). "WizardLM: Empowering Large Language Models to Follow Complex Instructions." arXiv. (Evol-Instruct)
- Zelikman, E. et al. (2022). "STaR: Bootstrapping Reasoning With Reasoning." *NeurIPS*.
- Chen, Z. et al. (2024). "Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models." *ICML*. (SPIN)
- Mitra, A. et al. (2023). "Orca 2: Teaching Small Language Models How to Reason." arXiv.
- Tian, Y. et al. (2024). "StableRep: Synthetic Images from Text-to-Image Models Make Strong Visual Representation Learners." *NeurIPS*.

### Neural Network Compression
- LeCun, Y., Denker, J. & Solla, S. (1990). "Optimal Brain Damage." *NeurIPS*.
- Frankle, J. & Carlin, M. (2019). "The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks." *ICLR*.
- Frantar, E. & Alistarh, D. (2023). "SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot." *ICML*.
- Sun, M. et al. (2024). "A Simple and Effective Pruning Approach for Large Language Models." *ICLR*. (Wanda)
- Evci, U. et al. (2020). "Rigging the Lottery: Making All Tickets Winners." *ICML*. (RigL)
- Michel, P., Levy, O. & Neubig, G. (2019). "Are Sixteen Heads Really Better than One?" *NeurIPS*.
- Zhu, M. & Gupta, S. (2017). "To Prune, or Not to Prune." arXiv.
- Ashkboos, S. et al. (2024). "SliceGPT: Compress Large Language Models by Deleting Rows and Columns." *ICLR*.
- Hassibi, B. & Stork, D. (1993). "Second Order Derivatives for Network Pruning: Optimal Brain Surgeon." *NeurIPS*.
- Han, S. et al. (2015). "Deep Compression." *ICLR 2016*.

### Reward Modeling and RLHF
- Christiano, P. et al. (2017). "Deep Reinforcement Learning from Human Preferences." *NeurIPS*.
- Ouyang, L. et al. (2022). "Training language models to follow instructions with human feedback." *NeurIPS*. (InstructGPT)
- Stiennon, N. et al. (2020). "Learning to Summarize from Human Feedback." *NeurIPS*.
- Rafailov, R. et al. (2023). "Direct Preference Optimization." *NeurIPS*. (DPO)
- Schulman, J. et al. (2017). "Proximal Policy Optimization Algorithms." arXiv. (PPO)
- Gao, L. et al. (2022). "Scaling Laws for Reward Model Overoptimization." *ICML 2023*.
- Ethayarajh, K. et al. (2024). "KTO: Model Alignment as Prospect Theoretic Optimization." arXiv.
- Azar, M.G. et al. (2024). "A General Theoretical Paradigm to Understand Learning from Human Feedback." *AISTATS*. (IPO)
- Bai, Y. et al. (2022). "Training a Helpful and Harmless Assistant with RLHF." arXiv. (Anthropic)
- DeepSeek-AI (2025). "DeepSeek-R1." arXiv. (GRPO)

### Retrieval-Augmented Generation
- Lewis, P. et al. (2020). "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks." *NeurIPS*.
- Karpukhin, V. et al. (2020). "Dense Passage Retrieval for Open-Domain Question Answering." *EMNLP*. (DPR)
- Gao, L. et al. (2023). "Precise Zero-Shot Dense Retrieval without Relevance Labels." *ACL*. (HyDE)
- Asai, A. et al. (2024). "Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection." *ICLR*.
- Yan, S. et al. (2024). "Corrective Retrieval Augmented Generation." arXiv. (CRAG)
- Edge, D. et al. (2024). "From Local to Global: A Graph RAG Approach." arXiv. (Graph RAG, Microsoft)
- Khattab, O. & Zaharia, M. (2020). "ColBERT: Efficient and Effective Passage Search." *SIGIR*.
- Es, S. et al. (2024). "RAGAS: Automated Evaluation of Retrieval Augmented Generation." arXiv.
- Borgeaud, S. et al. (2022). "Improving Language Models by Retrieving from Trillions of Tokens." *ICML*. (RETRO)

### Long-Context and Memory Architectures
- Chen, S. et al. (2023). "Extending Context Window of LLMs via Positional Interpolation." arXiv.
- Peng, B. et al. (2023). "YaRN: Efficient Context Window Extension of Large Language Models." arXiv.
- Munkhdalai, T. et al. (2024). "Leave No Context Behind: Efficient Infinite Context Transformers with Infini-attention." arXiv.
- Liu, H. et al. (2023). "Ring Attention with Blockwise Transformers for Near-Infinite Context." arXiv.
- Dai, Z. et al. (2019). "Transformer-XL: Attentive Language Models Beyond a Fixed-Length Context." *ACL*.
- Bulatov, A. et al. (2022). "Recurrent Memory Transformer." *NeurIPS*.
- Mohtashami, A. & Jaggi, M. (2023). "Landmark Attention: Random-Access Infinite Context Length." arXiv.
- Xiao, G. et al. (2023). "Efficient Streaming Language Models with Attention Sinks." *ICLR 2024*.
- Zhang, Z. et al. (2023). "H2O: Heavy-Hitter Oracle for Efficient Generative Inference." *NeurIPS*.
- Liu, N.F. et al. (2023). "Lost in the Middle: How Language Models Use Long Contexts." *TACL*.
- Hsieh, C.-P. et al. (2024). "RULER: What's the Real Context Size of Your Long-Context Language Models?" arXiv.
- Reid, M. et al. (2024). "Gemini 1.5: Unlocking Multimodal Understanding Across Millions of Tokens." arXiv.

### Mechanistic Interpretability
- Olsson, C. et al. (2022). "In-context Learning and Induction Heads." Anthropic.
- Elhage, N. et al. (2021). "A Mathematical Framework for Transformer Circuits." Anthropic.
- Elhage, N. et al. (2022). "Toy Models of Superposition." Anthropic.
- Wang, K. et al. (2023). "Interpretability in the Wild: A Circuit for Indirect Object Identification in GPT-2 Small." *ICLR*.
- Templeton, A. et al. (2024). "Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet." Anthropic.
- Gao, L. et al. (2024). "Scaling and Evaluating Sparse Autoencoders." arXiv. (TopK SAEs)
- Conmy, A. et al. (2023). "Towards Automated Circuit Discovery for Mechanistic Interpretability." *NeurIPS*.
- Zou, A. et al. (2023). "Representation Engineering: A Top-Down Approach to AI Transparency." arXiv.
- Bills, S. et al. (2023). "Language Models Can Explain Neurons in Language Models." OpenAI.
- Olah, C. et al. (2020). "Zoom In: An Introduction to Circuits." *Distill*.

### Language Model Pre-Training
- Devlin, J. et al. (2018). "BERT: Pre-training of Deep Bidirectional Transformers." *NAACL 2019*.
- Radford, A. et al. (2018). "Improving Language Understanding by Generative Pre-Training." OpenAI. (GPT)
- Radford, A. et al. (2019). "Language Models are Unsupervised Multitask Learners." OpenAI. (GPT-2)
- Brown, T. et al. (2020). "Language Models are Few-Shot Learners." *NeurIPS*. (GPT-3)
- Raffel, C. et al. (2020). "Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer." *JMLR*. (T5)
- Liu, Y. et al. (2019). "RoBERTa: A Robustly Optimized BERT Pretraining Approach." arXiv.
- Clark, K. et al. (2020). "ELECTRA: Pre-training Text Encoders as Discriminators." *ICLR*.
- Touvron, H. et al. (2023). "LLaMA: Open and Efficient Foundation Language Models." arXiv.
- Peters, M. et al. (2018). "Deep Contextualized Word Representations." *NAACL*. (ELMo)
- He, P. et al. (2021). "DeBERTa: Decoding-enhanced BERT with Disentangled Attention." *ICLR*.
- Tay, Y. et al. (2022). "UL2: Unifying Language Learning Paradigms." *ICLR 2023*.

### Optimization Theory for Deep Learning
- Soudry, D. et al. (2018). "The Implicit Bias of Gradient Descent on Separable Data." *JMLR*.
- Jacot, A., Gabriel, F. & Hongler, C. (2018). "Neural Tangent Kernel." *NeurIPS*.
- Cohen, J. et al. (2021). "Gradient Descent on Neural Networks Typically Occurs at the Edge of Stability." *ICLR*.
- Power, A. et al. (2022). "Grokking: Generalization Beyond Overfitting on Small Algorithmic Datasets." arXiv.
- Nanda, N. et al. (2023). "Progress Measures for Grokking via Mechanistic Interpretability." *ICLR*.
- Yang, G. & Hu, E.J. (2021). "Tensor Programs V: Tuning Large Neural Networks via Zero-Shot Hyperparameter Transfer." arXiv. (μP)
- Chizat, L. & Bach, F. (2019). "On the Global Convergence of Gradient Descent for Over-parameterized Models." *NeurIPS*.
- Arora, S. et al. (2019). "Implicit Regularization in Deep Matrix Factorization." *NeurIPS*.

### Autonomous Driving Perception
- Lang, A. et al. (2019). "PointPillars: Fast Encoders for Object Detection from Point Clouds." *CVPR*.
- Yin, T. et al. (2021). "Center-Based 3D Object Detection and Tracking." *CVPR*. (CenterPoint)
- Li, Z. et al. (2022). "BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images." *ECCV*.
- Philion, J. & Fidler, S. (2020). "Lift, Splat, Shoot: Encoding Images From Arbitrary Camera Rigs." *ECCV*. (LSS)
- Liu, Z. et al. (2023). "BEVFusion: Multi-Task Multi-Sensor Fusion with Unified BEV Representation." *ICRA*.
- Hu, Y. et al. (2023). "Planning-oriented Autonomous Driving." *CVPR*. (UniAD)
- Liao, B. et al. (2023). "MapTR: Structured Modeling and Learning for Online Vectorized HD Map Construction." *ICLR*.
- Caesar, H. et al. (2020). "nuScenes: A Multimodal Dataset for Autonomous Driving." *CVPR*.
- Sun, P. et al. (2020). "Scalability in Perception for Autonomous Driving: Waymo Open Dataset." *CVPR*.

### Protein and Molecular Deep Learning
- Jumper, J. et al. (2021). "Highly Accurate Protein Structure Prediction with AlphaFold." *Nature*.
- Abramson, J. et al. (2024). "Accurate structure prediction of biomolecular interactions with AlphaFold 3." *Nature*.
- Rives, A. et al. (2021). "Biological Structure and Function Emerge from Scaling Unsupervised Learning to 250 Million Protein Sequences." *PNAS*. (ESM)
- Lin, Z. et al. (2023). "Evolutionary-scale prediction of atomic-level protein structure with a language model." *Science*. (ESMFold)
- Watson, J. et al. (2023). "De novo design of protein structure and function with RFdiffusion." *Nature*.
- Schütt, K. et al. (2017). "SchNet: A Continuous-Filter CNN for Modeling Quantum Interactions." *NeurIPS*.
- Gasteiger, J. et al. (2020). "Directional Message Passing for Molecular Graphs." *ICLR*. (DimeNet)
- Hoogeboom, E. et al. (2022). "Equivariant Diffusion for Molecule Generation in 3D." *ICML*. (EDM)
- Satorras, V.G. et al. (2021). "E(n) Equivariant Graph Neural Networks." *ICML*. (EGNN)
- Avsec, Ž. et al. (2021). "Effective Gene Expression Prediction from Sequence." *Nature Methods*. (Enformer)
- Nguyen, E. et al. (2024). "Sequence Modeling and Design from Molecular to Genome Scale with Evo." *Science*.

### Medical Imaging
- Rajpurkar, P. et al. (2017). "CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays." arXiv.
- Ronneberger, O., Fischer, P. & Brox, T. (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation." *MICCAI*.
- Isensee, F. et al. (2021). "nnU-Net: A Self-Configuring Method for Deep Learning-Based Biomedical Image Segmentation." *Nature Methods*.
- Esteva, A. et al. (2017). "Dermatologist-level Classification of Skin Cancer." *Nature*.
- Gulchan, V. et al. (2016). "Development and Validation of a Deep Learning Algorithm for Detection of Diabetic Retinopathy." *JAMA*.
- Irvin, J. et al. (2019). "CheXpert: A Large Chest Radiograph Dataset." *AAAI*.
- Lu, M. et al. (2021). "Data-Efficient Computational Pathology on Whole-Slide Images." *Nature Biomedical Engineering*. (CLAM)
- Ma, J. et al. (2024). "Segment Anything in Medical Images." *Nature Communications*. (MedSAM)
- Gichoya, J. et al. (2022). "AI recognition of patient race in medical imaging." *Lancet Digital Health*.

### NLP Tasks
- Vaswani, A. et al. (2017). "Attention Is All You Need." *NeurIPS*.
- Rajpurkar, P. et al. (2016). "SQuAD: 100,000+ Questions for Machine Comprehension." *EMNLP*.
- Bahdanau, D., Cho, K. & Bengio, Y. (2015). "Neural Machine Translation by Jointly Learning to Align and Translate." *ICLR*.
- Lample, G. et al. (2016). "Neural Architectures for Named Entity Recognition." *NAACL*.
- See, A., Liu, P. & Manning, C. (2017). "Get to the Point: Summarization with Pointer-Generator Networks." *ACL*.
- Zhang, J. et al. (2020). "PEGASUS: Pre-training with Extracted Gap-sentences for Abstractive Summarization." *ICML*.
- Kim, Y. (2014). "Convolutional Neural Networks for Sentence Classification." *EMNLP*.
- Wang, A. et al. (2019). "SuperGLUE: A Stickier Benchmark." *NeurIPS*.
- Conneau, A. et al. (2020). "Unsupervised Cross-lingual Representation Learning at Scale." *ACL*. (XLM-R)

### Energy-Based Models and Contrastive Learning
- Oord, A. van den et al. (2018). "Representation Learning with Contrastive Predictive Coding." arXiv. (CPC/InfoNCE)
- Chen, T. et al. (2020). "A Simple Framework for Contrastive Learning of Visual Representations." *ICML*. (SimCLR)
- Gutmann, M. & Hyvärinen, A. (2010). "Noise-Contrastive Estimation." *AISTATS*.
- HaoChen, J. et al. (2021). "Provable Guarantees for Self-Supervised Deep Learning with Spectral Contrastive Loss." *NeurIPS*.
- Wang, T. & Isola, P. (2020). "Understanding Contrastive Representation Learning through Alignment and Uniformity." *ICML*.
- Grill, J.B. et al. (2020). "Bootstrap Your Own Latent." *NeurIPS*. (BYOL)
- Chen, X. & He, K. (2021). "Exploring Simple Siamese Representation Learning." *CVPR*. (SimSiam)
- Bardes, A., Ponce, J. & LeCun, Y. (2022). "VICReg: Variance-Invariance-Covariance Regularization." *ICLR*.
- Zbontar, J. et al. (2021). "Barlow Twins: Self-Supervised Learning via Redundancy Reduction." *ICML*.
- Hyvärinen, A. (2005). "Estimation of Non-Normalized Statistical Models by Score Matching." *JMLR*.
- LeCun, Y. et al. (2006). "A Tutorial on Energy-Based Learning." *Predicting Structured Data*.

### Neural Network Initialization
- Glorot, X. & Bengio, Y. (2010). "Understanding the difficulty of training deep feedforward neural networks." *AISTATS*. (Xavier)
- He, K. et al. (2015). "Delving Deep into Rectifiers." *ICCV*. (Kaiming initialization)
- Zhang, H. et al. (2019). "Fixup Initialization: Residual Learning Without Normalization." *ICLR*.
- Yang, G. & Hu, E.J. (2021). "Tensor Programs V: Tuning Large Neural Networks via Zero-Shot Hyperparameter Transfer." arXiv. (μP)
- Saxe, A., McClelland, J. & Ganguli, S. (2014). "Exact Solutions to the Nonlinear Dynamics of Learning in Deep Linear Networks." *ICLR*.
- Huang, X.S. et al. (2020). "Improving Transformer Optimization Through Better Initialization." *ICML*. (T-Fixup)
- Wang, H. et al. (2022). "DeepNet: Scaling Transformers to 1,000 Layers." arXiv.
- Mishkin, D. & Matas, J. (2016). "All You Need is a Good Init." *ICLR*. (LSUV)

### Robotics and Embodied AI
- Brohan, A. et al. (2023). "RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control." arXiv.
- Brohan, A. et al. (2022). "RT-1: Robotics Transformer for Real-World Control at Scale." arXiv.
- Team Octo et al. (2024). "Octo: An Open-Source Generalist Robot Policy." arXiv.
- Ahn, M. et al. (2022). "Do As I Can, Not As I Say: Grounding Language in Robotic Affordances." arXiv. (SayCan)
- Chi, C. et al. (2023). "Diffusion Policy: Visuomotor Policy Learning via Action Diffusion." *RSS*.
- Zhao, T. et al. (2023). "Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware." *RSS*. (ALOHA/ACT)
- Tobin, J. et al. (2017). "Domain Randomization for Transferring Deep Neural Networks from Simulation to the Real World." *IROS*.
- Liang, J. et al. (2023). "Code as Policies: Language Model Programs for Embodied Control." *ICRA*.
- Open X-Embodiment Collaboration (2023). "Open X-Embodiment: Robotic Learning Datasets and RT-X Models." arXiv.
- Haarnoja, T. et al. (2018). "Soft Actor-Critic: Off-Policy Maximum Entropy Deep RL." *ICML*. (SAC)
- Ross, S., Gordon, G. & Bagnell, J.A. (2011). "A Reduction of Imitation Learning to No-Regret Online Learning." *AISTATS*. (DAgger)

### Time Series Forecasting
- Oreshkin, B. et al. (2020). "N-BEATS: Neural Basis Expansion Analysis for Interpretable Time Series Forecasting." *ICLR*.
- Nie, Y. et al. (2023). "A Time Series is Worth 64 Words: Long-term Forecasting with Transformers." *ICLR*. (PatchTST)
- Zhou, H. et al. (2021). "Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting." *AAAI*. (Best Paper)
- Zeng, A. et al. (2023). "Are Transformers Effective for Time Series Forecasting?" *AAAI*. (DLinear)
- Salinas, D. et al. (2020). "DeepAR: Probabilistic Forecasting with Autoregressive Recurrent Networks." *IJOF*.
- Das, A. et al. (2024). "A Decoder-Only Foundation Model for Time-Series Forecasting." *ICML*. (TimesFM)
- Ansari, A.F. et al. (2024). "Chronos: Learning the Language of Time Series." arXiv. (Amazon)
- Woo, G. et al. (2024). "Unified Training of Universal Time Series Forecasting Transformers." *ICML*. (Moirai)
- Liu, Y. et al. (2024). "iTransformer: Inverted Transformers Are Effective for Time Series Forecasting." *ICLR*.
- Makridakis, S. et al. (2018). "The M4 Competition." *IJF*.

### Recommender Systems
- Covington, P., Adams, J. & Sargin, E. (2016). "Deep Neural Networks for YouTube Recommendations." *RecSys*.
- He, X. et al. (2017). "Neural Collaborative Filtering." *WWW*. (NCF)
- Kang, W. & McAuley, J. (2018). "Self-Attentive Sequential Recommendation." *ICDM*. (SASRec)
- Sun, F. et al. (2019). "BERT4Rec: Sequential Recommendation with Bidirectional Encoder Representations." *CIKM*.
- Cheng, H. et al. (2016). "Wide & Deep Learning for Recommender Systems." *DLRS*. (Google)
- Naumov, M. et al. (2019). "Deep Learning Recommendation Model for Personalization and Recommendation Systems." arXiv. (DLRM, Meta)
- Zhou, G. et al. (2018). "Deep Interest Network for Click-Through Rate Prediction." *KDD*. (DIN, Alibaba)
- Koren, Y., Bell, R. & Volinsky, C. (2009). "Matrix Factorization Techniques for Recommender Systems." *Computer*.
- Yi, X. et al. (2019). "Sampling-Bias-Corrected Neural Modeling for Large Corpus Item Recommendations." *RecSys*.
- Hidasi, B. et al. (2016). "Session-Based Recommendations with Recurrent Neural Networks." *ICLR*. (GRU4Rec)

### Audio Generation
- Oord, A. van den et al. (2016). "WaveNet: A Generative Model for Raw Audio." arXiv. (DeepMind)
- Kong, J., Kim, J. & Bae, J. (2020). "HiFi-GAN: Generative Adversarial Networks for Efficient and High Fidelity Speech Synthesis." *NeurIPS*.
- Zeghidour, N. et al. (2021). "SoundStream: An End-to-End Neural Audio Codec." *IEEE/ACM TASLP*.
- Défossez, A. et al. (2022). "High Fidelity Neural Audio Compression." arXiv. (EnCodec, Meta)
- Wang, C. et al. (2023). "Neural Codec Language Models are Zero-Shot Text to Speech Synthesizers." arXiv. (VALL-E)
- Copet, J. et al. (2023). "Simple and Controllable Music Generation." *NeurIPS*. (MusicGen)
- Borsos, Z. et al. (2023). "AudioLM: A Language Modeling Approach to Audio Generation." *IEEE/ACM TASLP*.
- Liu, H. et al. (2023). "AudioLDM: Text-to-Audio Generation with Latent Diffusion Models." *ICML*.
- Kim, J. et al. (2021). "Conditional Variational Autoencoder with Adversarial Learning for End-to-End TTS." *ICML*. (VITS)
- Agostinelli, A. et al. (2023). "MusicLM: Generating Music From Text." arXiv. (Google)

### Fairness and Bias
- Buolamwini, J. & Gebru, T. (2018). "Gender Shades: Intersectional Accuracy Disparities in Commercial Gender Classification." *FAccT*.
- Chouldechova, A. (2017). "Fair Prediction with Disparate Impact." *Big Data*.
- Kleinberg, J., Mullainathan, S. & Raghavan, M. (2017). "Inherent Trade-Offs in the Fair Determination of Risk Scores." *ITCS*.
- Hardt, M., Price, E. & Srebro, N. (2016). "Equality of Opportunity in Supervised Learning." *NeurIPS*.
- Bolukbasi, T. et al. (2016). "Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings." *NeurIPS*.
- Mitchell, M. et al. (2019). "Model Cards for Model Reporting." *FAccT*.
- Gebru, T. et al. (2021). "Datasheets for Datasets." *CACM*.
- Dwork, C. et al. (2012). "Fairness Through Awareness." *ITCS*.
- Parrish, A. et al. (2022). "BBQ: A Hand-Built Bias Benchmark for Question Answering." *ACL*.
- Gichoya, J. et al. (2022). "AI recognition of patient race in medical imaging." *Lancet Digital Health*.

### Hardware-Software Co-Design
- Dao, T. et al. (2022). "FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness." *NeurIPS*.
- Tillet, P., Kung, H.T. & Cox, D. (2019). "Triton: An Intermediate Language and Compiler for Tiled Neural Network Computations." *MAPL*.
- Chen, T. et al. (2018). "TVM: An Automated End-to-End Optimizing Compiler for Deep Learning." *OSDI*.
- Ansel, J. et al. (2024). "PyTorch 2: Faster ML Through Dynamic Python Bytecode Transformation and Graph Compilation." *ASPLOS*. (torch.compile)
- NVIDIA (2020). "NVIDIA A100 Tensor Core GPU Architecture Whitepaper."
- NVIDIA (2022). "NVIDIA H100 Tensor Core GPU Architecture Whitepaper."
- Ivanov, A. et al. (2021). "Data Movement Is All You Need: A Case Study on Optimizing Transformers." *MLSys*.
- Ragan-Kelley, J. et al. (2013). "Halide: A Language and Compiler for Optimizing Parallelism, Locality, and Recomputation." *PLDI*.

### 3D Generation Deep Dive
- Mildenhall, B. et al. (2020). "NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis." *ECCV*.
- Kerbl, B. et al. (2023). "3D Gaussian Splatting for Real-Time Radiance Field Rendering." *SIGGRAPH*.
- Poole, B. et al. (2023). "DreamFusion: Text-to-3D using 2D Diffusion." *ICLR*.
- Wang, Z. et al. (2024). "ProlificDreamer: High-Fidelity and Diverse Text-to-3D Generation with Variational Score Distillation." *NeurIPS*.
- Müller, T. et al. (2022). "Instant Neural Graphics Primitives with a Multiresolution Hash Encoding." *SIGGRAPH*.
- Barron, J. et al. (2023). "Zip-NeRF: Anti-Aliased Grid-Based Neural Radiance Fields." *ICCV*.
- Lin, C.-H. et al. (2023). "Magic3D: High-Resolution Text-to-3D Content Creation." *CVPR*.
- Hong, Y. et al. (2024). "LRM: Large Reconstruction Model for Single Image to 3D." *ICLR*.
- Liu, R. et al. (2023). "Zero-1-to-3: Zero-shot One Image to 3D Object." *ICCV*.
- Tang, J. et al. (2024). "DreamGaussian: Generative Gaussian Splatting for Efficient 3D Content Creation." *ICLR*.

### Instruction Tuning and Multi-Task Learning
- Sanh, V. et al. (2022). "Multitask Prompted Training Enables Zero-Shot Task Generalization." *ICLR*. (T0)
- Wei, J. et al. (2022). "Finetuned Language Models Are Zero-Shot Learners." *ICLR*. (FLAN)
- Chung, H.W. et al. (2022). "Scaling Instruction-Finetuned Language Models." arXiv. (FLAN-T5/FLAN-PaLM)
- Wang, Y. et al. (2023). "Self-Instruct: Aligning Language Models with Self-Generated Instructions." *ACL*.
- Zhou, C. et al. (2023). "LIMA: Less Is More for Alignment." *NeurIPS*.
- Xu, C. et al. (2023). "WizardLM: Empowering Large Language Models to Follow Complex Instructions." arXiv. (Evol-Instruct)
- Mukherjee, S. et al. (2023). "Orca: Progressive Learning from Complex Explanation Traces of GPT-4." arXiv.
- Raffel, C. et al. (2020). "Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer." *JMLR*. (T5)
- Caruana, R. (1997). "Multitask Learning." *Machine Learning*, 28(1).

### Causal Inference and Deep Learning
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference*. 2nd ed. Cambridge University Press.
- Schölkopf, B. et al. (2021). "Toward Causal Representation Learning." *Proceedings of the IEEE*.
- Arjovsky, M. et al. (2019). "Invariant Risk Minimization." arXiv.
- Shalit, U., Johansson, F. & Sontag, D. (2017). "Estimating Individual Treatment Effect." *ICML*. (TARNet/CFR)
- Chernozhukov, V. et al. (2018). "Double/Debiased Machine Learning." *Econometrics Journal*.
- Zheng, X. et al. (2018). "DAGs with NO TEARS: Continuous Optimization for Structure Learning." *NeurIPS*.
- Khemakhem, I. et al. (2020). "Variational Autoencoders and Nonlinear ICA." *AISTATS*.
- Geirhos, R. et al. (2020). "Shortcut Learning in Deep Neural Networks." *Nature Machine Intelligence*.
- Peters, J., Janzing, D. & Schölkopf, B. (2017). *Elements of Causal Inference*. MIT Press.
- Jin, Z. et al. (2023). "CLadder: Assessing Causal Reasoning in Language Models." *NeurIPS*.

### Evaluation and Benchmarking
- Hendrycks, D. et al. (2021). "Measuring Massive Multitask Language Understanding." *ICLR*. (MMLU)
- Zheng, L. et al. (2024). "Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena." *NeurIPS*.
- Jimenez, C. et al. (2024). "SWE-bench: Can Language Models Resolve Real-World GitHub Issues?" *ICLR*.
- Liang, P. et al. (2023). "Holistic Evaluation of Language Models." *TMLR*. (HELM)
- Wang, A. et al. (2018). "GLUE: A Multi-Task Benchmark." *ICLR 2019*.
- Deng, J. et al. (2009). "ImageNet: A Large-Scale Hierarchical Image Database." *CVPR*.
- Chen, M. et al. (2021). "Evaluating Large Language Models Trained on Code." arXiv. (HumanEval)
- Cobbe, K. et al. (2021). "Training Verifiers to Solve Math Word Problems." arXiv. (GSM8K)
- Lin, S. et al. (2022). "TruthfulQA: Measuring How Models Mimic Human Falsehoods." *ACL*.

### Privacy-Preserving ML
- Dwork, C. et al. (2006). "Calibrating Noise to Sensitivity in Private Data Analysis." *TCC*.
- Abadi, M. et al. (2016). "Deep Learning with Differential Privacy." *CCS*. (DP-SGD)
- Shokri, R. et al. (2017). "Membership Inference Attacks Against Machine Learning Models." *IEEE S&P*.
- Carlini, N. et al. (2021). "Extracting Training Data from Large Language Models." *USENIX Security*.
- Carlini, N. et al. (2023). "Quantifying Memorization Across Neural Language Models." *ICLR*.
- Fredrikson, M. et al. (2015). "Model Inversion Attacks." *CCS*.
- Gentry, C. (2009). "Fully Homomorphic Encryption Using Ideal Lattices." *STOC*.
- Bagdasaryan, E. et al. (2019). "Differential Privacy Has Disparate Impact on Model Accuracy." *NeurIPS*.
- Bourtoule, L. et al. (2021). "Machine Unlearning." *IEEE S&P*. (SISA training)

### Hyperparameter Optimization
- Bergstra, J. & Bengio, Y. (2012). "Random Search for Hyper-Parameter Optimization." *JMLR*.
- Snoek, J., Larochelle, H. & Adams, R. (2012). "Practical Bayesian Optimization of Machine Learning Algorithms." *NeurIPS*.
- Bergstra, J. et al. (2011). "Algorithms for Hyper-Parameter Optimization." *NeurIPS*. (TPE)
- Li, L. et al. (2017). "Hyperband: A Novel Bandit-Based Approach to Hyperparameter Optimization." *JMLR*.
- Falkner, S., Klein, A. & Hutter, F. (2018). "BOHB: Robust and Efficient HPO at Scale." *ICML*.
- Jaderberg, M. et al. (2017). "Population Based Training of Neural Networks." arXiv. (DeepMind)
- Akiba, T. et al. (2019). "Optuna: A Next-generation HPO Framework." *KDD*.

### Knowledge Graphs and Structured Knowledge
- Bordes, A. et al. (2013). "Translating Embeddings for Modeling Multi-relational Data." *NeurIPS*. (TransE)
- Sun, Z. et al. (2019). "RotatE: Knowledge Graph Embedding by Relational Rotation in Complex Space." *ICLR*.
- Trouillon, T. et al. (2016). "Complex Embeddings for Simple Link Prediction." *ICML*. (ComplEx)
- Schlichtkrull, M. et al. (2018). "Modeling Relational Data with Graph Convolutional Networks." *ESWC*. (R-GCN)
- Zhu, Z. et al. (2021). "Neural Bellman-Ford Networks." *NeurIPS*. (NBFNet)
- Zhang, Z. et al. (2019). "ERNIE: Enhanced Language Representation with Informative Entities." *ACL*.
- Ji, S. et al. (2022). "A Survey on Knowledge Graphs." *IEEE TNNLS*.

### Speech Recognition Deep Dive
- Graves, A. et al. (2006). "Connectionist Temporal Classification." *ICML*. (CTC)
- Graves, A. (2012). "Sequence Transduction with Recurrent Neural Networks." arXiv. (RNN-T)
- Radford, A. et al. (2023). "Robust Speech Recognition via Large-Scale Weak Supervision." *ICML*. (Whisper)
- Baevski, A. et al. (2020). "wav2vec 2.0: Self-Supervised Learning of Speech Representations." *NeurIPS*.
- Hsu, W.-N. et al. (2021). "HuBERT: Self-Supervised Speech Representation Learning." *IEEE/ACM TASLP*.
- Gulati, A. et al. (2020). "Conformer: Convolution-augmented Transformer for Speech Recognition." *Interspeech*.
- Pratap, V. et al. (2023). "Scaling Speech Technology to 1,000+ Languages." arXiv. (MMS)

### Few-Shot and Zero-Shot Learning
- Snell, J., Swersky, K. & Zemel, R. (2017). "Prototypical Networks for Few-Shot Learning." *NeurIPS*.
- Vinyals, O. et al. (2016). "Matching Networks for One Shot Learning." *NeurIPS*.
- Finn, C., Abbeel, P. & Levine, S. (2017). "Model-Agnostic Meta-Learning." *ICML*. (MAML)
- Radford, A. et al. (2021). "Learning Transferable Visual Models From Natural Language Supervision." *ICML*. (CLIP)
- Lampert, C.H. et al. (2009). "Learning to Detect Unseen Object Classes by Between-Class Attribute Transfer." *CVPR*.
- Triantafillou, E. et al. (2020). "Meta-Dataset: A Dataset of Datasets." *ICLR*.
- Zhai, X. et al. (2023). "Sigmoid Loss for Language Image Pre-Training." *ICCV*. (SigLIP)

### Point Cloud and LiDAR Deep Learning
- Qi, C.R. et al. (2017). "PointNet: Deep Learning on Point Sets." *CVPR*.
- Qi, C.R. et al. (2017). "PointNet++: Deep Hierarchical Feature Learning on Point Sets." *NeurIPS*.
- Choy, C. et al. (2019). "4D Spatio-Temporal ConvNets: Minkowski Convolutional Neural Networks." *CVPR*. (MinkowskiNet)
- Zhao, H. et al. (2021). "Point Transformer." *ICCV*.
- Wu, X. et al. (2024). "Point Transformer V3: Simpler, Faster, Stronger." *CVPR*.
- Shi, S. et al. (2020). "PV-RCNN: Point-Voxel Feature Set Abstraction for 3D Object Detection." *CVPR*.
- Qi, C.R. et al. (2019). "Deep Hough Voting for 3D Object Detection." *ICCV*. (VoteNet)
- Pang, Y. et al. (2022). "Masked Autoencoders for Point Cloud Self-Supervised Learning." *ECCV*. (Point-MAE)

### Other Key References
- Shannon, C. (1948). "A Mathematical Theory of Communication." *Bell System Technical Journal*.
- Lewis, P. et al. (2020). "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks." *NeurIPS*. (RAG)
- Ilharco, G. et al. (2022). "Editing Models with Task Arithmetic." *ICLR 2023*.
- Bommasani, R. et al. (2021). "On the Opportunities and Risks of Foundation Models." arXiv.

## Textbooks and Surveys

- Goodfellow, I., Bengio, Y. & Courville, A. (2016). *Deep Learning*. MIT Press. https://www.deeplearningbook.org
- Bishop, C. & Bishop, H. (2024). *Deep Learning: Foundations and Concepts*. Springer.
- Prince, S. (2023). *Understanding Deep Learning*. MIT Press. https://udlbook.github.io/udlbook/
- Paszke, A. et al. (2019). "PyTorch: An Imperative Style, High-Performance Deep Learning Library." *NeurIPS*.

## Frameworks and Tools

- **PyTorch**: https://pytorch.org — dominant research framework
- **TensorFlow/Keras**: https://www.tensorflow.org — Google's framework, strong in production
- **JAX**: https://github.com/google/jax — functional transformations on NumPy code
- **llama.cpp**: https://github.com/ggerganov/llama.cpp — CPU/GPU inference for quantized LLMs
- **Hugging Face**: https://huggingface.co — model hub and libraries (Transformers, Diffusers, Datasets)
- **vLLM**: https://github.com/vllm-project/vllm — high-throughput LLM serving with PagedAttention
- **DeepSpeed**: https://github.com/microsoft/DeepSpeed — distributed training with ZeRO optimizer
- **Megatron-LM**: https://github.com/NVIDIA/Megatron-LM — model parallelism for large-scale training
