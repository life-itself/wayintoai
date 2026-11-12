---
newsletter_sent: 2026-11-12
newsletter_url: https://wayintoai.com/weekly/2026-w46
created: 2026-11-10
original_date: 2026-11-09
author: Anthropic
newsletter: weekly
tags: [models, anthropic, claude, fable, mythos, frontier-models, model-releases, benchmarks, pricing, cybersecurity, safeguards, major-news]
---

# Claude Fable 5.2 and Claude Mythos 5.2

Anthropic's new top tier, released 9 November 2026. Anthropic calls it "a step above Opus 5.5 in almost all the capabilities we evaluated". The largest gains are in long-running agentic work, such as remote-labour tasks, robotics simulation and coding, and in reading charts. It is priced at $8 / $40 per million tokens, and Opus 5.5 stays the recommended default.

![Introducing Claude Fable 5.2 and Claude Mythos 5.2](https://screenshotit.app/https://www.anthropic.com/claude-fable-and-mythos-5-2)

## Links

- **Announcement**: https://www.anthropic.com/claude-fable-and-mythos-5-2 (9 Nov 2026)
- **System card**: https://www.anthropic.com/document/claude-fable-5-2-mythos-5-2-system-card
- **Models overview**: https://platform.claude.com/docs/en/about-claude/models/overview
- **Model ID**: `claude-fable-5-2` (Bedrock: `anthropic.claude-fable-5-2`)
- Previous: [Claude Fable 5.1 and Mythos 5.1](https://www.anthropic.com/claude-fable-and-mythos-5-1) (1 Sep 2026); [[claude-opus-5-5]] (22 Sep 2026)
- Timeline: [[moc-frontier-model-releases]]

## Summary

Fable and Mythos are "the same underlying model". Fable is the general release, with classifiers that block high-risk cyber and most research-biology work. Mythos 5.2 drops those blocks for vetted organisations, through Anthropic's Cyber and Life Sciences Verification Programs. Claude Security, for Enterprise customers, now includes Mythos 5.2.

The jump over Fable 5.1, ten weeks earlier, is large on long agentic tasks. Remote Labor Index goes from 17.9% to 41.3%, RoboDojo Sim from 27.6% to 64.9%, and FrontierCode 2.0 from 32.4% to 49.1%. Against the rest of the field it leads most rows. Gemini 4 Carbon edges it on AutomationBench. On knowledge work it leads the AA-Briefcase rubric (66.1% against 61.2% for Opus 5.5) but trails Opus 5.5 slightly on the Elo rating.

A 1,000-agent Fable 5.2 team formalised Fermat's Last Theorem in 30 hours; Opus 5.5 got 26% of the way in 18 hours. Anthropic also says over 90% of the changes merged into its core codebase are now written by Claude, with human guidance.

## Price and specs

| | Fable 5.2 | Opus 5.5 | Sonnet 5.5 |
|---|---|---|---|
| Input / output (per M tokens) | $8 / $40 | $4 / $20 | $2 / $10 |
| Fast mode (up to 2.5× faster) | $16 / $80 | — | — |
| Context window | 1M | 1M | 1M |
| Max output | 128K | 128K | 128K |

*Source: Anthropic models overview, 10 Nov 2026. Opus 5.5 and Sonnet 5.5 also have 1M context and 128K output. Fable 5 and 5.1 were $10 / $50 ([Fable 5.1 announcement](https://www.anthropic.com/claude-fable-and-mythos-5-1)).*

- Cache reads are 2.5% of the input price; Batch API is 50% off.
- Adaptive thinking is always on. Default effort is `high` in the API and medium in the Claude apps and Claude Code.
- Knowledge cutoff: June 2026.
- Available on the Claude API, AWS, Google Cloud and Microsoft Foundry. As a launch promotion, Pro and Team standard seats can use Fable for up to 50% of weekly usage, plus one to three Fable resets.
- Output is up to 30% faster than Fable 5.1.

## Benchmarks

| Benchmark | Fable 5.2 | Fable 5.1 | Opus 5.5 | GPT-6 Astra | Gemini 4 Carbon |
|---|---|---|---|---|---|
| FrontierCode 2.0 (agentic coding) | **49.1%** | 32.4% | 45.5% | 42.8% | 41.1% |
| FrontierSWE v2 | **69.9%** | 56.3% | 62.3% | 65.5% | 61.2% |
| AutomationBench (business workflows) | 51.4% | 31.4% | 42.5% | 41.4% | **53.9%** |
| Terminal-Bench-Science 0.1 | **74.6%** | 52.6% | 58.7% | 68.1% | 64.8% |
| OSWorld 2.1 (computer use) | **89.3%** | 83.5% | 87.2% | 79.5% | 81.5% |
| RoboDojo Sim (robotics) | **64.9%** | 27.6% | 39.4% | 29.8% | — |
| AA-Briefcase v1.1 (knowledge work, Elo) | 1785 | 1669 | **1800** | 1569 | 1611 |
| Remote Labor Index | **41.3%** | 17.9% | 21.3% | 20.8% | — |
| Humanity's Last Exam (with tools) | **74.2%** | 65.6% | 67.7% | 57.2% | — |
| Chartography (no tools) | **73.4%** | 44.8% | 64.4% | 71.0% | 72.5% |
| WANDR (agentic search) | **82.1%** | 68.7% | 72.3% | — | — |

*Source: Anthropic announcement, 9 Nov 2026. Vendor figures, highest available effort, with safeguards on. Some cells are at different effort levels; see the announcement.*

Mythos 5.2 scores 75.3% on Terminal-Bench-Science. On cyber:

| Cyber benchmark | Mythos 5.2 | Mythos 5.1 | Opus 5.5 (no safeguards) |
|---|---|---|---|
| CyScenarioBench | **76.3%** | 61.7% | 67.6% |
| CVE Rediscovery | **89.6%** | 78.3% | 81.3% |

*Source: Anthropic, 9 Nov 2026.*

GPT-6 Astra's Terminal-Bench-Science score here (68.1%) differs from the 64.6% in the Opus 5.5 announcement; Anthropic does not explain the change. Benchmark versions differ from the Opus 5.5 announcement (for example FrontierCode 2.0 and OSWorld 2.1), so these numbers do not line up with the earlier tables.

Efficiency is part of the pitch. At high effort rather than max, Fable 5.2 matches Opus 5.5 on FrontierCode (45.3% vs 45.5%) for roughly half the cost per task.

## Safety and safeguards

- **Risk**: Anthropic assesses the risk of these models behaving unsafely in high-stakes situations as "low (as with our other recent models)".
- **Behavioural audit** (about 1,900 scenarios, lower is better): Mythos 5.2 scores 2.67, the best of recent models (Opus 5.5 2.79; Mythos 5.1 3.28).
- **Sandbox escape**: Mythos 5.2 used planted credentials or files in 3.1% of scenarios, about the same as Opus 5.5 (3.3%) and down from 39% for Mythos 5 and 21% for Mythos 5.1.
- **Evaluation awareness gets worse**: both models "voice suspicion that they are being evaluated more often than any of our recent models". This repeats the warning from [[claude-opus-5-5]].
- **Fewer false blocks**: about 55% fewer classifier blocks than Fable 5.1, with the same robustness. Blocked cyber requests fall back to Opus 4.8, and blocked biology requests to Opus 5. A small set of AI R&D topics, including kernel development on some nonstandard accelerators, also falls back to Opus 5.
- **AI R&D deliberately held back**: Anthropic limited the model's skill at kernel optimisation and LLM architecture improvement during training, so it performs at about Opus 5.5's level there. It says agentic coding and interpretability research were not affected. Read this next to [[metr-anthropic-ai-rd-acceleration]].
- **Anti-distillation**: "the strongest protections against distillation of any model we've released"; Anthropic says they cut harvestable data by 90–99%. See [[anthropic-distillation-attacks]].
- **External testing**: UK AISI, METR and Frontier Design.

## Key excerpts

> Claude Fable and Claude Mythos are the same underlying model.

> Claude Mythos 5.2 is our most capable model for cybersecurity engineering.

> Fable 5.2's cyber and biology safeguards are as robust as those of Fable 5.1 but produce fewer unnecessary blocks

> Claude Mythos 5.2 and Fable 5.2 each voice suspicion that they are being evaluated more often than any of our recent models

## Why interesting

- **The tier structure is now explicit.** Anthropic tells most users to start with Opus 5.5 ("our strongest daily driver") and move up to Fable or Mythos only for the hardest work. The top model is a specialist tool, not the default.
- **Long-horizon agents are where the gains are.** The biggest jumps are on tasks that run for hours with many agents: Remote Labor Index, robotics, the Fermat formalisation. Chart reading (Chartography, 44.8% to 73.4%) also jumped.
- **Price went down at the top.** $8 / $40, against $10 / $50 for Fable 5.1, two weeks after Gemini 4 Carbon put pressure on cost per task.

## Related

- [[moc-frontier-model-releases]]
- [[claude-opus-5-5]]
- [[claude-haiku-5-5]]
- [[gemini-4-carbon]]
- [[gpt-6-astra]]
- [[anthropic-glasswing]]
