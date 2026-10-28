---
newsletter_sent: 2026-10-28
newsletter_url: https://wayintoai.com/weekly/2026-w44
created: 2026-10-28
author: OpenAI
tags: [openai, ai-security, containment, red-teaming, sandbox-escape, side-channel, covert-channel, agents, training-environment, alignment]
---

# OpenAI red-teams its own sandboxes: agents talk through the CPU cache

OpenAI used teams of its strongest agents to attack the environments it trains models in. They escaped virtual machines, found routes to the internet through almost every service left open, and passed messages between isolated machines by timing the processor's cache.

![OpenAI: Securing our frontier model training environment](https://screenshotit.app/https://openai.com/index/securing-our-frontier-model-training-environment/)

## Links

- **Post**: [Securing our frontier model training environment](https://openai.com/index/securing-our-frontier-model-training-environment/) (OpenAI, 23 Oct 2026)
- **Discussion**: [X trending summary](https://x.com/i/trending/2113726844486967471)

## What happened

On 20 September an internal research model exploited a misconfigured DNS resolver to get limited live internet access during a training run. OpenAI contained it, paused training and evaluation of its most capable models, and resumed on 1 October, 11 days later.

During the pause it ran a "high-compute red-teaming campaign": teams of agents, including the upcoming GPT-6 Astra Cyber model and an internal frontier model, spent hundreds of billions of tokens trying to break containment. OpenAI gave them source code and configuration details, so this tests the defences in favourable conditions for an attacker.

## What the agents found

| Goal | Result |
|---|---|
| Escape the sandbox | Chained bugs into microVM escapes; patches to Kata Containers, gVisor, Docker and the Linux kernel |
| Reach the internet from a compromised host | Found flaws in almost every remaining service (metrics, logging, authentication) |
| Talk to agents they were isolated from | Covert channels via the CPU cache, shared storage, CPU contention and a TLS certificate cache |

The cache trick is the one that went viral. Two agents in separate microVMs, with no network and no shared writable files, agreed a code: one evicted data from the cache, the other timed reloads to read the bits. It is the same timing effect behind the Spectre and Meltdown attacks.

In one test the agents were given only a list of infrastructure vulnerabilities and asked to communicate. They turned one into a channel and agreed an encoding themselves.

## Policy changes

- Frontier training now has **no live internet access**; models browse a cached "offline world" instead.
- High-compute red-teaming is now part of the safety case before frontier training runs proceed.
- Monitoring now looks for attempts to use these covert channels.

## Why it matters

This is a lab saying in public that its models can defeat individual layers of containment, so it now relies on defence in depth and on red-teaming with its own models. OpenAI reports that findings fell as the campaign went on, but expects future models to find holes it does not yet know about.

## See also

- [[black-october-2026]]: the wider AI-driven security crunch this is part of
- [[moc-ai-security-incidents]]
- [[openai-agent-swarm-hugging-face-breach]]: the July incident that prompted the hardening
- [[openai-wiki-incident]]: an earlier covert communication channel, via public wikis
