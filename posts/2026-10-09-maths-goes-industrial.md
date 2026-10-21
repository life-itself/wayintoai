---
newsletter_sent: 2026-10-13
newsletter_url: https://wayintoai.com/weekly/2026-w42
title: "OpenAI releases Fields Medal-level maths in bulk"
description: In one drop, OpenAI has released hundreds of new maths results from a single unreleased model, claimed solutions to long-standing open problems, including one a leading mathematician called "an instant Fields Medal". Most are not yet verified, but maths is being industrialised, and it's making mathematicians dizzy.
date: 2026-10-09
featured: true
newsletter: standalone
authors: [rufus-pollock]
---

I studied maths at Cambridge through to graduate level and very nearly did a PhD. So this one is personal. I think maths as a discipline, in its current form, is in many ways over. If I were a graduate student today, I honestly don't know what I'd be thinking.

Here's why. This week OpenAI [released 719 maths papers](/ref/openai-math-results-release), all written by an unreleased internal model. They aren't exercises. They are claimed solutions to open problems, grouped into 372 "families" of related results, and the list includes some of the biggest names in number theory and geometry. Individually, several would be career-defining: the kind of result that wins a Fields Medal or settles a whole field. Here there are hundreds, from one model, in one drop. This is Dario Amodei's ["country of geniuses in a datacenter"](https://www.darioamodei.com/essay/machines-of-loving-grace) showing up in one field, at scale.

The one that stopped people in their tracks is the **quasi-Riemann hypothesis**: a proof that the Riemann zeta function has no zeros to the right of the line Re(s) = 7/8. Alex Kontorovich, a professor of mathematics at Rutgers, posted:

> Quasi-RH?!?!???! Are you kidding me? If a human did this, it would be an instant Fields Medal, no questions asked.

![Alex Kontorovich's tweet on the quasi-Riemann hypothesis paper](/assets/kontorovich-quasi-rh-tweet-2026-10-09.png)

To be clear, this is not the Riemann hypothesis itself, which would push that line all the way to 1/2. But until last week the best anyone had was a zero-free region that got thinner and thinner the higher up you went. A fixed zero-free half-plane is a different kind of result, and a long-standing open problem.

The same release also claims the full Birch–Swinnerton-Dyer formula for a large class of elliptic curves, the Hodge conjecture for CM abelian varieties, and hundreds of other results.

## The pace is the story

I [said this in September](/posts/2026-09-10-the-pace-is-the-story) and it's even more true now. Look at the [last five months](/ref/ai-and-mathematics):

- **May:** an OpenAI model disproves Erdős's unit-distance conjecture. Tim Gowers says he would have recommended it for the Annals.
- **July:** a cascade. Decades-old conjectures fall almost daily, many of them to ordinary people prompting public models.
- **August:** GPT-6 Astra solves 10 major open problems for under $2,000 of compute.
- **September:** OpenAI claims a Lean-checked Navier–Stokes blow-up proof, a Millennium Prize Problem, from a model that had been training for less than two weeks.
- **October:** 719 papers in one drop. The average result took the equivalent of about three hours of ChatGPT Pro thinking.

Six months ago a single AI result on an open problem was news. Now OpenAI says its existing maths benchmarks have "saturated" and that it gave the model about 4,000 open problems to see what it could do. It says it's "working to responsibly release the model that produced these results."

## What it's breaking

This is where I think the bigger story is. The results are arriving faster than the field can absorb them, and that is destabilising in several ways at once.

**Verification can't keep up.** About 42% of the headline results have a computer-checked Lean proof. The rest need human referees, and there are not enough of them for 719 papers. On the very day of the announcement OpenAI withdrew three Hodge-conjecture papers because of a sign error, and repaired 14 others. OpenAI says plainly that some of the unformalized results "could have issues."

**The field's own sense of itself is wobbling.** In September, 25 Fields Medallists [signed a declaration](/ref/tao-fields-medalists-ai-mathematics-declaration) saying the goals of AI companies and of mathematics are "severely misaligned." They worried about credit, about breaking the chain by which understanding passes from person to person, and about mass-producing true-or-false verdicts without the ideas that make them meaningful. This release is exactly the scale they were warning about. To be fair, OpenAI consulted an independent advisory group at the Institute for Advanced Study on how to publish, and it is versioning its corrections in public.

For Fields medallist Hugo Duminil-Copin, the shock was deeply personal. OpenAI's release included work on 16 questions directly relevant to his research. Speaking at a French Mathematical Society videoconference, he said (in English translation):

> “On Tuesday night, I cried, and it woke up my daughter”
>
> “They have annihilated my field of research.”

— Hugo Duminil-Copin, reported by David Larousserie in [Le Monde, 10 October 2026](https://www.lemonde.fr/sciences/article/2026/10/10/nouveau-coup-de-massue-d-openai-sur-les-mathematiciens-ils-ont-annihile-mon-domaine-de-recherche_6790951_1650684.html).

Another honest reaction came from Yuanning Zhang, a PhD student at Northwestern, [in the New York Times](https://www.nytimes.com/2026/10/08/science/mathematicians-respond-openai-release.html):

> What I'm feeling is less a judgment than a kind of vertigo. If these reported resolutions are verified, this would suggest that A.I.-assisted mathematical research is beginning to operate on an industrial scale.

He compared it to the end of Truffaut's *The 400 Blows*, where the boy runs to the sea and the film ends on "a freeze frame that passes no judgment on whether this is an escape or a dead end." He doesn't think that's a bad picture of where mathematics stands.

**Power is concentrated.** The model that produced all this isn't public. One company decides which problems it attacks, when results come out and what goes with them. Whatever you think of how OpenAI handled it, that's a lot of control over a field's agenda to sit with one lab.

## Why this matters beyond maths

Maths is the canary because results can be checked. Lean can confirm a proof is correct in a way that's much harder for a drug trial or an economic model. So maths is where we get to see first what happens when a field's frontier starts moving faster than its people can follow.

I don't know if that's an escape or a dead end either. But I'm fairly sure the same thing is coming to other fields, and that the hard questions will be the ones maths is facing now: who checks the work, who gets the credit and who sets the agenda.

Tracking what AI is solving and what it isn't is getting harder. [ProofAtlas](/ref/proofatlas) keeps a ranked list of open problems with dated status notes, which helps.
