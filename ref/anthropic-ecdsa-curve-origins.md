---
newsletter_sent: 2026-10-21
newsletter_url: https://wayintoai.com/weekly/2026-w43
created: 2026-10-20
author: Anthropic Frontier Red Team
newsletter: weekly
tags: [anthropic, claude, cryptography, security, research, ecdsa, nist, ai-discovery]
---

# Claude reveals the origins of the NIST elliptic-curve seeds

A 29-year cryptography mystery, solved by an AI in under half an hour: the "random" seeds behind the NIST P-256 and related curves came from an ordinary C random-number generator started from the clock.

![Claude reveals ECDSA curve origins](https://screenshotit.app/https://www.anthropic.com/research/ecdsa-curve-origins)

## Links

- **Write-up**: https://www.anthropic.com/research/ecdsa-curve-origins (16 Oct 2026)
- **The bounty**: https://words.filippo.io/seeds-bounty (NIST Elliptic Curves Seeds Bounty, organised by Filippo Valsorda)

## Overview

The NIST curves (P-192 to P-521) secure much of the web. Their constants were derived from "seeds" whose origin was never explained, which led to years of suspicion that they hid a deliberate backdoor. Several Anthropic employees had tried and failed to find them.

A curious employee then asked an internal research model to work it out without a hint. "In under half an hour" it found the answer: the seeds are not hash outputs but output from `lrand48`, a common C library generator, seeded with a Unix timestamp from August 1997. It spotted an unlikely bit pattern (a 1-in-5,810 chance), then used lattice reduction to recover the generator's state. For P-256, the seed was candidate 1,842 of the run.

Anthropic is clear: "This is not a cryptographic break, new attack, or weakness in the ECDSA curves." If anything, it makes a backdoor *less* plausible. The $36,864 bounty goes to the Internet Security Research Group (the people behind Let's Encrypt). A few pieces are still unexplained, including the B-163 seed and several base points.

## Why interesting

> A cool little story, but also a demonstration of how clever an AI can be now. This is the kind of thing no one had worked out in years. It took in-depth research and quite intelligent exploration to find. It's an innocent example, but it's the kind of thing you would do in cybersecurity attack and defence. — Rufus Pollock

It is also a counterpoint to the maths story ([[openai-math-results-release]]): the same capability in a field where a finding can matter for security.

## Related

- [[moc-ai-security-incidents]]
- [[openai-math-results-release]]
- [[aisi-gpt-6-astra-supply-chain-attacks]]
