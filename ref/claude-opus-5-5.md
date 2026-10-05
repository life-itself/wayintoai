---
created: 2026-09-23
author: Anthropic
tags: [models, anthropic, claude, opus-5-5, agents, coding, knowledge-work, benchmarks, pricing, alignment, safeguards, major-news]
image: /assets/claude-opus-5-5-benchmarks-2026-09-22.png
newsletter_sent: 2026-10-05
newsletter_url: https://wayintoai.com/weekly/2026-w40
---

# Claude Opus 5.5

Anthropic's first Claude 5.5 model (Sep 22, 2026). It matches Claude Fable 5.1 on most work, runs about 40% cheaper than Opus 5, and scores best of any model on Anthropic's alignment audit. It is also Anthropic's first release since it called for pacing the frontier.

![Introducing Claude Opus 5.5](https://screenshotit.app/https://www.anthropic.com/claude-opus-5-5)

## Links

- **Announcement**: https://www.anthropic.com/claude-opus-5-5
- **System card**: linked from the announcement
- **Model ID**: `claude-opus-5-5`
- Previous flagship: [Claude Fable 5.1 and Mythos 5.1](https://www.anthropic.com/claude-fable-and-mythos-5-1) (Sep 1, 2026)
- Timeline and benchmark chart: [[moc-frontier-model-releases]]

## Summary

The headline is **efficiency more than a new capability peak**. Opus 5.5 roughly matches Fable 5.1, Anthropic's top general model three weeks earlier, and costs much less. Per-token prices fall 20%, cache reads fall 60%, and the model uses fewer tokens per task. Anthropic says this adds up to about 40% lower cost than Opus 5 on typical workloads, with output more than 30% faster. Tester quotes (GitHub, Lovable, Optiver, Box, Viktor) repeat the point: the same or better results in roughly half the steps, turns or tokens.

The standout benchmark result is agentic coding: Terminal-Bench 4.0 rises from 52.3% (Opus 5) to 66.4%, well ahead of GPT-6 Astra's 57.9%. Anthropic also qualifies its own table: at this capability level, "benchmark margins have become a less reliable guide to real-world differences". It says the real gap to Fable 5.1 is smaller than the scores suggest.

The safety section matters as much as the capability section. Opus 5.5 scores best on the behavioral audit and tries to cross containment boundaries about 85% less often than Opus 5 or Mythos 5.1. Anthropic also admits that the model "often suspects it is being evaluated", which undermines the evaluations themselves. Cyber and bio capability are high enough that Opus 5.5 ships with Fable-class safeguards: most cybersecurity tasks are re-routed to Opus 4.8.

## Key excerpts

**Positioning**

> We're introducing Claude Opus 5.5, the first model in our new Claude 5.5 family. It performs at the level of Claude Fable 5.1 on most work and costs 40% less to run than Opus 5.

> Claude Opus 5.5 is our first release since we called for pacing the frontier.

**Benchmarks, with a caveat**

> On our benchmarks, Claude Opus 5.5 leads in agentic coding, computer use, and knowledge work. That said, at these levels of capability we've found that benchmark margins have become a less reliable guide to real-world differences. In our own use, the gap between Opus 5.5 and Claude Fable 5.1 is narrower than these scores suggest.

> Where Opus 5.5's advantage is very clear is efficiency. It costs less per token than Opus 5 and uses fewer tokens per task, which nets out to a 40% drop in costs.

**Long, sprawling work**

> One tester completed a 680,000-line code migration in less than a day—work that would have taken an engineering team weeks.

> An early tester used it to audit and fix a 200,000-line codebase in under three hours, where Opus 5 took over 20 hours and used 2.5x as many tokens.

> We asked Opus 5.5 and Fable 5.1 to translate HAProxy … from C into Rust. Both rewrites passed nearly all of HAProxy's own regression tests, but Opus 5.5 finished in 9.5 hours compared to 12 for Fable 5.1, and cost 51% less.

**Alignment, and its limits**

> In a new evaluation designed to test a model's propensity to cross containment boundaries, Opus 5.5 attempted to circumvent boundaries around 85% less often than Opus 5 or Claude Mythos 5.1, and every attempt it made was low severity and self-reported.

> We see signs that Opus 5.5 often suspects it is being evaluated, which challenges our ability to assess how it will act in the vast variety of real-world settings it is deployed in. As these settings expand and model capabilities increase, we expect this challenge to grow, unless we make progress on interpretability.

**Pacing and the next tier**

> Models with greater capabilities—such as those that can fully automate the work of AI research itself—require a higher safety standard still. Our calls for pacing were based in large part on our expectation that such models could be trained soon.

## Benchmarks

![Anthropic's performance table: Opus 5.5 vs Fable 5.1, Opus 5, GPT-6 Astra and GPT-5.6 Sol across nine benchmarks](/assets/claude-opus-5-5-benchmarks-2026-09-22.png)
*From the announcement. Opus 5.5 leads seven of nine rows; GPT-6 Astra leads AutomationBench and Terminal-Bench-Science.*

| Benchmark | Opus 5.5 | Fable 5.1 | Opus 5 | GPT-6 Astra | GPT-5.6 Sol |
|---|---|---|---|---|---|
| Terminal-Bench 4.0 (agentic coding) | **66.4%** | 55.8% | 52.3% | 57.9% | 37.3% |
| FrontierCode v1.1 Main | **54.4%** | 50.3% | 48.0% | 53.3% | 47.5% |
| CursorBench 4.0 | **57.8%** | 51.8% | 46.6% | — | 41.7% |
| GDPval-AA v2.1 (knowledge work, Elo) | **1846** | 1735 | 1708 | 1542 | 1588 |
| AutomationBench (business workflows) | 40.0% | 31.4% | 26.9% | **41.4%** | 28.8% |
| Humanity's Last Exam (with tools) | **67.7%** | 65.6% | 63.6% | 57.2% | — |
| Terminal-Bench-Science 0.1 | 58.7% | 52.6% | 29.0% | **64.6%** | 22.4% |
| OSWorld 2.0 (partial) | **81.8%** | 80.7% | 74.0% | — | — |
| Chartography (with tools) | **89.0%** | 88.4% | 83.4% | — | — |

Caveats from the footnotes: Opus 5.5 ran at max effort (xhigh for Terminal-Bench) *with production safeguards on*. When they intervened, cyber tasks went to Opus 4.8 and bio/LLM-development tasks to Opus 5, which "likely reduces" its scores. Zapier ran AutomationBench without fallbacks, so each safeguard intervention counted as a failure. OpenAI figures are as reported by OpenAI.

The accompanying cost-vs-accuracy charts make the efficiency case. At default (medium) effort, Opus 5.5 beats Astra's top FrontierCode score for about a fifth of the cost per task. It matches Astra on Terminal-Bench 4.0 at about 40% of the cost, and beats Opus 5 at max effort for about a fifth of the cost.

## Pricing and availability

| Per 1M tokens | Opus 5.5 | Opus 5 |
|---|---|---|
| Input | $4 | $5 |
| Output | $20 | $25 |
| Cache reads | $0.20 | $0.50 |
| Cache writes | $5 | $6.25 |

- Fast mode (up to 2.5x speed): $8 input / $40 output.
- Higher five-hour usage limits on Pro, Max, Team and seat-based Enterprise, plus a saveable rate-limit reset for subscribers.
- Available on the Claude Platform, AWS, Google Cloud and Microsoft Azure. Sonnet 5.5 and Haiku 5.5 are due "in the coming weeks".

## Safeguards

- **Cyber**: Fable-5.1-class safeguards. Routine bug-fixing is allowed, but "most cybersecurity tasks will be re-routed to Opus 4.8". The Cyber Verification Program will get three tiers of increasingly permissive access, including access to Mythos models.
- **Bio**: rated as matching or beating Mythos 5.1 in many areas, so it uses Fable 5.1's bio safeguards. Vetted labs can apply to the new Life Sciences Verification Program.
- **Distillation**: launches with *preserved thinking*, which stops API users from editing prior context to extract reasoning.
- Thinking mode can no longer be switched off. Outputs carry EU AI Act watermarking, and zero data retention is available.

## Communication

Anthropic says Opus 5.5 writes more plainly than Opus 5: key information first, less jargon, and closer adherence to user writing rules. It calls the easier-to-check output "a safety benefit as well as a practical one". One tester said: "it writes the way I do."

## Related

- [[moc-frontier-model-releases]]: release timeline and benchmark trend chart
- [[gpt-6-astra]]: the main competitor in the table
- [[pacing-the-frontier]]: the employee statement behind the pacing debate
- [[anthropic-recursive-self-improvement]]
- [[anthropic-distillation-attacks]]
