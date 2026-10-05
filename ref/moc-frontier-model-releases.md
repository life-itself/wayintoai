---
created: 2026-09-23
tags: [moc, models, frontier-models, model-releases, timeline, benchmarks, anthropic, openai]
image: /assets/frontier-models-terminal-bench-2026-09.svg
newsletter_sent: 2026-10-05
newsletter_url: https://wayintoai.com/weekly/2026-w40
---

# MOC: Frontier Model Releases

This map covers major frontier model releases: when each shipped, where it is logged here, and how the frontier has moved on benchmarks that stay comparable across releases. The pace in 2026 is the story. Anthropic shipped four flagship-tier releases between June and September, and OpenAI went from GPT-5.6 Sol to GPT-6 Astra in eight weeks.

![Line charts of Terminal-Bench 4.0 and Terminal-Bench-Science 0.1 scores by release date, Jun–Sep 2026: Claude rises from Fable 5 to Opus 5.5; OpenAI from GPT-5.6 Sol to GPT-6 Astra](/assets/frontier-models-terminal-bench-2026-09.svg)

## Benchmark progress (Jun–Sep 2026)

Most benchmark rows change between announcements. GDPval-AA moved from v2 to v2.1, which changed the Elo scale. OSWorld 2.0 changed its task set, and AutomationBench's leaderboard re-scored older models. Only **Terminal-Bench 4.0** and **Terminal-Bench-Science 0.1** keep the same numbers across the Fable 5.1 and Opus 5.5 tables: Opus 5 reproduces at 52.3% and 29.0% in both. The chart uses only those two.

| Model | Released | Terminal-Bench 4.0 | Terminal-Bench-Science 0.1 |
|---|---|---|---|
| Claude Fable 5 | 2026-06-09 | 42.0% | 24.7% |
| GPT-5.6 Sol | 2026-07-09 | 37.3% | 22.4% |
| Claude Opus 5 | 2026-07-24 | 52.3% | 29.0% |
| Claude Fable 5.1 | 2026-09-01 | 55.8% | 52.6% |
| GPT-6 Astra | 2026-09-03 | 57.9% | 64.6% |
| Claude Opus 5.5 | 2026-09-22 | **66.4%** | 58.7% |

Scores: Fable 5 from the Fable 5.1 announcement;[^fable-5-1] all others from the Opus 5.5 announcement,[^opus-5-5] where the shared rows match.

Claude Mythos 5.1, which has restricted access, scores 60.9% on Terminal-Bench 4.0. The science benchmark shows the steepest change: Claude went from 29% to 53% in one release (Opus 5 → Fable 5.1), and Astra reached 65%. Anthropic now says benchmark margins at this level are "a less reliable guide to real-world differences", so read the chart for direction rather than decimals. Scores come from vendors; OpenAI figures are as reported by OpenAI.

## Timeline

### 2026

| Date | Model | Lab | Notes | Source |
|---|---|---|---|---|
| 2026-02-05 | Claude Opus 4.6 | Anthropic | 1M context in beta | [^claude-timeline] |
| 2026-02-17 | Claude Sonnet 4.6 | Anthropic | | [^claude-timeline] |
| 2026-03 | [[gpt-5-4]] | OpenAI | Native computer use, 1M context | [^gpt-5-4] |
| 2026-04 | [[gemma-4]] | Google DeepMind | Open models built from Gemini 3 research | [^gemma-4] |
| 2026-04-08 | [[meta-muse-spark-msl]] | Meta | Muse Spark, from Meta Superintelligence Labs | [^muse-spark] |
| 2026-04 | Claude Mythos Preview | Anthropic | Restricted; announced with [[anthropic-glasswing]] | [^glasswing] |
| 2026-04-16 | Claude Opus 4.7 | Anthropic | | [^claude-timeline] |
| 2026-04-23 | [[gpt-5-5]] | OpenAI | Agentic coding, computer use | [^gpt-5-5] |
| 2026-04 | [[deepseek-v4-preview]] | DeepSeek | Open-weights MoE, 1M context, very low API prices | [^deepseek-v4] |
| 2026-05-28 | Claude Opus 4.8 | Anthropic | Now the fallback model for Opus 5.5's cyber safeguards | [^claude-timeline] [^opus-5-5] |
| 2026-06-09 | Claude Fable 5 + Mythos 5 | Anthropic | Access revoked Jun 12 after a US government letter; see [[fable-5-oneshot-sakura]] | [^fable-5] [^mythos-wiki] |
| 2026-06-30 | Claude Sonnet 5 | Anthropic | $2 / $10 per M tokens | [^claude-timeline] |
| 2026-07-09 | GPT-5.6 (Luna / Terra / Sol) | OpenAI | Limited preview from Jun 26 | [^gpt-5-6] |
| 2026-07-24 | Claude Opus 5 | Anthropic | 1M context, adaptive thinking; see [[trq212-claude-5-context-engineering]] | [^claude-timeline] |
| 2026-09-01 | Claude Fable 5.1 + Mythos 5.1 | Anthropic | Most capable general release at the time | [^fable-5-1] |
| 2026-09-03 | [[gpt-6-astra]] | OpenAI | Saturates ARC-AGI-3; first "Critical" cyber rating | [^astra] [^astra-wiki] |
| 2026-09-22 | [[claude-opus-5-5]] | Anthropic | Fable 5.1-level for about 40% less than Opus 5; Sonnet/Haiku 5.5 "in the coming weeks" | [^opus-5-5] |

