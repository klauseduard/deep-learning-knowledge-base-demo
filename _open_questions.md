# Deep Learning — Open Questions and Gaps

Areas not yet covered, questions worth exploring deeper, and directions for future knowledge base expansion.

## Missing Topics (Not Yet Covered)

### Architectures
- ~~**Graph Neural Networks (GNNs)**~~ **ADDED** — see [[graph-neural-networks]]

### Training and Optimization
- ~~**Knowledge distillation**~~ **ADDED** — see [[knowledge-distillation]]
- ~~**Federated learning**~~ **ADDED** — see [[federated-learning]]
- ~~**Neural architecture search (NAS)**~~ **ADDED** — see [[neural-architecture-search]]
- ~~**Curriculum learning**~~ **ADDED** — see [[curriculum-learning]]
- ~~**Meta-learning / few-shot learning**~~ **ADDED** — see [[meta-learning]]

### Theory
- ~~**Generalization theory / double descent / grokking**~~ **ADDED** — see [[generalization-theory]]
- ~~**Loss landscape geometry**~~ **ADDED** — see [[loss-landscape-geometry]]
- ~~**Information theory in deep learning**~~ **ADDED** — see [[information-theory]]

### Applications
- ~~**Object detection**~~ **ADDED** — see [[object-detection]]
- ~~**Speech and audio**~~ **ADDED** — see [[speech-and-audio]]
- ~~**Multimodal models**~~ **ADDED** — see [[multimodal-models]]
- ~~**AI agents and tool use**~~ **ADDED** — see [[agents-and-tool-use]]
- ~~**Semantic segmentation**~~ **ADDED** — see [[semantic-segmentation]]
- ~~**3D vision and neural rendering**~~ **ADDED** — see [[3d-vision-and-neural-rendering]]
- ~~**Video understanding and generation**~~ **ADDED** — see [[video-understanding-and-generation]]

### Practical Engineering
- ~~**GPU/TPU hardware**~~ **ADDED** — see [[gpu-and-accelerator-hardware]]
- ~~**Model deployment**~~ **ADDED** — see [[model-deployment]]
- ~~**Data engineering for ML**~~ **ADDED** — see [[data-engineering]]

## Cross-Cutting Questions

### Theoretical Foundations
- Is there a unified theory connecting loss landscape geometry, SGD dynamics, and generalization?
- What are the computational limits of Transformers? Are they Turing-complete in practice?
- Can we prove that depth is strictly more efficient than width for specific function classes?

### Scaling and Emergence
- Are emergent abilities real or artifacts of evaluation metrics? (Schaeffer et al., 2023 vs. Wei et al., 2022)
- What are the scaling laws for capabilities beyond next-token prediction (reasoning, planning, tool use)?
- Is there a ceiling to scaling — when will power-law improvements plateau?
- How do scaling laws change for multimodal models and SSMs?

### Architecture Design
- Will Transformers remain dominant, or will SSM-Transformer hybrids take over?
- Is there a principled way to choose architecture components rather than empirical trial?
- Can NAS discover qualitatively new architectural primitives, or only optimize within human-defined search spaces?
- What is the optimal ratio of SSM to attention layers in hybrid architectures?

### Alignment and Safety
- How reliable is RLHF? What failure modes does it have?
- Can we verify that aligned models remain aligned after fine-tuning?
- What is the relationship between model capability and alignment difficulty?
- Can mechanistic interpretability provide safety guarantees?

### Agents and Tool Use
- Can LLM agents achieve 99%+ reliability for autonomous deployment, or is human-in-the-loop supervision fundamentally required?
- Is prompt injection via tool results (adversarial web pages, documents) a solvable problem, or an inherent vulnerability?
- What are the scaling laws for test-time compute (reasoning tokens, agent loops)? Do they follow power laws like training compute?
- When is a multi-agent architecture better than a single agent with good tools? Is there a principled way to decide?

