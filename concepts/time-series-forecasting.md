# Time Series Forecasting

> Deep learning for temporal prediction — from RNN/LSTM baselines through Transformer-based models (Informer, PatchTST), foundation models for time series (TimesFM, Chronos, Moirai), anomaly detection, and the debate over whether deep learning consistently beats classical methods.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[recurrent-neural-networks]] — LSTMs were the first DL architecture for time series; DeepAR (LSTM-based) remains widely deployed; RNN limitations (sequential processing, gradient issues) motivated Transformer adoption
- [[attention-and-transformers]] — Transformer-based forecasting (Informer, PatchTST, iTransformer) adapts attention for temporal data; patching mirrors ViT's image-to-token approach
- [[autoregressive-models]] — DeepAR and Chronos use autoregressive generation for probabilistic forecasting; the same next-token paradigm that powers LLMs
- [[self-supervised-learning]] — PatchTST uses masked patch prediction (like MAE); foundation models pre-train on unlabeled time series via next-value prediction
- [[large-language-models]] — Chronos treats time series as a language modeling problem (discretize values → tokens → Transformer); LLMs are being directly applied to time series (PromptCast, LLMTime)
- [[scaling-laws]] — do foundation model scaling laws hold for time series? Early evidence suggests yes, but the data landscape differs dramatically from text
- [[autoencoders]] — VAE-based anomaly detection and reconstruction-based methods use the latent space to define "normality"
- [[bayesian-deep-learning]] — probabilistic forecasting naturally connects to Bayesian uncertainty; calibrated prediction intervals are essential for decision-making
