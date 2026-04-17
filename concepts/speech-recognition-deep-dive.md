# Speech Recognition Deep Dive

> Automatic speech recognition (ASR) — from CTC and RNN-Transducer through self-supervised speech (wav2vec 2.0, HuBERT), Whisper's supervised scaling, streaming ASR, multilingual models, and the speech foundation model paradigm.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[speech-and-audio]] — this article deepens the ASR side; TTS, audio codecs, and music generation are covered there; ASR + TTS together enable speech-to-speech systems
- [[attention-and-transformers]] — Transformer encoder-decoders (Whisper, LAS) and Conformer (attention + convolution) are the dominant ASR architectures
- [[self-supervised-learning]] — wav2vec 2.0 and HuBERT learn speech representations from unlabeled audio; contrastive and masked prediction objectives parallel text SSL (BERT) and image SSL (MAE)
- [[audio-generation]] — ASR is the inverse of TTS; neural codecs (SoundStream, EnCodec) provide discrete audio tokens shared across ASR and generation; codec-based ASR is emerging
- [[data-augmentation]] — SpecAugment is the universal ASR augmentation; speed perturbation, noise injection, and room impulse response simulation are domain-specific techniques
- [[tokenization]] — ASR output tokenization (characters, BPE subwords, words) affects accuracy and vocabulary coverage; shared tokenizers with LLMs enable unified speech-text models
- [[multimodal-models]] — GPT-4o and Gemini process speech natively, unifying ASR with language understanding; Whisper-style encoders provide the audio input pathway for multimodal models