### 2024–2025 (Claude, for context)

All dates from the public Claude release timeline.[^claude-timeline]

| Date | Model |
|---|---|
| 2024-03-04 | Claude 3 (Haiku, Sonnet, Opus) |
| 2024-06-21 | Claude 3.5 Sonnet |
| 2024-10-22 | Claude 3.5 Haiku; upgraded 3.5 Sonnet (computer use) |
| 2025-02-24 | Claude 3.7 Sonnet (hybrid reasoning) |
| 2025-05-22 | Claude Opus 4 + Sonnet 4 |
| 2025-08-05 | Claude Opus 4.1 |
| 2025-09-29 | Claude Sonnet 4.5 |
| 2025-10-15 | Claude Haiku 4.5 |
| 2025-11-24 | Claude Opus 4.5 |

## Related

- [[2026-09-10-the-pace-is-the-story]]: OpenAI's internal model after Astra, and why pace matters
- [[pacing-the-frontier]]: the call to deliberately slow the frontier
- [[stephen-reid-coding-agents-benchmarks]]
- [[moc-ai-security-incidents]]

## Sources

Where a row links to a reference entry here, that entry holds the fuller write-up and links.

[^claude-timeline]: [anthropic-claude-timeline](https://github.com/jqueryscript/anthropic-claude-timeline): a community-maintained timeline of Claude model releases. It is a secondary source; check against Anthropic's announcements where it matters.
[^opus-5-5]: [Introducing Claude Opus 5.5](https://www.anthropic.com/claude-opus-5-5), Anthropic, 2026-09-22.
[^fable-5-1]: [Introducing Claude Fable 5.1 and Claude Mythos 5.1](https://www.anthropic.com/claude-fable-and-mythos-5-1), Anthropic.
[^fable-5]: [Introducing Claude Fable 5 and Claude Mythos 5](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5), Claude Platform docs.
[^mythos-wiki]: [Claude Mythos](https://en.wikipedia.org/wiki/Claude_Mythos), Wikipedia: covers the US government letter and the access revocation.
[^glasswing]: [Project Glasswing](https://www.anthropic.com/glasswing), Anthropic.
[^gpt-5-4]: [Introducing GPT-5.4](https://openai.com/index/introducing-gpt-5-4/), OpenAI.
[^gpt-5-5]: [Introducing GPT-5.5](https://openai.com/index/introducing-gpt-5-5/), OpenAI.
[^gpt-5-6]: [GPT-5.6](https://en.wikipedia.org/wiki/GPT-5.6), Wikipedia.
[^astra]: [GPT-6 Astra: A new generation of intelligence](https://openai.com/index/gpt-6-astra/), OpenAI.
[^astra-wiki]: [GPT-6 Astra](https://en.wikipedia.org/wiki/GPT-6_Astra), Wikipedia: gives the Sep 3 release to approved users and general availability the next day.
[^gemma-4]: [Gemma 4](https://deepmind.google/models/gemma/gemma-4/), Google DeepMind.
[^muse-spark]: [Introducing Muse Spark](https://ai.meta.com/blog/introducing-muse-spark-msl/), Meta.
[^deepseek-v4]: [DeepSeek V4 Preview release](https://api-docs.deepseek.com/news/news260424/), DeepSeek API docs.
