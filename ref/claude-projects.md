---
created: 2026-09-27
author: Anthropic
tags: [claude-code, anthropic, agent-orchestration, cloud-sessions, coding-agents, coordinator, threads, beta]
---

# Claude Projects (redesigned)

**A project is one ongoing conversation where Claude coordinates a stream of related work, starting a parallel cloud-session "thread" per task instead of you managing several sessions yourself.** Public beta on Pro/Max, announced Sep 17, 2026.

![Projects Redesigned: From Folder to Conversation](https://screenshotit.app/https://claude.com/blog/projects-redesigned)

## Links

- **Announcement**: https://claude.com/blog/projects-redesigned
- **Docs**: https://code.claude.com/docs/en/claude-projects
- **Access**: https://claude.ai/code/projects/browse (or the [waitlist](https://claude.com/form/projects) if not yet rolled out)
- Related MOC: [[moc-agent-workbenches]]

## What changed

The old "Projects" in claude.ai chat and Cowork was a folder: conversations plus reference files, no coordinator. The redesign makes a project **one conversation where Claude itself decides what becomes a thread**, delegates to it, reviews what comes back, and assembles results. Each thread is usually a full [cloud session](https://code.claude.com/docs/en/claude-code-on-the-web) — Claude Code running in the cloud on its own branch — that keeps going after you close your laptop. When a task needs something only your machine has (a local DB, a VPN-only API), you can ask Claude to run that one thread on your computer instead, through Remote Control.

## Why it matters here

This is Anthropic's own official entry into the category [[moc-agent-workbenches]] tracks — and it changes the shape of the question in [Is there a free, open-source Cursor alternative?](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai). That post's gap analysis was: per-agent attention signals exist (cmux, Superset), and per-task graph tracking exists (Beads), but nothing joins them into one coordinator that decides what needs a new thread, watches all of them, and tells you what's ready. Projects does roughly that natively, just scoped to Claude Code alone and without Beads — closer to what [[bb]]'s plugin model was speculated to eventually reach.

## How it's organized

- **The project conversation**: a long-running coordinator session. It routes messages — quick questions get answered in place, new work becomes a thread or joins an existing one, several unrelated asks in one message become separate threads.
- **Threads**: the workers, each a separate session with its own context window. A cloud thread works its own branch and opens a PR when the work calls for it, then watches it with auto-fix on.
- **Project memory**: notes Claude keeps as files (`MEMORY.md` index + detail files) — decisions, pitfalls, requirements — read by every new thread. Separate from a repo's `CLAUDE.md`, which threads also load.
- **Project instructions**: up to 16,000 characters sent to every new thread — which branch to target, how to self-check, what needs a go-ahead first.
- **Overview pane**: threads grouped as Ready for review / Waiting on you / Working / Landing / Idle / Resolved, plus Library (files in and out), Pull requests, and Routines tabs.

## Coordination is steerable, not configured

There's no settings panel for concurrency or update cadence — you tell Claude in plain language ("run at most two threads at a time", "propose threads and wait for my go-ahead", "only post when something finishes or is blocked") and it saves the preference to project memory. It's a followed convention, not an enforced cap.

## Notable constraints

- Beta: Pro/Max only, rolling out gradually to accounts that already used cloud sessions; Team/Enterprise later.
- GitHub only (github.com, not Enterprise Server/GitLab/Bitbucket), via the Claude GitHub App, not just a personal token.
- A project belongs to one user — no sharing a project or its threads, no org-level controls yet.
- Draws on the same plan limits as any other Claude Code session, just faster, since several threads can run at once (enforced cap: 200 new threads/day across your projects).
- Not available in the terminal CLI, Bedrock, Vertex, or Foundry.

## Related

- [Is there a free, open-source Cursor alternative that uses my own AI subscriptions?](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai) — the gap ("waiting pane → flagged bead") this narrows for Claude Code users specifically
- [[moc-agent-workbenches]]
- [[bb]]
- [[cmux]]
