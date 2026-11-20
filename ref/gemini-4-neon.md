---
created: 2026-11-20
original_date: 2026-11-18
author: Koray Kavukcuoglu, Google DeepMind
featured: true
newsletter: weekly
tags: [google, gemini, models, frontier-models, model-releases, cybersecurity, pricing]
---

# Gemini 4 Neon

Google's middle-tier Gemini 4 model: near-frontier scores at lower cost than Carbon, and the lead model for coding agents. Vendor figures throughout; no independent check yet except the Artificial Analysis and Vals rankings Google cites.

## Links

- **Announcement**: [Introducing Gemini 4 Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/), Koray Kavukcuoglu, Google DeepMind, 18 Nov 2026
- **Model card**: [Gemini 4 Neon model card (PDF)](https://storage.googleapis.com/deepmind-media/Model-Cards/Gemini-4-Neon-Model-Card.pdf)

## Overview

- **Position**: the middle of the Gemini 4 line. [[gemini-4-carbon]] is for the hardest long-horizon work, [[gemini-4-hydrogen]] for fast everyday execution, Neon balances depth and efficiency. In Google Antigravity Neon can orchestrate parallel Hydrogen subagents.
- **Price**: $3 input / $15 output per million tokens, cached input 95% off, 1M-token context. Four thinking levels. At the default (high) it costs 32% less per task than Carbon, and Google claims 50–80% less than rival frontier models on Vals and Agent Arena.
- **Intelligence**: #3 on the Artificial Analysis Intelligence Index (61 at xhigh), just behind larger, slower models; #2 on the Vals Index (70.9%).
- **Coding and agents**: #1 on the Artificial Analysis Coding Agent Index (58.6), 65.2% on Terminal-Bench 4.1, 46.2% on FrontierCode 2.0. #1 on Zapier AutomationBench, Legal Research Bench and Tax Agent Bench.
- **Cyber**: state of the art on AutoBaxBench hard (76%) and WebExploitBench v1.2 (51.26%); SEC-bench Pro 90.5%; CWE-bench v2 70.7%. A cyber variant goes to trusted defenders through the Fairwind Program "in the coming days".
- **Safety (Google's figures)**: 0.0% indirect prompt-injection success on Gray Swan at the top thinking level; 0.09% misaligned-action rate; 99.2% on an agent honesty eval.

## How to get it

Rolling out from 18 Nov 2026.

- **Gemini app**: Google AI Pro or Ultra subscribers, from the model drop-down.
- **Google AI Studio and Gemini API**: paid tier for developers; Pro and Ultra subscribers can try it in AI Studio. Also Android Studio.
- **Google Antigravity**: paid Pro and Ultra subscribers.
- **Enterprise**: "Gemini for business" (Gemini Enterprise), via the API or model drop-down.
- **Not stated**: any Google Workspace plan inclusion, free-tier Gemini app access, regions, or Vertex AI. Hydrogen is included in Workspace (checked by Rufus); Neon is not (checked by Rufus, 2026-11-20); nor is Carbon.

## Why interesting

Third Gemini 4 release in five weeks. Google now has a full ladder (Hydrogen, Neon, Carbon) and is competing on cost per task as much as raw score, as with [[gpt-6-2-astra-sol]].

## Related

- [[moc-google-ai-releases]]
- [[moc-frontier-model-releases]]
- [[gemini-4-carbon]]
- [[gemini-4-hydrogen]]