### Privacy and Data Constraints
- Can federated learning match the accuracy of centralized training, or is there a fundamental "price of privacy"?
- Is differential privacy compatible with high-quality models for sensitive domains (healthcare, finance)?
- How should federated learning scale to foundation model fine-tuning?

### Continual Learning and Adaptation
- Is catastrophic forgetting a fundamental problem, or will it be solved by scale (larger models forget less)?
- Can continual pre-training keep LLMs up-to-date without full retraining?
- What is the right balance between storing knowledge in parameters vs. external retrieval (RAG)?

### Representations and Retrieval
- Is dense retrieval (embedding-based) fundamentally better than sparse retrieval (BM25), or is hybrid always optimal?
- Can a single embedding model handle all retrieval tasks, or do specialized models always outperform?
- How should embeddings represent negation and compositional semantics?

### Optimization Landscape
- Is there an optimizer that strictly dominates AdamW for Transformers?
- Can learning rate schedules be derived analytically rather than chosen empirically?
- Why does SGD generalize better than Adam on some vision tasks?

## Suggested Next Research Tasks

1. ~~**Add AI safety and alignment article**~~ **ADDED** — see [[ai-safety-and-alignment]]
2. ~~**Add embeddings and representation learning article**~~ **ADDED** — see [[embeddings-and-representation-learning]]
3. ~~**Add normalization techniques article**~~ **ADDED** — see [[normalization-techniques]]
4. ~~**Add optimization beyond SGD article**~~ **ADDED** — see [[optimization-beyond-sgd]]
5. ~~**Add text-to-image generation article**~~ **ADDED** — see [[text-to-image-generation]]

6. ~~**Add positional encoding article**~~ **ADDED** — see [[positional-encoding]]
7. ~~**Add quantization deep-dive article**~~ **ADDED** — see [[quantization]]
8. ~~**Add prompt engineering and in-context learning article**~~ **ADDED** — see [[prompt-engineering-and-in-context-learning]]
9. ~~**Add Bayesian deep learning article**~~ **ADDED** — see [[bayesian-deep-learning]]
10. ~~**Add image classification milestones article**~~ **ADDED** — see [[image-classification-milestones]]

11. ~~**Add tokenization article**~~ **ADDED** — see [[tokenization]]
12. ~~**Add transfer learning article**~~ **ADDED** — see [[transfer-learning]]
13. ~~**Add adversarial robustness article**~~ **ADDED** — see [[adversarial-robustness]]
14. ~~**Add neural ODE and continuous models article**~~ **ADDED** — see [[neural-odes-and-continuous-models]]
15. ~~**Add efficient attention variants article**~~ **ADDED** — see [[efficient-attention-variants]]

16. ~~**Add data augmentation article**~~ **ADDED** — see [[data-augmentation]]
17. ~~**Add world models and predictive learning article**~~ **ADDED** — see [[world-models-and-predictive-learning]]
18. ~~**Add reasoning in LLMs article**~~ **ADDED** — see [[reasoning-in-llms]]
19. ~~**Add model merging and editing article**~~ **ADDED** — see [[model-merging-and-editing]]
20. ~~**Add test-time adaptation article**~~ **ADDED** — see [[test-time-adaptation]]

21. ~~**Add synthetic data generation article**~~ **ADDED** — see [[synthetic-data-generation]]
22. ~~**Add neural network compression article**~~ **ADDED** — see [[neural-network-compression]]
23. ~~**Add reward modeling and RLHF deep-dive article**~~ **ADDED** — see [[reward-modeling-and-rlhf]]
24. ~~**Add retrieval-augmented generation (RAG) article**~~ **ADDED** — see [[retrieval-augmented-generation]]
25. ~~**Add long-context and memory architectures article**~~ **ADDED** — see [[long-context-and-memory-architectures]]

