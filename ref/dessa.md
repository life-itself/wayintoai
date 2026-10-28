---
created: 2026-10-28
author: Block
tags: [voice, speech-to-speech, full-duplex, audio-model, block, local-ai, apple-silicon, ai-safety, scams]
---

# Dessa: Block's conversation model trained only on speech

Block's AI research lab trained a speech-to-speech model from scratch on recorded human conversation, with no text at all. It is full-duplex: it listens and talks at the same time, with overlaps, laughter and "yeah" backchannels. The samples sound very human.

![Dessa – the conversation model trained only on speech](https://screenshotit.app/https://block.xyz/dessa)

## Links

- **Page with audio samples**: https://block.xyz/dessa (released c. 24 Oct 2026)
- **More recordings**: [Ragavan Thurairatnam on X](https://x.com/RagavanThurair)
- **Discussion**: [X trending summary](https://x.com/i/trending/2113698647234015512)

## Overview

Most voice assistants convert speech to text, run a language model, then convert back. Dessa skips text entirely and learns turn-taking and tone straight from audio. That is why it can interrupt and be interrupted naturally.

It was trained on a single NVIDIA GB200 NVL72 rack rather than a large cluster, and runs locally on a MacBook Pro M4 Max or better, faster than real time. It is as much a demo of what a small lab can now do as a product.

## Access

No weights, licence or paper yet ("launch links are coming soon"). There is a waitlist, and Block is giving a small group of AI safety researchers early access. The obvious worry raised on release: voice that convincing makes phone scams easier.

## See also

- [[moc-tts-voice-models]]: text-to-speech models (Dessa is speech-to-speech, so it is not listed there)
