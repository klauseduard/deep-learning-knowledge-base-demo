# Training Techniques

> Practical methods for training and adapting deep learning models — from data augmentation and learning rate schedules to RLHF alignment and parameter-efficient fine-tuning with LoRA.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[gradient-descent]] — The underlying optimization algorithm; learning rate schedules and batch sizes directly modulate how gradient descent behaves.
- [[large-language-models]] — LLMs are trained using the full pipeline described here: pre-training, SFT, RLHF/DPO.
- [[scaling-laws]] — Scaling laws determine the optimal allocation of compute across training techniques.
- [[regularization]] — Weight decay, dropout, and data augmentation are all forms of regularization applied during training.
- [[autoregressive-models]] — The pre-training objective for GPT-style models, which training techniques are designed to optimize.
- [[loss-functions]] — Cross-entropy, reward model loss, DPO loss, and contrastive losses are all central to the training pipeline.
