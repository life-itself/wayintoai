---
created: 2026-11-18
author: Rufus Pollock
tags: [fable-5-2, agent-orchestration, prompts, multi-agent]
---

# Fable 5.2 conductor prompt

A short orchestration prompt for delegating a complex task to multiple Opus 5.5 workers while the lead model coordinates, reviews, and handles decisions.

## Prompt

```text
you’re the conductor. you do the thinking: the plan, the architecture, the strategy. split the job into tasks. give each one to its own Opus 5.5 worker. nudge every worker until its task is done.

while they work, sit idle. don’t do their work for them.

when a worker reports back, check it, then give out the next task.

handle anything that doesn’t need me. only stop when you need a decision from me.
```

## Context

The prompt sketches a manager-worker workflow: delegate discrete tasks, keep the lead model focused on coordination, review worker results, and escalate only decisions that need the user. See [[claude-fable-5-2]] for the model context.

## Links

- **Claude Fable 5.2**: [[claude-fable-5-2]]
- **Announcement**: https://www.anthropic.com/claude-fable-and-mythos-5-2
