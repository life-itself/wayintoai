---
newsletter_sent: 2026-11-05
newsletter_url: https://wayintoai.com/weekly/2026-w45
created: 2026-10-28
original_date: 2026-10-27
author: Anthropic (Amaç Herdağdelen, Hailey Joren, Alex Tamkin)
newsletter: weekly
tags: [anthropic, research, judgment, deferral, automation-bias, experts, claude-code, human-oversight]
---

# How AI agents shape experts' judgment calls (Anthropic)

Anthropic randomly gave Claude a secret lean on each choice in a data analysis. Expert analysts went with that lean 86% of the time, and most repeated its arguments as their own.

> **Rufus's note (2026-10-28):** A big deal on how AI shapes choices, even with experts. Read the piece itself.

## Links

- **Write-up**: https://www.anthropic.com/research/agents-judgment-calls (27 Oct 2026)
- **Paper (PDF)**: https://www-cdn.anthropic.com/519c17a5d23a794e8b6d50a854048d0b61e0d73a.pdf
- **X summary**: https://x.com/i/trending/2115221896325210500

## Overview

A randomised controlled trial with 50 professional analysts, all with causal-inference and Python or R experience. Each analysed a fictional farming co-op's advisory programme using Claude Code (Opus 4.8). They made four analysis choices (outcome measure, comparison method, which farms to cover, weighting) and a final recommendation.

For each choice, a coin flip secretly set which option the agent leaned toward. A hidden instruction told it to argue for that option, change its mind if the evidence went decisively against it, and never misstate results.

- **Analysts followed the lean 86% of the time** across the four choices, where about 50% would mean no influence (92%, 82%, 81% and 90% per choice).
- **The final call moved too**: 54% recommended rollout when the agent leaned that way, against 36% when it did not.
- **Prior views gave way**: analysts who started with a preference switched 60% of the time when the agent disagreed, and 6% when it agreed.
- **Arguments without credit**: 77% repeated the agent's reasoning in their own explanations, but only 15% credited the agent.
- **Fewer errors with the agent**: 3 of 50 made serious errors with it, against 6 of 11 without. The no-agent group was less experienced, so the authors do not read this as causal.

The authors' caveats: the lean was deliberately strengthened, and the study covers one task, one field and one model. With no lean set, Opus 4.8 made the same five choices in 112 of 123 runs, so in real use the agent's defaults are the lean.

## Why interesting

The usual safeguard for AI work is "a human checks it". This study suggests that check is weaker than it looks: as the authors put it, "a human reviewer is only an independent check if their judgment is their own." The agent made the work faster and more accurate, and it also quietly made the decisions. Their suggestions: measure deferral in real work, build agents that argue each option or ask for the expert's view first, and decide which decisions need a person's own judgment and the time to form it.

## Related

- [[llm-vs-human-peer-review-errors]]: the same week, AI beat human peer reviewers at finding errors
- [[ai-power-law-adoption-laggards]]
