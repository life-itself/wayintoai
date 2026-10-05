---
created: 2026-09-18
author: BB
tags: [agent-workbench, agent-orchestrator, ide, coding-agents, plugins, open-source, local-first]
newsletter_sent: 2026-10-05
newsletter_url: https://wayintoai.com/weekly/2026-w40
---

# bb — The IDE That Builds Itself

**A local-first, open-source agent workbench that can run several coding agents and be extended by asking an agent to build a plugin.**

![bb homepage](https://screenshotit.app/https://getbb.app/)

## Links

- **Website:** https://getbb.app/
- **Blog:** [An Agentic IDE That Builds Itself](https://getbb.app/blog/an-agentic-ide-that-builds-itself) — the clearest explanation of the product and its philosophy.
- **GitHub:** https://github.com/get-bb/bb
- **License:** MIT

## Overview

bb is an agent-oriented IDE and orchestrator for working across threads, worktrees, and coding agents. It supports Claude Code, Codex, Cursor, Pi, OpenCode, Grok, omp, Hermes, and ACP-compatible agents, using the subscriptions you already have.

Its distinguishing claim is malleability: much of bb itself is implemented as plugins, and users can ask an agent to add a capability. The product post gives examples including a task-management GUI, tiled thread navigation, automated code review, a markdown vault, and a small digital-audio workstation. A plugin can add both a sidebar surface and a CLI/skill for agents to use.

It belongs to the crowded agent-workbench space, but is more interesting as an experiment in software that lets its own agents reshape the environment they work in than as another fixed agent dashboard.

## Related

- [[moc-agent-workbenches]] — the wider category of environments for running and managing coding agents.
- [[pi.dev]] — a smaller, terminal-first coding harness built around extensibility.
- [[paperclip]] — an orchestration layer for agent teams and autonomous businesses.
