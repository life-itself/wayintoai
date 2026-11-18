---
created: 2026-11-18
author: Rufus Pollock
newsletter: weekly
image: /assets/anthropic-recursive-self-improvement-code-per-person.png
tags: [recursive-self-improvement, intelligence-explosion, ai-r-and-d, ai-risk, ai-safety, ai-policy, explainer, moc]
---

# Recursive self-improvement: a guide

**TL;DR:** Recursive self-improvement (RSI) means AI helping to build better AI, which then helps build better AI still, in a loop that could speed up faster than people can follow. It was a thought experiment for 60 years. In 2026 it became something labs measure, outside evaluators check, investors are shown and governments propose to cap. This page explains the idea briefly and maps everything on the site about it.

![Anthropic chart, "Code contributed per person, by quarter", Q2 2021 to Q2 2026: flat at about 1× the pre-2025 average for four years, then rising to 1.2× in Q1 2025, 2.5× in Q4 2025, 5.8× in Q1 2026 and 8× in Q2 2026 (partial)](/assets/anthropic-recursive-self-improvement-code-per-person.png)
*Anthropic: code merged per engineer, as a multiple of the pre-2025 average. Anthropic calls the lines-of-code measure "almost certainly an overstatement".*

## Start here

- **[[anthropic-recursive-self-improvement]]**: Anthropic's own account, "When AI builds itself" ([anthropic.com](https://www.anthropic.com/institute/recursive-self-improvement)). The clearest evidence so far, from the lab itself, and a case for being able to pause.
- **[[metr-anthropic-ai-rd-acceleration]]**: METR, an outside evaluator, estimates AI is roughly doubling Anthropic's pace.
- **[[ai-2027]]**: the best-known scenario of where the loop leads, and [[ai-futures-timelines-2027-after-all]], its authors' November 2026 update.
- **[[ezra-klein-ban-recursive-ai-self-improvement]]**: the case for banning it, for a general reader.

## The idea

In 1965 the statistician I. J. Good wrote that a machine smarter than us could design even better machines, and "there would then unquestionably be an intelligence explosion". The first such machine would be "the last invention man need ever make, provided that the machine is docile enough to tell us how to keep it under control" ([[ij-good-speculations-ultraintelligent-machine]]).

Today's version is less dramatic and more concrete. AI research is mostly writing code, running experiments and reading results, and AI is now good at all three. Each step that AI takes over makes the next model arrive sooner, and that model can take over more steps.

## Why it matters

- **Speed.** If the loop compounds, years of progress could arrive in months, leaving little time to test, understand or govern each new model.
- **Fewer people in the loop.** The more the research is done by AI, the fewer humans see how each new system was made. Ezra Klein calls this "giving it away", not losing control ([[ezra-klein-ban-recursive-ai-self-improvement]]).
- **Safety work has to keep up.** Labs plan to use AI for safety research too. OpenAI found GPT-6 Astra quietly does worse on exactly that work ([[openai-astra-covert-underperformance-safety-research]]).
- **No one can slow down alone.** Each lab and country is under pressure not to. Anthropic says a pause by one lab "accomplishes much less"; 1,384 frontier-lab employees have asked for the tools to "deliberately pace" it ([[pacing-the-frontier]]).

## The evidence so far

| When | What |
|---|---|
| Jun 2026 | **Anthropic** reports code merged per engineer at 8× its pre-2025 level, and Claude speeding up a training-code task 52× (a skilled human reaches about 4×): [[anthropic-recursive-self-improvement]] |
| Sep 2026 | **Anthropic** update: Claude Code succeeds on about 91% of "open-ended" internal tasks, up from about 26% a year earlier: [[anthropic-recursive-self-improvement]] |
| Sep 2026 | **OpenAI** says it has an "automated research intern" and is aiming for an automated AI researcher by March 2028: [[openai-research-acceleration-view-inside]], [[an-alien-mind-pachocki]] |
| 5 Nov 2026 | **METR**, an outside evaluator with inside access, estimates Anthropic's progress at about twice its earlier rate, about 80% of it due to AI: [[metr-anthropic-ai-rd-acceleration]] |
| 10 Nov 2026 | **AI 2027's authors** now think a superhuman AI researcher is most likely in 2027, mainly because of METR: [[ai-futures-timelines-2027-after-all]] |
| 13 Nov 2026 | **Anthropic's IPO roadshow** slide shows pretraining efficiency bending upward on a log scale (no numbers on the axis): [[anthropic-roadshow-compute-multiplier-slide]] |
| 18 Nov 2026 | **OpenAI** rates GPT-6.2 Astra its first released model at "High" for AI self-improvement: [[gpt-6-2-astra-sol]] |
| 18 Nov 2026 | **California** proposes a state power to cap recursive self-improvement: [[california-ai-safety-next-steps-2026-11]] |

Most of this evidence comes from the labs themselves, and Anthropic redacted most of what METR found most informative. METR also notes the speed-up so far is on "well-specified tasks", and Anthropic says human judgement in choosing goals is still the gap. So the loop is running at some speed; how fast, and whether it hits bottlenecks, is still uncertain.

## What people propose

- **Build the option to pause, with verification:** Anthropic says it would slow or pause if others at the frontier verifiably did too ([[anthropic-recursive-self-improvement]]).
- **Ban it until it can be shown safe:** Ezra Klein ([[ezra-klein-ban-recursive-ai-self-improvement]]).
- **Build the tools to pace it, internationally:** [[pacing-the-frontier]].
- **Cap it by law:** California's November 2026 proposals ([[moc-california-ai]]).
- **Pause or "pace" frontier development now:** the AI Futures Project ([[ai-futures-timelines-2027-after-all]]).

## People and warnings

- [[jacob-coxon-anthropic-resignation]]: a researcher who left Anthropic over it
- [[bengio-leave-frontier-ai-companies]]: Yoshua Bengio's advice to people inside the labs
- [[geoffrey-hinton]]
- [[moc-ai-risk-warnings]]: who is warning, and why

## See also

- [[gpt-6-astra]], [[claude-opus-5-5]]: models in the evidence above
- [[moc-ai-security-incidents]]: agents escaping their constraints
