---
created: 2026-10-08
newsletter: weekly
tags: [moc, tts, text-to-speech, voice, open-source, local-models, voice-cloning]
---

# MOC: Which Open-Source TTS (Voice) Model to Use

Map of Content for picking a local, open-weights text-to-speech model as of October 2026. The short answer is a table, sorted by model size. For the long list, see the appendix.

## Quick picks

★ marks the pick for each size. Each name links to the model's official page, and the Weights column links to where you download it.

| Size | Model | Weights | Notes |
|---|---|---|---|
| ≤ ~120M (CPU / edge) | ★ [Chatterbox-Nano](https://www.resemble.ai/learn/models/chatterbox-nano) (Resemble AI) | [HF](https://huggingface.co/ResembleAI/chatterbox-nano) | 110M, MIT. ~3× real-time on 8 CPU cores, voice cloning, tags such as `[laugh]`. |
| | [Kokoro](https://github.com/hexgrad/kokoro) | [HF](https://huggingface.co/hexgrad/Kokoro-82M) | 82M, Apache 2.0. Very fast and very popular. |
| | [Supertonic 3](https://github.com/supertone-inc/supertonic) (Supertone) | [HF](https://huggingface.co/Supertone/supertonic-3) | 99M. The repo was archived in July 2026 and gets no further updates. |
| ~120M–800M | ★ [Qwen3-TTS](https://github.com/QwenLM/Qwen3-TTS) (Alibaba Qwen) | [HF](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice) | 0.6B (1.7B also available), Apache 2.0. Preset voices, voice design and cloning. |
| | [Chatterbox](https://www.resemble.ai/chatterbox/) (Resemble AI) | [GitHub](https://github.com/resemble-ai/chatterbox) | MIT. Emotion control and cloning. |
| | [Gepard](https://nineninesix.ai) (nineninesix.ai) | [HF](https://huggingface.co/nineninesix/gepard-1.0) | ~0.5B, Apache 2.0. Use it if you need streaming: it's built for real-time voice agents, with first audio in ~50 ms. |
| | [OmniVoice](https://github.com/k2-fsa/OmniVoice) (k2-fsa / Xiaomi) | [HF](https://huggingface.co/k2-fsa/OmniVoice) | Use it if you need more languages (600+). It tops the tts-bench cloning votes but can drop words. |
| ~2B | ★ [VoxCPM2](https://github.com/OpenBMB/VoxCPM) (OpenBMB) | [HF](https://huggingface.co/openbmb/VoxCPM2) | 2B, Apache 2.0, 30 languages, 48 kHz output. Can design a voice from a text description. |
| Largest / best quality | ★ [Fish Audio S2 Pro](https://fish.audio/s2/) | [HF](https://huggingface.co/fishaudio/s2-pro) | The [Fish Audio Research License](https://huggingface.co/fishaudio/s2-pro/blob/main/LICENSE.md) only allows research and non-commercial use. Commercial use needs a separate licence. |
| Not recommended | [Higgs TTS 3](https://www.boson.ai/blog/higgs-tts-3) (Boson AI) | [HF](https://huggingface.co/bosonai/higgs-tts-3-4b) | 4B, research/non-commercial licence. |

Older models such as **Bark** and **XTTS** are no longer the standard.

## The recommendation behind the table

The table is built on a comment from a self-described TTS specialist in r/LocalLLM, [What is the best open-source TTS model right now?](https://www.reddit.com/r/LocalLLM/comments/1uh2xyh/what_is_the_best_opensource_tts_model_right_now/) (posted around July 2026). The comment is tidied here. Links and licence notes were added from the model cards.

> I've trained and fine-tuned TTS models for a while and tested every major one.
>
> - **~120M and below:** Chatterbox-Nano, Kokoro, Supertonic. Chatterbox-Nano is the one to go for.
> - **~120M to 800M:** Qwen3-TTS-0.6B, Chatterbox, Gepard (if you need streaming). If I had to pick one, Qwen3-TTS, or OmniVoice for more languages.
> - **Above that:** VoxCPM2 (~2B) if you want something smaller. If larger, Fish Audio S2 Pro. (I wouldn't recommend Higgs Audio TTS 3.)
>
> The gold standard has moved far beyond older models like Bark and XTTS. Lots of people recommend Kokoro, and it's an amazing model, but Chatterbox-Nano outclasses it on basically everything.

This is one practitioner's view, not a benchmark. To hear the models yourself, use the tts-bench listening pages and blind A/B arena below.

## Appendix: tts-bench

![tts-bench](https://screenshotit.app/https://github.com/5uck1ess/tts-bench)

[tts-bench](https://github.com/5uck1ess/tts-bench) (MIT) benchmarks **75 local TTS models** on Windows, Linux and macOS. It measures speed (time to first audio, real-time factor and memory, on CPU, CUDA and Apple Silicon). It also scores each model on naturalness (UTMOS), intelligibility (WER) and speaker similarity (SIM), and you can listen to every model on every prompt. A blind A/B arena ranks models by human votes. All models get the same plain prompts, so expressive controls such as emotion tags are not tested.

It is very thorough and also overwhelming, so use it to check a shortlist rather than to choose from scratch. Snapshot as of 2026-10-08:

**Fastest (June 2026 results)**

| Category | Rig | Model | Warm TTFA | RTFx |
|---|---|---|---|---|
| Fastest CPU | Ryzen 9 9950X3D | Piper | 107 ms | 59× |
| Fastest CUDA | RTX 5090 | Kokoro | 67 ms | 104× |
| Fastest Apple Silicon | M4, 16 GB | Piper | 208 ms | 32× |

**Best voice cloning (blind A/B preference)**

| Rank | Model | W-L-T | Note |
|---|---|---|---|
| 1 | [OmniVoice](https://huggingface.co/k2-fsa/OmniVoice) | 24-1-3 | Best voice match, but can garble or drop words |
| 2 | Echo-TTS | 21-1-6 | Clean 44.1 kHz output |
| 3 | IndexTTS-2 | 16-2-5 | Keeps accents well |

The [full table](https://github.com/5uck1ess/tts-bench) lists 26 models with built-in voices and 37 zero-shot cloning models, each with size, release date and licence.
