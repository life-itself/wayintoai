---
created: 2026-10-28
author: OpenAI
newsletter: weekly
tags: [ai, mathematics, physics, computer-science, openai, proofs, lean, millennium-prize-problem, yang-mills, kakeya, exponential-time-hypothesis, complexity-theory, open-research]
---

# OpenAI: the Exponential Time Hypothesis is false, Kakeya in all dimensions, and Yang–Mills exists

On 26 October 2026 OpenAI announced three new results from its internal models, each a major open problem: in computer science, mathematics and physics. Each was checked in the Lean proof assistant, and each is handed to outside experts to explain.

![OpenAI: Working with academic communities to build scientific understanding](https://screenshotit.app/https://openai.com/index/building-scientific-understanding-with-academic-communities/)

## Links

- **Announcement**: [Working with academic communities to build scientific understanding](https://openai.com/index/building-scientific-understanding-with-academic-communities/) (OpenAI, 26 Oct 2026)
- **Proofs and write-ups**: https://github.com/openai/math (maths and computer science results; physics held back)

## The three results

| Field | Result | Shepherds |
|---|---|---|
| **Computer science** | The Exponential Time Hypothesis (ETH) is false | Russell Impagliazzo and Ramamohan Paturi (who proposed ETH), Ryan Williams |
| **Mathematics** | Local smoothing in every dimension, so the Kakeya and Stein restriction conjectures hold in all dimensions | Released openly, no group |
| **Physics** | Rigorous existence of QCD and a unified completion of the Standard Model, including pure Yang–Mills (part of a Millennium Prize problem) | David Gross (Nobel 2004), Arthur Jaffe, Michael Douglas, Igor Klebanov, Nikita Nekrasov |

*Source: OpenAI. Results found 9 Sep (Yang–Mills) to 18 Oct; all formalized in Lean.*

## Why each matters

**ETH** is a long-held belief that some hard problems (Boolean satisfiability, close to P vs NP) can't be solved much faster than brute force. Hundreds of papers assume it to prove other problems hard. If it is false, those hardness results lose their footing and faster algorithms may exist, though finding them is further work.

**Local smoothing** (Sogge, 1991) says extreme focusing of waves must be short-lived. It was proved in two dimensions in 2019, and Kakeya in three dimensions in 2025. OpenAI's proof covers every dimension, via a new auxiliary equation.

**Yang–Mills existence** is half of one of the seven Clay Millennium Prize problems (the other half is the "mass gap"). OpenAI says this could make quantum field theory, the framework of modern physics, mathematically rigorous.

## A new release process

After the credit fights over [[openai-navier-stokes-millennium-proof|Navier–Stokes]], OpenAI says it seeks no academic credit. Expert "shepherds" chose how each result is released. Groups are unpaid, sign no NDAs and speak for themselves. OpenAI will fund a conference on ETH and has given $5 million to a Simons Foundation programme for understanding AI-produced results.

## See also

- [[openai-math-results-release]]: the 7 October bulk release of 719 papers
- [[openai-navier-stokes-millennium-proof]]
- [[ai-and-mathematics]]
