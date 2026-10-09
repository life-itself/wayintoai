---
created: 2026-10-09
author: OpenAI
tags: [ai, mathematics, openai, proofs, lean, riemann-hypothesis, hodge-conjecture, birch-swinnerton-dyer, reasoning-models, open-research]
---

# OpenAI releases 719 AI-produced maths papers (incl. the quasi-Riemann hypothesis)

On 7 October 2026 OpenAI released 719 manuscripts in 372 "families" of new mathematical results, all produced by its unreleased internal frontier model. They are on GitHub with Lean formalizations for about 42% of the headline results.

![OpenAI: Sharing AI progress in mathematics](https://screenshotit.app/https://openai.com/index/sharing-ai-progress-in-mathematics/)

## Links

- **Announcement**: https://openai.com/index/sharing-ai-progress-in-mathematics/ (7 Oct 2026)
- **Repository**: https://github.com/openai/math (Apache-2.0; created 6 Oct, already revised 7 Oct)
- **Manuscript map**: https://github.com/openai/math/blob/main/CONTENTS.md
- **Quasi-RH paper**: [The Quasi-Riemann Hypothesis: A Zero-Free Half-Plane Re s > 7/8](https://github.com/openai/math/blob/main/preprints/The-Quasi-Riemann-Hypothesis-September-30-2026/paper.pdf)
- **New York Times: mathematicians respond** (8 Oct): https://www.nytimes.com/2026/10/08/science/mathematicians-respond-openai-release.html
- **ProofAtlas status note on RH**: https://www.proofatlas.ai/open-problems/#problem-riemann-hypothesis ([[proofatlas]])
- **IAS Advisory Group on Mathematics and AI**: https://agmai.org/ ([recommendations, 29 Sep](https://agmai.org/general-sep29/))
- **OpenAI tweet**: https://x.com/OpenAI/status/2107596713791767021
- **Alex Kontorovich reaction**: https://x.com/AlexKontorovich/status/2107609087902941646

## What was released

- **719 manuscripts in 372 families.** Each family groups a main result with its companion papers, consequences or alternative proofs, and is classified by discipline.
- **Lean formalizations** for about 300 of the 719 (~42%) headline results, with more promised.
- **Reasoning summaries** for 10 results: abridged traces of how the model got there, e.g. Mahler's conjectures, Kaplansky's direct-finiteness conjecture in characteristic two, and the isomorphism of free group factors.
- **Compute and attempt statistics.** The model was given about 4,000 problems, and the average result took about three hours of ChatGPT Pro thinking. OpenAI's README says it "expanded these evaluations after performance on our existing mathematical evaluations saturated."

OpenAI says the release format came out of consultation with the Institute for Advanced Study's independent Advisory Group on Mathematics and AI. It is also funding workshops and conferences to help mathematicians digest AI-produced results, and is "working to responsibly release the model that produced these results."

## Headline results (as claimed)

- **Quasi-Riemann hypothesis (family 003).** Every Dirichlet L-function, including the Riemann zeta function, has no zeros where Re(s) > 7/8. A companion paper gives a different proof for Re(s) > 11/12, which also rules out Landau–Siegel zeros. The family has a [Lean formalization](https://github.com/openai/math/blob/main/lean/docs/003.md). OpenAI notes the zeta work fell outside its standard procedure, and that humans edited the 11/12 writeup for readability.
- **Birch–Swinnerton-Dyer (002).** The full BSD leading-term formula for every elliptic curve over ℚ with Selmer corank ≤ 1 at some prime. This gives full BSD for a density-one set of quadratic twists.
- **Rational Hodge conjecture for CM abelian varieties (032).** By Milne's results, this also gives the Tate conjecture for abelian varieties over finite fields.
- **Also:** Ostmann's inverse Goldbach conjecture, Koebe's circle-domain conjecture, abelian Zilber–Pink, a disproof of Kuznetsov's rationality conjecture for cubic fourfolds, two-dimensional Fontaine–Mazur at 2, and hundreds more.

## Why it matters: "an instant Fields Medal"

Rutgers mathematician Alex Kontorovich on the quasi-RH result:

> Quasi-RH?!?!???! Are you kidding me? If a human did this, it would be an instant Fields Medal, no questions asked.
>
> RH says zeta has no zeros in Re(s)>1/2. The best we had until a second ago was a region that got thinner and thinner the higher up the imaginary axis you go. I thought maybe they'd fatten that up a bit, that'd be a massive breakthrough. But no. They got a zero free strip!!!! Insane

![Alex Kontorovich's tweet on the quasi-Riemann hypothesis paper](/assets/kontorovich-quasi-rh-tweet-2026-10-09.png)

In short, mathematicians had only ever proved zero-free regions that shrink to nothing high up the critical strip. A fixed zero-free half-plane at any σ < 1 is a long-standing open problem, the "quasi-Riemann hypothesis". The full Riemann hypothesis would push that boundary to 1/2.

### "A kind of vertigo"

From the [New York Times](https://www.nytimes.com/2026/10/08/science/mathematicians-respond-openai-release.html), Yuanning Zhang, a maths PhD student at Northwestern visiting SLMath:

> What I'm feeling is less a judgment than a kind of vertigo. If these reported resolutions are verified, this would suggest that A.I.-assisted mathematical research is beginning to operate on an industrial scale.

Early rumours put the release at 400 solved problems, which made Zhang think of Truffaut's *The 400 Blows*:

> The film is about a boy who is evaluated, judged and shut away from society, and no one really takes the time to understand him. Towards the end, he runs to the sea, and the film ends on a freeze frame that passes no judgment on whether this is an escape or a dead end. I don't think that's a bad picture of where mathematics stands with these results.

## Caveats

- **Verification is uneven.** OpenAI's README says: "This collection includes results at different stages of verification… Some of the unformalized results could have issues."
- **Retractions have already happened.** On 7 October, the same day as the announcement, OpenAI withdrew three Hodge-conjecture manuscripts after finding a sign error in one paper that broke a construction two others relied on. It also repaired 14 other manuscripts.
- **The scale is the problem the Fields Medallists warned about.** 719 papers at once is exactly the "strip-mining" mathematicians objected to in September. Following the IAS group's guidelines and adding versioned corrections responds to some of that criticism, but not to all of it.

## Related

- Our take: [Maths is being industrialised, and it's making mathematicians dizzy](/posts/2026-10-09-maths-goes-industrial)

- [[ai-and-mathematics]]
- [[openai-navier-stokes-millennium-proof]]: same internal model, September 2026
- [[tao-fields-medalists-ai-mathematics-declaration]]
- [[openai-unit-distance-problem-ai-proof]]
- [[proofatlas]]: AI-ranked list of top open problems, tracking claims like this one
