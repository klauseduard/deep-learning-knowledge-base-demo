# Test-Time Adaptation

> Adapting models during inference to handle distribution shifts — from entropy minimization (TENT) to test-time training with self-supervised objectives (TTT) and TTT layers that replace attention with learned adaptation mechanisms.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[transfer-learning]] — TTA is the extreme of adaptation: adapting to the specific test distribution rather than a target training set; PEFT methods (LoRA, adapters) are training-time transfer while TTA is inference-time transfer
- [[continual-learning]] — long-term TTA faces the same catastrophic forgetting challenges; CoTTA uses parameter restoration (analogous to EWC) to prevent drift
- [[self-supervised-learning]] — TTT's auxiliary self-supervised objective at test time directly reuses SSL machinery; the quality of the SSL task determines TTA effectiveness
- [[normalization-techniques]] — BN adaptation is the simplest TTA; TENT updates only normalization parameters; the interaction between normalization and distribution shift is fundamental
- [[state-space-models]] — TTT layers are proposed as an alternative to both attention and SSMs for sequence modeling, with gradient-based state updates instead of linear recurrence
- [[attention-and-transformers]] — attention can be viewed as a form of test-time adaptation (data-dependent output); TTT layers make this analogy literal
- [[loss-landscape-geometry]] — SAR applies sharpness-aware minimization during TTA; flat minima are more stable under adaptation
- [[adversarial-robustness]] — TTA can improve robustness to natural distribution shifts but may be vulnerable to adversarial manipulation (an attacker could craft inputs that cause harmful adaptation)
