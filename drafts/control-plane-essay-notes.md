---
title: "Notes: what I want from an agent control plane, and why nothing fits yet"
publish: false
---

Rough notes from Rufus, 2026-10-30, captured while drafting the OpenBases Hacker News launch. Raw material for an essay. Evidence: [[hn-agent-control-planes-survey]], [[2026-08-10-fleet-of-agents-survey]].

## The claim

Running many agent sessions on one laptop is solved; Claude Code does it. What isn't solved is the **control plane**. The edge is something like **Gas Town plus a control plane**.

## What I want

- **A graph of work across all my projects.** I start by planning in the graph and then hand off: "I've done the planning, now build the roadmap, now execute."
- **An overview that tells me what needs me.** A dashboard where I can see "that agent's not working". It reminds me of the context and what I need to do next.
- **Coordination between agents across projects**, the way Gas Town does it on a shared ledger (Beads). Gas Town was the breakthrough because the ledger, not any one session, holds the state.
- **Harnesses, so more of it runs unattended.** Planning, then roadmap, then execution, with less of me in the middle.
- **A learning loop.** As the work runs, what you learn flows back and improves the harness, the prompts and the process. Improvement is part of the work graph too, not a separate activity.

## Why nothing fits

- Laptop workbenches (Conductor, Vibe Kanban, Superset, cmux) give you many panes, but no graph and no coordination.
- Paperclip models a company as an org chart, which is a metaphor, not a work graph. It never took off on HN.
- Gas Town has the ledger and the coordination, but it's Claude-only, idiosyncratic and not built to run headless for a team.
- Claude Agent Teams covers teamwork inside one bounded run, not a backlog across projects. (Am I using it well enough? Needs its own write-up.)
- OpenBases (Datopian) is our own attempt: Beads as the work graph, a headless runner, sandboxed agents, an attention inbox. Its improvement loop is designed but not built.

## Essay shape (first guess)

1. The problem: you scale past a few agents and coordination becomes the bottleneck.
2. What exists, by category, with screenshots of each.
3. Our experience: Gas Town, then building OpenBases, with what broke and what it cost.
4. What I actually want: the five points above.
5. Where the edge is: the work graph, harnesses and the learning loop.