26. ~~**Add mechanistic interpretability deep-dive article**~~ **ADDED** — see [[mechanistic-interpretability]]
27. ~~**Add language model pre-training article**~~ **ADDED** — see [[language-model-pretraining]]
28. ~~**Add optimization theory for deep learning article**~~ **ADDED** — see [[optimization-theory-for-deep-learning]]
29. ~~**Add autonomous driving perception article**~~ **ADDED** — see [[autonomous-driving-perception]]
30. ~~**Add protein and molecular deep learning article**~~ **ADDED** — see [[protein-and-molecular-deep-learning]]

31. ~~**Add medical imaging deep learning article**~~ **ADDED** — see [[medical-imaging]]
32. ~~**Add natural language processing tasks article**~~ **ADDED** — see [[nlp-tasks]]
33. ~~**Add energy-based models and contrastive learning theory article**~~ **ADDED** — see [[energy-based-models-and-contrastive-learning]]
34. ~~**Add neural network initialization article**~~ **ADDED** — see [[neural-network-initialization]]
35. ~~**Add robotics and embodied AI article**~~ **ADDED** — see [[robotics-and-embodied-ai]]

36. ~~**Add time series forecasting article**~~ **ADDED** — see [[time-series-forecasting]]
37. ~~**Add recommender systems article**~~ **ADDED** — see [[recommender-systems]]
38. ~~**Add deep learning for audio generation article**~~ **ADDED** — see [[audio-generation]]
39. ~~**Add fairness and bias in deep learning article**~~ **ADDED** — see [[fairness-and-bias]]
40. ~~**Add hardware-software co-design article**~~ **ADDED** — see [[hardware-software-co-design]]

41. ~~**Add neural radiance field and 3D generation deep-dive**~~ **ADDED** — see [[3d-generation-deep-dive]]
42. ~~**Add multi-task and instruction tuning article**~~ **ADDED** — see [[instruction-tuning-and-multi-task-learning]]
43. ~~**Add causal inference and deep learning article**~~ **ADDED** — see [[causal-inference-and-deep-learning]]
44. ~~**Add model evaluation and benchmarking article**~~ **ADDED** — see [[evaluation-and-benchmarking]]
45. ~~**Add privacy-preserving ML article**~~ **ADDED** — see [[privacy-preserving-ml]]

46. ~~**Add hyperparameter optimization article**~~ **ADDED** — see [[hyperparameter-optimization]]
47. ~~**Add knowledge graphs and structured knowledge article**~~ **ADDED** — see [[knowledge-graphs-and-structured-knowledge]]
48. ~~**Add speech recognition deep-dive article**~~ **ADDED** — see [[speech-recognition-deep-dive]]
49. ~~**Add few-shot and zero-shot learning article**~~ **ADDED** — see [[few-shot-and-zero-shot-learning]]
50. ~~**Add point cloud and LiDAR deep learning article**~~ **ADDED** — see [[point-cloud-and-lidar-deep-learning]]

### Next Suggested Topics

1. **Add optical flow and video motion estimation article** — FlowNet, RAFT, scene flow, motion segmentation, self-supervised flow — connects [[video-understanding-and-generation]] and [[convolutional-neural-networks]]
2. **Add depth estimation article** — monocular depth (MiDaS, Depth Anything), stereo matching, self-supervised depth, metric vs. relative depth — connects [[3d-vision-and-neural-rendering]] and [[autonomous-driving-perception]]
3. **Add multi-agent systems and LLM orchestration article** — multi-agent debate, hierarchical agents, communication protocols, tool orchestration — connects [[agents-and-tool-use]] and [[reasoning-in-llms]]
4. **Add document understanding and OCR article** — LayoutLM, Donut, document parsing, table extraction, visual question answering on documents — connects [[multimodal-models]] and [[nlp-tasks]]
5. **Add neural network debugging and training diagnostics article** — gradient monitoring, loss curves, learning rate finders, mode connectivity probing, training instabilities — connects [[training-techniques]] and [[loss-landscape-geometry]]
