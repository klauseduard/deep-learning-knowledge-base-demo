# Audio Generation

> Neural audio synthesis — WaveNet and autoregressive waveform generation, neural vocoders (HiFi-GAN, Vocos), codec language models (VALL-E, MusicGen), audio diffusion, and the convergence of speech, music, and sound effect generation into unified models.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[speech-and-audio]] — this article deepens the generation side of audio processing; ASR (Whisper, wav2vec) provides the complementary input understanding
- [[autoregressive-models]] — codec language models (VALL-E, MusicGen, AudioLM) apply autoregressive generation to audio tokens, directly paralleling text LLMs
- [[diffusion-models]] — audio diffusion (DiffWave, AudioLDM, Stable Audio) applies the diffusion paradigm to audio, operating on spectrograms or latent spaces
- [[generative-adversarial-networks]] — GAN-based vocoders (HiFi-GAN) remain the fastest high-quality waveform generators; adversarial training is central to codec training
- [[autoencoders]] — neural codecs (SoundStream, EnCodec) are VQ-VAEs applied to audio; the encoder-quantizer-decoder structure directly mirrors VQ-VAE
- [[tokenization]] — audio codecs are tokenizers for audio, converting continuous waveforms to discrete tokens that language models can process; RVQ is a hierarchical tokenization scheme
- [[large-language-models]] — the convergence of audio and text generation: models like AudioPaLM and Gemini process both text and audio tokens in a unified architecture
- [[multimodal-models]] — unified audio-text-image models (Gemini, GPT-4o) generate and understand audio alongside other modalities
