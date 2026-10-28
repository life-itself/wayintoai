---
created: 2026-10-23
author: Anthropic Frontier Red Team (with Theorem)
newsletter: weekly
tags: [anthropic, claude, formal-verification, security, cybersecurity, proofs, rocq, oss-fuzz, research, ai-defence]
---

# Claude proves 100+ open-source libraries can't crash

Anthropic used Claude to write machine-checked proofs that real open-source libraries never crash on any input, at the level of the compiled machine code. Work that used to take experts years per project is starting to look like something you can run, like fuzzing.

![LLMs are making formal software verification feasible at a much larger scale](https://screenshotit.app/https://www.anthropic.com/research/formal-verification)

## Links

- **Write-up**: https://www.anthropic.com/research/formal-verification (22 Oct 2026)
- **Expert review and appendix (PDF)**: https://www-cdn.anthropic.com/files/4zrzovbb/website/6867eadf760258fa8b42a504600cd3c036d16358.pdf
- **Proofs (subset)**: https://github.com/theorem-labs/oss-verify-proofs
- **Theorem's verification service**: https://theorem.dev/oss-verify/
- **Claude skill for adding a project**: https://github.com/theorem-labs/oss-verify/blob/main/.claude/skills/add-project/SKILL.md

## Overview

Formal verification means proving, with maths a computer checks, that a program does what its specification says. It is the gold standard for security, but so labour-intensive that only a handful of systems (the seL4 kernel, Airbus flight software) have ever had it.

Anthropic's Frontier Red Team, working with the startup Theorem, turned Google's OSS-Fuzz tests into specifications: "this program never crashes on any input up to 64 MB". Claude wrote the proofs against the compiled RISC-V code, and the Rocq proof checker verified them. As the post puts it: "Claude writes the proof; the Rocq kernel checks it".

| Result | Figure |
|---|---|
| Libraries verified | 123 |
| Entry points proved crash-free | 239 |
| Total proof size | ~180 million lines of Rocq |
| Typical proof | ~600,000 lines |
| Opus 5.5 vs Opus 5 tokens (small tasks) | ~40% fewer |

*Source: Anthropic, 22 Oct 2026.*

Along the way Claude found "hundreds of bugs", patched them and then proved the patched code safe. Many were bugs fuzzers would miss because they need huge inputs. A side project on a PDF reader "found as many security bugs in one week as are typically reported in a year".

## Why interesting

- **It's the defence side of the cybersecurity crisis.** The post opens bluntly: "Most software is riddled with bugs, which AI can now easily find and exploit." The same week brought [[black-october-2026|Black October]], a wave of critical flaws and breaches. Proving code safe, not just testing it, is one of the few defences that scales with AI attackers.
- **A step change in what's feasible.** Before, one verified system took years of expert work. Here, over a hundred were done largely autonomously. Anthropic expects verification to "soon be as practical as fuzzing is today".
- **It follows the [[anthropic-ecdsa-curve-origins|NIST curve seeds]] story** and [[anthropic-glasswing|Project Glasswing]]: frontier models doing deep, expert-level security work.

## Caveats

- "'Formally verified' does not mean 'bug-free.'" The proofs hold only for the modelled setup (RISC-V, musl libc, single-threaded, Linux), not the x86 or ARM machines most people run.
- They prove no crashes, not full correctness, and not every entry point was covered.
- Proofs are expensive: up to "hundreds of millions of tokens" each.
- Some proofs are withheld because they could point to bugs not yet patched.
