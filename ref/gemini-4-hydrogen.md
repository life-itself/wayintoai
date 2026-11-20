---
created: 2026-11-20
original_date: 2026-11-12
author: Koray Kavukcuoglu, Google DeepMind
tags: [google, gemini, models, model-releases, pricing]
---

# Gemini 4 Hydrogen

Google's fast, cheap Gemini 4 model, built for quick everyday execution or as the execution engine under Carbon and Argon. Vendor figures.

## Links

- **Announcement**: [Introducing Gemini 4 Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/), Koray Kavukcuoglu, Google DeepMind, 12 Nov 2026 (updated 16 Nov)

## Overview

- **Price**: $1.50 input / $7.50 output per million tokens, flat across the 1M-token context.
- **Benchmarks**: Artificial Analysis Intelligence Index 51 at high (Argon 50), 54 at the new xhigh setting; Terminal-Bench 4.1 57% against 18.2% for Gemini 3.8 Flash; Vals Tax Agent Bench #1 (52.3%). About 2.5x faster than 3.8 Flash.
- **Orchestrator**: Google Antigravity can switch between Carbon and Hydrogen in one session; near-Carbon task success with 24% less quota and 19% faster (vendor-reported).
- **Access**: Gemini app model drop-down for everyone (free users via auto model selection), Google Search for all users, Gemini API and AI Studio on all tiers, Antigravity for paid Pro and Ultra, Gemini in Sheets for Pro/Ultra and eligible business plans. Workspace inclusion is not stated.

## Related

- [[gemini-4-neon]]
- [[gemini-4-carbon]]
- [[moc-google-ai-releases]]
