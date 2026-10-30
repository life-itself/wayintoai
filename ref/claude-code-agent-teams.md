---
created: 2026-10-31
author: Anthropic
tags: [claude-code, anthropic, agent-orchestration, multi-agent, agent-teams, experimental, how-to]
---

# Claude Code Agent Teams

**One Claude Code session (the lead) starts several full Claude Code sessions (teammates) that share a task list with dependencies and can message each other directly.** Experimental and off by default, as of Claude Code 2.1.31x (October 2026).

![Claude Code Agent Teams docs](https://screenshotit.app/https://code.claude.com/docs/en/agent-teams)

## Links

- **Docs**: https://code.claude.com/docs/en/agent-teams
- **Token costs**: https://code.claude.com/docs/en/costs#agent-team-token-costs
- **Changelog**: https://github.com/anthropics/claude-code/blob/main/CHANGELOG.md
- **HN launch thread** (396 points, Feb 2026): https://news.ycombinator.com/item?id=46902368
- Related: [[moc-agent-workbenches]], [[claude-projects]], [Fleet of agents survey](/posts/2026-08-10-fleet-of-agents-survey), [Run multiple threads in Claude](/posts/2026-08-26-run-multiple-threads-in-claude)

## How it works

- **Lead.** Your ordinary session. When teams are on and Claude calls its Agent tool with a `name`, it starts a teammate instead of a subagent; it does not ask first. The lead is fixed for the life of the team, and a session has one team.
- **Teammates.** Each is a full Claude Code instance with its own context window. It loads `CLAUDE.md`, MCP servers and skills like any session, plus the lead's spawn prompt. It does **not** get the lead's conversation, so the spawn prompt has to carry the brief. Teammates inherit the lead's permission mode; their permission prompts surface in the lead. No nested teams.
- **Shared task list.** Stored on disk at `~/.claude/tasks/{team-name}/`. Tasks are pending, in progress or completed, and can depend on other tasks. The lead assigns work, or teammates claim the next unblocked task themselves (with file locking). Finishing a task unblocks the tasks that wait on it. `Ctrl+T` shows the list.
- **Mailbox.** Each agent has an inbox (`~/.claude/teams/{team-name}/inboxes/`). Teammates message each other by name; messages arrive automatically. There is no broadcast: one message per recipient. When a teammate goes idle, the lead gets its final answer.
- **Hooks.** `TaskCreated`, `TaskCompleted` and `TeammateIdle` can block or redirect (exit code 2): for example, refuse to mark a task complete until tests pass.

## Turning it on

Add to `~/.claude/settings.json`:

```json
{ "env": { "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1" } }
```

Display: `teammateMode` is `in-process` by default (all in one terminal: Up/Down to pick a teammate, Enter to talk to it, `x` to stop it). Set it to `tmux`, `iterm2` or `auto` for one split pane per teammate. Split panes don't work in VS Code's terminal, Windows Terminal or Ghostty. Headless `claude -p` and Agent SDK runs don't spawn teammates.

## Limits and cost

- **Cost.** Every teammate is a full session, so a team uses "significantly more tokens" than one session, roughly in proportion to how many teammates are active. Docs suggest 3–5 teammates with 5–6 tasks each. In-process teammates' prompt cache lasts five minutes unless you set `subagentPromptCacheTtl` to `1h`.
- **Rough edges.** In-process teammates can't be brought back with `/resume` or `/rewind`; task status can lag; shutdown is slow. The team config is deleted when the session ends (the task files stay).
- **Side effect.** With teams on, subagents Claude would normally launch can become teammates. Set the flag to `0` when you want plain subagents.
- **Bad fits** (per the docs): sequential work, edits to the same file, and work with many dependencies between tasks.

## Teams vs the alternatives

| | Who coordinates | Talk to each other? | Lives how long | Good for |
|---|---|---|---|---|
| **Subagents** | The caller; results come back to it | No | One call | Research or checks whose answer you need now |
| **Agent Teams** | A lead session with a shared task list | Yes, by name | One session | One bounded job split into parallel parts that need to talk |
| **Separate sessions** (worktrees, Agent View) | You | No | As long as you like | Independent work streams, one per branch or project |
| **[[claude-projects]]** | A coordinator conversation in the cloud | Via the coordinator | Ongoing | A stream of related tasks on a GitHub repo, each ending in a PR |

## How to use it more (a workflow with Beads)

Teams are a tool for **one run**, not a backlog. Beads (or any tracker) stays the source of truth across days and projects; a team is how you burn down one epic quickly.

1. **Epic to team.** Plan and break down in Beads as usual (`bd dep` for order). Then, in the repo: "Make a team. Take the ready children of epic X; one teammate per independent bead; close each bead when its task completes." The Beads graph maps neatly onto the team's task list.
2. **Competing hypotheses.** For a stubborn bug or an open design question, spawn three teammates with different theories and tell them to argue it out. Direct messaging is what subagents can't do.
3. **Builder plus reviewer.** One teammate builds, another reviews and tests, and a `TaskCompleted` hook refuses "done" until the checks pass. This puts "critique before showing" into the process.
4. **Research fan-out with cross-talk.** For a survey post: one teammate per source or tool, told to message each other when they find overlaps or contradictions, with the lead writing the synthesis.
5. **Split by file ownership.** For a site or app change, give each teammate distinct files (content, styles, scripts) so they never edit the same file.

**Where teams don't fit:** a backlog across many repos (a team is one session in one place, and dies with it), overnight or always-on work (no resume), anything mostly sequential, and quick lookups (a subagent is cheaper). For those, use Beads plus separate sessions, or [[claude-projects]] for cloud threads.
