---
created: 2026-10-09
tags: [ai-models, system-one, open-source, agents, reward-models, contrastive-learning]
---

# Contrastive Language Models (CLM)

An open "System One" model that picks the best action from a list by matching embeddings, instead of generating text. Its makers report performance on par with [[typesafe-jev|Jev]] at up to 9× lower latency.

![Contrastive Language Models](https://screenshotit.app/https://contrastive-lm.notion.site/)

## Links

- **Project page**: https://contrastive-lm.notion.site/ (posted 23 Sep 2026)

## Overview

A CLM has two encoders: one embeds the current state and the other embeds each candidate action, both into the same space. At decision time it scores every candidate by how close its embedding is to the state's and picks the best match. Each encoder is a frozen LLM with a small (20M-parameter) trainable head, so training is cheap; one pre-training run takes about an hour on a single RTX 4090. Action embeddings can be cached, so when the action set is large or fixed the model is far faster than a generative model. The page reports a 13× speedup at around 1,000 candidates.

The released model is CLM-8B. The page reports it roughly matches Jev on computer-use, gaming and tool-calling tasks. Fine-tuned to judge which of several candidate solutions is best, it reports state-of-the-art scores on DeepSWE (81.6%) and Terminal-Bench 2.1 (87.6%), where they say Jev does worse than picking at random. They also report predictable scaling laws.

## Why interesting

CLM is an open alternative to the closed System One model idea that TypeSafe introduced with Jev: fast, cheap decision models that sit inside software alongside larger LLMs.

## Related

- [[typesafe-jev]]
