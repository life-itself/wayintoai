---
title: Monitoring all my Claude Code sessions, across machines
publish: false
---

Context note, 2026-10-26, from a planning sweep in `rufuspollock/planning`. Not committed on purpose.

## The question

Which tools let me see every Claude Code session in one place, wherever it runs, including the headless MacBook Air with Remote Control on? Wanted for my own AI workflow and as a possible Way Into AI entry.

## Why it came up

On 2026-10-25 I asked for a summary of threads I had started the previous afternoon from the headless machine (Flowershow, Reports That Matter and others). The desktop app's session list showed only sessions on this Mac, so the headless sessions were invisible. That visibility gap is the problem to solve.

## Candidates from a first web search (nothing verified, all young projects)

Cross-machine:

- [claude-vigie](https://pkg.go.dev/github.com/haribo/claude-vigie): Go, MIT; transcript watcher plus hook reporter, terminal dashboard and read-only web view; aimed at multiple machines.
- [Marc Nuri's multi-device dashboard](https://blog.marcnuri.com/ai-coding-agent-dashboard): aggregates several machines into one real-time view.
- [Shane Hartman's `cs`](https://shanehartman.net/managing-claude-code-sessions-across-multiple-machines/): tmux for persistence plus shared MongoDB; Linux hosts; state detection is heuristic.
- [Claude Fleet](https://community.home-assistant.io/t/claude-fleet-see-all-your-claude-code-sessions-on-one-dashboard/1027113): hooks publish state over MQTT to Home Assistant.

Single machine (read `~/.claude/projects/` transcripts): [cltop](https://pypi.org/project/cltop/), [ccboard](https://docs.rs/crate/ccboard/latest), [claude-code-monitor (Stargx)](https://github.com/Stargx/claude-code-dashboard), [claude-code-monitor (onikan27)](https://github.com/onikan27/claude-code-monitor) (macOS only, Tailscale for remote), [claude-code-monitor (bruceyxli)](https://github.com/bruceyxli/claude-code-monitor) (LAN, remote approval).

Unverified: a third-party guide describes built-in Remote Control, Dispatch and "Agent View" ([source](https://radar.firstaimovers.com/claude-code-remote-control-dispatch-multi-device-guide-2026)). Check Anthropic's docs.

## Open questions for whoever picks this up

- Does Claude's built-in Agent View, or the desktop app with Remote Control, already show headless-machine sessions? Test before installing anything.
- If not, does a hook-based tool (vigie-style) close the gap with little setup and acceptable security (transcripts contain secrets and private content)?
- Is there a Way Into AI entry in it, or is it a private workflow note?
- Link to the existing how-to-use-ai drafts, and to the board project in planning (`day/2026-10-26-ai-work-board.md`), which wants to read session state too.
