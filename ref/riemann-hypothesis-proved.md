---
created: 2026-11-21
author: Levent Alpöge
tags: [ai, mathematics, riemann-hypothesis, claude, anthropic, lean, proofs, formal-verification]
newsletter: standalone
featured: true
---

# Riemann Hypothesis proved by Anthropic and Claude, certified in Lean

**Update (21 Nov 2026):** the Lean FRO and the Mathlib Initiative jointly certified both the statement and the proof: "We have full confidence that Alpöge's proof of the Riemann Hypothesis is correct." See Status below.

Anthropic mathematician Levent Alpöge says he and Claude, Anthropic's AI, have proved the Riemann Hypothesis, and the Generalized Riemann Hypothesis too, in about six weeks. The proof is released only as a Lean formalization, with no human-readable paper yet.

![Alpöge, remark.pdf](https://screenshotit.app/https://alpo.ge/remark.pdf)

> **Rufus's note (2026-11-21):**
> Massive news (if true): the Riemann Hypothesis solved by Claude over six weeks.

> **Rufus's note (2026-11-24):**
> Riemann is massive.

My short on it, *The end of human mathematics. Everything else is next.*:

https://www.youtube.com/shorts/rOWKmYk4_eQ

## Links

- **Announcement**: [alpo.ge/remark.pdf](https://alpo.ge/remark.pdf), a four-page note dated 20 Nov 2026
- **Lean code**: `https://alpo.ge/lean.tar.gz.part01` to `part14` (14-part archive)
- **Certification**: [Lean verification of the Riemann Hypothesis](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/), joint statement by the Lean FRO and Mathlib Initiative, 21 Nov 2026; overview of checks by Andrew Sutherland at [math.mit.edu/~drew/grh](https://math.mit.edu/~drew/grh/)
- **Rufus's short**: [The end of human mathematics. Everything else is next.](https://www.youtube.com/shorts/rOWKmYk4_eQ) (Seeds of Renaissance, YouTube)
- **Discussion**: [X trending summary](https://x.com/i/trending/2124000775961784415)

## What the note says

- "I believe I have, working with Claude, discovered a proof of the Riemann Hypothesis." The method "easily extends" to GRH, and Alpöge expects the Extended Riemann Hypothesis "with more time". He says the arguments are formalized "without assumptions".
- **Claude led the finish.** Alpöge set up the strategy by analogy with a toy setting, a descendant of Stepanov's function-field argument. Then "Claude far outpaced me near the finish line. No, Claude flew, and danced, and sparkled". His headline example: to mimic multiplicity over the integers, Claude proposed chaining theta lifts, with a chain of length √X for a von Mangoldt sum of length X.
- **Lean only, no paper.** A written version would be "a huge, unreadable document"; Claude's draft "book" hit 250,000+ pages. Posting that would be "slop", so he released only Lean. He admits he has not yet mastered much of the mathematics, especially automorphic forms on higher-rank groups, and expects much shorter proofs to follow.
- **Timeline.** A 20-step timeline, which Claude compiled, runs from a "Stepanov determinant" on 6 Oct 2026 to iterated theta lifts on 15 Nov and "GRH" on 16 Nov. That is about six weeks.
- **Timing.** The breakthrough came "late Sunday night". He messaged Dario Amodei about whether he could announce, and says there was "a constraint to respect". He says the "obvious cynical view, to do with the timing" is false. Anthropic is mid-IPO ([[anthropic-ipo-s1]]).
- **OpenAI credit.** He praises OpenAI's earlier results (see [[openai-navier-stokes-millennium-proof]] and [[openai-math-results-release]]). One was a Siegel argument he read as "Stepanov without multiplicity", and it convinced him the problem would fall.

## Status

**Certified (21 Nov 2026).** In a [joint statement](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/), the Lean FRO and the Mathlib Initiative "certify that both the statement and the proof of the Riemann Hypothesis are correct". Their four checks:

1. **The statement is right.** The theorem is Mathlib's own `RiemannHypothesis`, vetted by Lean and number theory experts.
2. **It compiles.** Dozens of people built the 17-million-line library and reproduced the same proof export.
3. **It proves that statement.** Two independent tools (comparator and con-leche) confirm the proved theorem is exactly Mathlib's RH. This was the open question on 21 Nov.
4. **The proof is valid.** Lean's kernel and several independent checkers, some written in other languages, accepted it. Two of them (con-leche, con-ron) have formal proofs that they cannot accept a false proof, which answers worries about flaws in Lean itself.

The checks ran on an inert export, out of reach of any malicious code in the sources. What is still missing is a human-readable account: the statement says it looks forward to the mathematical community explaining "the new ideas in this proof". Terence Tao had called it an "(enormous) Lean-only proof". The Tao "strip mining" line in the X summary comes from his September comment on [[openai-navier-stokes-millennium-proof]], not from this claim.

## Why it matters

The Riemann Hypothesis is perhaps the most famous open problem in mathematics. It is one of the Clay Millennium Prize Problems, and [[proofatlas]] ranks it #2. With the proof certified, it is the biggest result yet in the [[ai-and-mathematics]] run. It would also be the first flagship result credited to Claude and not OpenAI. Alpöge was already on that list: he disproved the Jacobian conjecture in July and was on the Navier–Stokes team that disputed OpenAI's priority. It also shows the shift Tao and the Fields Medallists warned about in [[tao-fields-medalists-ai-mathematics-declaration]]: complete machine proofs that no one, not even their human co-author, fully understands yet.

## See also

- [[ai-and-mathematics]]: map of AI maths milestones
- [[anthropic-formal-verification]]
- [[ai-is-rewriting-mathematics]]
