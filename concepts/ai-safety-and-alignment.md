# AI Safety and Alignment

> Ensuring that AI systems behave as intended and remain aligned with human values — covering RLHF failure modes, reward hacking, Goodhart's law in ML, constitutional AI, red teaming, and the fundamental challenge of specifying what we actually want.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[reinforcement-learning]] — RLHF uses PPO to optimize against a reward model; DPO reformulates this as supervised learning; RL alignment methods inherit RL's stability challenges
- [[training-techniques]] — RLHF, DPO, and CAI are all fine-tuning methods; LoRA makes alignment fine-tuning more efficient; the SFT→RLHF pipeline is a standard training recipe
- [[large-language-models]] — alignment is primarily an LLM problem today; in-context learning means alignment must hold across arbitrary prompts and contexts
- [[interpretability]] — mechanistic interpretability aims to provide safety guarantees; representation engineering offers new steering methods; understanding model internals is prerequisite for verified alignment
- [[agents-and-tool-use]] — agent systems amplify alignment failures (an unaligned agent can take real-world actions); tool use means mistakes have consequences beyond text generation
- [[scaling-laws]] — does alignment difficulty scale with capability? Weak-to-strong generalization explores this; the alignment tax may change with scale
- [[knowledge-distillation]] — distilling aligned models may lose alignment properties; RLHF'd teachers may not produce RLHF'd students automatically
- [[information-theory]] — reward model capacity limits how much preference information can be captured; the information bottleneck may explain why reward hacking occurs (the reward model compresses preference information lossily)
