# Reward Modeling and RLHF

> The mechanics of training reward models from human preferences and using them to align LLMs via reinforcement learning — PPO, GRPO, DPO, KTO, and the failure modes that arise from optimizing proxy rewards.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[ai-safety-and-alignment]] — RLHF is the primary alignment mechanism; this article provides the technical depth on reward modeling and optimization
- [[reinforcement-learning]] — PPO, GRPO, and policy optimization are RL algorithms; RLHF applies RL to language generation
- [[training-techniques]] — RLHF/DPO is the final stage of the standard LLM training pipeline (pre-train → SFT → RLHF)
- [[reasoning-in-llms]] — process reward models provide step-level rewards for training reasoning models; RL (GRPO) trains the reasoning process in o1/R1
- [[scaling-laws]] — reward model overoptimization follows scaling laws (Gao et al.); the KL budget determines how much optimization is beneficial
- [[synthetic-data-generation]] — RLAIF generates synthetic preference data; Constitutional AI generates self-critique data for alignment
- [[knowledge-distillation]] — aligned models can be distilled to smaller models; the alignment properties transfer through distillation (partially)
- [[loss-functions]] — the Bradley-Terry loss for reward models and the DPO loss are specific loss functions with information-theoretic interpretations
