---
created: 2026-10-09
tags: [ai, mathematics, open-problems, rankings, lean, multi-agent, research-platform]
---

# ProofAtlas

An AI-first maths research platform whose best-known feature is a ranked list of the top 500 open problems in mathematics. Each problem has an exact statement, sources and a dated status note.

![ProofAtlas: Top 500 open math problems](https://screenshotit.app/https://www.proofatlas.ai/open-problems/)

## Links

- **Top 500 by importance**: https://www.proofatlas.ai/open-problems/
- **Top 100 by fame**: https://www.proofatlas.ai/open-problems/famous/
- **Home (collaboration platform)**: https://www.proofatlas.ai/

## Overview

The ranking is made by having LLMs from OpenAI, Claude, GLM and DeepSeek compare pairs of problems. A reliability-weighted model then combines those judgments. ProofAtlas says this is "a model-based assessment of mathematical importance, not an expert consensus." P vs NP ranks #1, the Riemann hypothesis #2 and the Hodge conjecture #4.

The useful part is the status notes, which track AI resolution claims and say what they actually cover. For example:
- **Riemann hypothesis:** after the [[openai-math-results-release]], the note on RH says a zero-free half-plane Re(s) > 7/8 is "partial zero-location progress, not the Riemann Hypothesis."
- **Navier–Stokes:** the note says OpenAI's [[openai-navier-stokes-millennium-proof|September claim]] covers a different variant of the problem (a forced alternative) from the one in the ranked entry.

Problems that get resolved stay on the list with their original rank.

ProofAtlas is also a platform where AI agents work on these problems together, recording proof routes, useful failures and Lean-checked results. It reports 268 workspaces and about 770k "investigation lines." Its claimed outcomes, mostly credited to Lech Mazur, include Lean-checked Collatz density bounds and a counterexample to Jackson's Hamilton-decomposition conjecture.

## Related

- [[ai-and-mathematics]]
- [[openai-math-results-release]]
- [[openai-navier-stokes-millennium-proof]]
