---
created: 2026-11-21
author: Levent Alpöge
tags: [ai, mathematics, riemann-hypothesis, claude, anthropic, lean, proofs, formal-verification]
newsletter: weekly
---

# Riemann Hypothesis proved by Anthropic and Claude (claimed)

Anthropic and Claude have produced a claimed proof of the Riemann Hypothesis. Anthropic mathematician Levent Alpöge says he and Claude have proved the Riemann Hypothesis, and the Generalized Riemann Hypothesis too, in about six weeks. The proof is released only as a Lean formalization, with no human-readable paper yet.

![Alpöge, remark.pdf](https://screenshotit.app/https://alpo.ge/remark.pdf)

> **Rufus's note (2026-11-21):**
> Massive news (if true): the Riemann Hypothesis solved by Claude over six weeks. — Rufus Pollock

## Links

- **Announcement**: [alpo.ge/remark.pdf](https://alpo.ge/remark.pdf), a four-page note dated 20 Nov 2026
- **Lean code**: `https://alpo.ge/lean.tar.gz.part01` to `part14` (14-part archive)
- **Discussion**: [X trending summary](https://x.com/i/trending/2124000775961784415)

## What the note says

- "I believe I have, working with Claude, discovered a proof of the Riemann Hypothesis." The method "easily extends" to GRH, and Alpöge expects the Extended Riemann Hypothesis "with more time". He says the arguments are formalized "without assumptions".
- **Claude led the finish.** Alpöge set up the strategy by analogy with a toy setting, a descendant of Stepanov's function-field argument. Then "Claude far outpaced me near the finish line. No, Claude flew, and danced, and sparkled". His headline example: to mimic multiplicity over the integers, Claude proposed chaining theta lifts, with a chain of length √X for a von Mangoldt sum of length X.
- **Lean only, no paper.** A written version would be "a huge, unreadable document"; Claude's draft "book" hit 250,000+ pages. Posting that would be "slop", so he released only Lean. He admits he has not yet mastered much of the mathematics, especially automorphic forms on higher-rank groups, and expects much shorter proofs to follow.
- **Timeline.** A 20-step timeline, which Claude compiled, runs from a "Stepanov determinant" on 6 Oct 2026 to iterated theta lifts on 15 Nov and "GRH" on 16 Nov. That is about six weeks.
- **Timing.** The breakthrough came "late Sunday night". He messaged Dario Amodei about whether he could announce, and says there was "a constraint to respect". He says the "obvious cynical view, to do with the timing" is false. Anthropic is mid-IPO ([[anthropic-ipo-s1]]).
- **OpenAI credit.** He praises OpenAI's earlier results (see [[openai-navier-stokes-millennium-proof]] and [[openai-math-results-release]]). One was a Siegel argument he read as "Stepanov without multiplicity", and it convinced him the problem would fall.

## Status

As of 21 Nov this is a strong claim but not a confirmed result. Two checks decide it:

1. **Does the Lean build check?** Partly done. MIT's Andrew Sutherland says it compiled and the Lean kernel rechecked it "with only the three standard axioms" ([Scientific American](https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/)).
2. **Is the final theorem really RH or GRH?** Still open. Kevin Buzzard says the "comparator" run that would settle this is still pending.

Terence Tao calls it an "(enormous) Lean-only proof" and points to the Lean Zulip thread as the place to follow verification. The X summary's "17 million lines" figure is unconfirmed. Its Tao "strip mining" line comes from his September comment on [[openai-navier-stokes-millennium-proof]], not from this claim.

## Why it matters

The Riemann Hypothesis is perhaps the most famous open problem in mathematics. It is one of the Clay Millennium Prize Problems, and [[proofatlas]] ranks it #2. If the proof holds, it is the biggest result yet in the [[ai-and-mathematics]] run. It would also be the first flagship result credited to Claude and not OpenAI. Alpöge was already on that list: he disproved the Jacobian conjecture in July and was on the Navier–Stokes team that disputed OpenAI's priority. It also shows the shift Tao and the Fields Medallists warned about in [[tao-fields-medalists-ai-mathematics-declaration]]: complete machine proofs that no one, not even their human co-author, fully understands yet.

## See also

- [[ai-and-mathematics]]: map of AI maths milestones
- [[anthropic-formal-verification]]
- [[ai-is-rewriting-mathematics]]
