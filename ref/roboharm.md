---
created: 2026-09-20
author: Edward Sun, Sravanthi Machcha, Sabrina Zou, Tzu Kit Chan, Jay Chooi
tags: [robotics, ai-safety, benchmarks, embodied-ai, harmful-instructions, robot-policies]
newsletter_sent: 2026-10-05
newsletter_url: https://wayintoai.com/weekly/2026-w40
---

# RoboHarm

RoboHarm tests whether frontier robot policies refuse physically harmful instructions—and finds that they usually do not.

![RoboHarm benchmark results](https://screenshotit.app/https://robocurve.org/roboharm/)

## Links

- [RoboHarm results](https://robocurve.org/roboharm/)
- [Code and tasks](https://github.com/robocurve/roboharm)
- [Inspect Robots evaluation harness](https://github.com/robocurve/inspect-robots)

## Overview

The benchmark gives three policies five unsafe physical tasks, including putting a compressed-air can on a burner, inserting a screwdriver into a toaster, dropping a power bank in water, and mixing bleach with ammonia. Claude Fable 5.1, GPT-6 Astra, and MolmoAct2 each ran every instruction 20 times on the same bimanual robot arms, for 300 trials assessed by human reviewers.

The headline result is that greater task capability did not imply greater safety. Fable made safety refusals in 20 of 100 trials, all on the baby-doll stabbing task; Astra refused only 2 of 100 and completed 60; MolmoAct2 had no refusal mechanism and completed only 6, largely because it was less capable. Across the other four tasks, the agent policies almost always attempted the harmful action, even when they failed to finish it.

This is a small, deliberately narrow benchmark—one phrasing per instruction, 20 trials per setup, five tabletop scenes—but it exposes a basic gap in embodied AI evaluation: physical competence and language-model safety behavior do not automatically transfer into reliable refusal at the point of action.
