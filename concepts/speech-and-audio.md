# Speech and Audio

> Deep learning for processing and generating sound — from speech recognition (Whisper) and text-to-speech (VALL-E) to music generation (MusicLM) — built on spectral representations, neural audio codecs, and autoregressive/diffusion generation.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[multimodal-models]] — speech models increasingly embedded in multimodal architectures (GPT-4o, Gemini, Moshi)
- [[attention-and-transformers]] — Whisper, VALL-E, and MusicGen all use Transformer architectures
- [[autoregressive-models]] — WaveNet, VALL-E, AudioLM, MusicGen all generate autoregressively
- [[self-supervised-learning]] — wav2vec 2.0 pre-trains on unlabeled audio; HuBERT uses masked prediction for speech
- [[diffusion-models]] — Stable Audio and Voicebox use diffusion/flow-matching for audio generation
- [[generative-adversarial-networks]] — HiFi-GAN uses adversarial training for vocoding; VITS combines VAE + GAN
- [[autoencoders]] — neural codecs (SoundStream, EnCodec) are specialized autoencoders with VQ; TTS pipelines use VAE-like latent spaces
- [[convolutional-neural-networks]] — codec encoders/decoders are CNNs; WaveNet uses dilated causal convolutions
