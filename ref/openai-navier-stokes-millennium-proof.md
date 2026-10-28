---
created: 2026-09-10
author: OpenAI
tags: [ai, mathematics, navier-stokes, millennium-prize-problem, fluid-dynamics, proofs, reasoning-models, openai, lean, multi-agent, controversy, superintelligence]
---

# OpenAI: a proof for the Navier–Stokes Millennium Prize Problem

> Since August 28 we have been training a new internal model that has exhibited unprecedented performance in our benchmarks, including mathematics. This model's training is ongoing and its performance continues to improve.
> — OpenAI, *On the Navier–Stokes Millennium Prize Problem*

![OpenAI: performance of GPT-6 Astra vs the new internal model on a curated set of open math problems — the new model, training only since Aug 28, is already roughly 2–3× Astra's pass rate](/assets/openai-new-model-since-aug-28-2026-09-10.jpg)

**Source:** [openai.com/index/navier-stokes-solution](https://openai.com/index/navier-stokes-solution/) — Sep 8, 2026

---

## What was claimed

OpenAI says an internal AI system produced a proof — with a full formalization in the **Lean** proof assistant — that solutions to the 3D incompressible **Navier–Stokes equations can develop a singularity in finite time** (the fluid's velocity or its gradient "blows up" to infinity). If it holds up, this resolves one of the seven **Clay Mathematics Institute Millennium Prize Problems** ($1M bounty), open in its modern form since Leray's work in the 1930s and formally posed by Clay in 2000.

The direction of the answer matters: OpenAI's result is a **blow-up** (non-smoothness) result, not a proof of global regularity.

### The run

- On the order of **~10,000 concurrent agents**, launched **September 1**.
- The agents reached the resolution on **Saturday, September 5 — ~88 hours** after launch.
- For Navier–Stokes specifically: **~2.7 million messages**, **~130 billion output tokens**.
- **Lean formalization and verification**: an additional **~17 hours**, run via **GPT-6 Astra**.
- The proof itself came from an **unreleased next-generation model** — the one "training since August 28."

### The chart (asset)

The embedded figure is OpenAI's own: *"Performance of GPT-6 Astra and our Internal Model on a curated set of open math problems."* Pass rate vs test-time compute (log scale). The new internal model sits far above Astra at every compute budget — roughly **0.26 → 0.48** pass rate across the sweep versus Astra's **~0.08 → 0.17**. See the post [This is definitely getting towards superintelligence](/posts/2026-09-10-the-pace-is-the-story) for why this sub-plot, not the proof, may be the real story.

## The controversy

The announcement was immediately contested on **priority and conduct** grounds.

- **The other team.** NYU's **Tristan Buckmaster** and Anthropic mathematician **Levent Alpöge** had worked on the same problem for about a year, using AI assistance. Buckmaster says they made "real progress" on **August 15** and had verified it by **August 22**. Buckmaster: *"Almost nobody else I know of was working on it."*
- **The Codex question.** The pair had put *all* their drafts, for the whole project, into **OpenAI Codex** sessions. Buckmaster: *"I asked whether the model had been trained on, or had access to, our sessions in Codex… I was told the model did not look up user data. I asked again, about training, and I did not get an answer."*
- **The timeline.** OpenAI requested a call on **Sep 3**, spoke with Buckmaster on **Sep 6**, published on **Sep 8**. OpenAI began its own push only after rumours of the Anthropic-side work reached it.
- **Intimidation allegation.** Buckmaster says OpenAI's **Sébastien Bubeck** pressed him to either publish with reduced credit to Alpöge or claim the Millennium Prize while acknowledging OpenAI's proof; when he declined, that Bubeck said *"Why would you ruin your career?"* and *"If you don't want me to be nice, then I don't have to be nice."*
- **OpenAI's denial (Bubeck).** *"We did not use their prompts or proofs to prompt our models or direct our agents… We did not see any of their work through any means until they released it publicly."*
- **Terence Tao's lament.** Tao warned that *"strip-mining of open problems for solutions may destroy the ecosystem from which the next generation of mathematical techniques… would have developed,"* likening it to archaeological looting.

## Expert verdict: "definitely insane" (Oct 2026)

Scott Armstrong (CNRS and NYU Courant, a specialist in PDEs and mathematical physics) [explained on X](https://x.com/scottnarmstrong/status/2114412308185100522) why the construction is new. It is closest to convex integration, where oscillations are usually built by hand. In OpenAI's proof, a fluid instability makes the flow generate its own oscillations, drawing energy from the background shear.

Those oscillations then produce the force that creates the collapsing smooth vortex. Armstrong says using a physical instability this way has no precedent. Some ingredients are in the literature, but the combination is not.

He calls the paper perhaps beyond what a human could have come up with, but not beyond human understanding: several groups of PDE experts say they now more or less follow it. His summary: "anyone saying that this OAI result is unsurprising is bullshitting."

## Why this matters

Navier–Stokes is not another decades-old niche conjecture — it is a **flagship** unsolved problem, one of the six Millennium Problems still open. Doing it (if verified) in **88 hours** with a swarm of agents, using a model that **did not exist two weeks earlier**, is a step change from the [[ai-is-rewriting-mathematics|July–August run of results]] and OpenAI's own [[ai-and-mathematics|Astra 10-problem announcement]].

The dispute is now part of the story, not a footnote: the same episode raises (a) whether a lab can **scoop** an identified research route using superior compute and rumour, (b) whether **customer drafts in Codex** are safe from a vendor racing the same problem, and (c) whether **"solved by AI" corrodes the field** even when the answer is right.

## See also

- [Post: This is definitely getting towards superintelligence](/posts/2026-09-10-the-pace-is-the-story) — the pace, not the proof, is the headline
- [[ai-and-mathematics]] — running timeline of AI mathematical milestones (Navier–Stokes added)
- [[ai-is-rewriting-mathematics]] — Nofil's July–August timeline and the "mathematicians crashing out" reaction
- [[openai-unit-distance-problem-ai-proof]] — May 2026 Erdős unit-distance disproof, the previous "first"

## Links

- OpenAI — *On the Navier–Stokes Millennium Prize Problem*: https://openai.com/index/navier-stokes-solution/
- TechCrunch — *OpenAI fought dirty on career-making math problem, says NYU mathematician* (Russell Brandom, Sep 8, 2026): https://techcrunch.com/2026/09/08/openai-fought-dirty-on-career-making-math-problem-says-nyu-mathematician/
- Fortune — *OpenAI says it cracked Navier-Stokes…* (Sep 8, 2026): https://fortune.com/2026/09/08/openai-says-it-cracked-navier-stokes-math-grand-challenge-buckmaster-accusation-cheating-intimidation-tao-lament/
- Simon Willison — *On the Navier–Stokes Millennium Prize Problem* (Sep 8, 2026): https://simonwillison.net/2026/Sep/8/on-navier-stokes/
- CNN Business (Sep 9, 2026): https://www.cnn.com/2026/09/09/business/openai-millennium-problems-navier-stokes-hnk
- ABC News (Australia) (Sep 10, 2026): https://www.abc.net.au/news/2026-09-10/openai-navier-stokes-millennium-problem-claims/107132242
