---
title: "Where to keep API keys so your AI agents can use them on every machine"
description: A tested recipe for sharing secrets with AI agents across laptops, servers and cloud sessions using dotenvx, a free open-source tool, without committing them in plain text.
date: 2026-10-20
status: draft
authors: [rufus-pollock]
---

# Where to keep API keys so your AI agents can use them on every machine

**Q: My agents need API keys, app passwords and webhooks. How do I make them available on all my laptops, remote machines and cloud AI sessions, without pasting them into chat or committing them?**

**A: Keep one encrypted `.env` file in a private git repo, managed with [dotenvx](https://dotenvx.com). Each machine or cloud environment gets one decryption key. Agents run commands through `dotenvx run`, so values reach the program but are never printed.**

## What dotenvx is

dotenvx is a free, open-source command-line tool from the author of the original `dotenv`. It encrypts each value in a `.env` file with a public key. The encrypted file is safe to commit and sync with git. Decrypting needs the matching private key, which lives in a separate `.env.keys` file that never goes into git, or in the `DOTENV_PRIVATE_KEY` environment variable on machines where you can't keep files.

So there's one thing to copy to each new place (the private key), and everything else syncs with ordinary git.

Why not the alternatives: a password manager CLI (e.g. 1Password's `op run`) works well but is paid; Bitwarden Secrets Manager's free plan is a reasonable fallback. Anthropic's Managed Agents "vaults" only reach agents run through that API, not Claude Code sessions.

## One-time setup

```bash
npm install -g @dotenvx/dotenvx        # or: brew install dotenvx/brew/dotenvx
mkdir secrets && cd secrets && git init
printf '.env.keys\n' > .gitignore      # the private key never goes into git
dotenvx set TEST_SECRET "hello"        # creates .env (encrypted) and .env.keys (private key)
dotenvx ext precommit --install        # git hook that refuses to commit an unencrypted .env or .env.keys
git add -A && git commit -m "secrets"
gh repo create secrets --private --source . --push
```

Then put a copy of the `DOTENV_PRIVATE_KEY` line from `.env.keys` in your password manager. If you lose every copy of it, the encrypted values are gone.

## Adding or changing a secret

```bash
cd ~/secrets && dotenvx set BLUESKY_APP_PASSWORD 'xxxx-xxxx' && git commit -am "add bluesky" && git push
```

Do this yourself, not through an agent: typing a real secret into an AI chat sends it to the AI provider. Other machines get it on their next `git pull`.

## Adding a new machine or cloud environment

- **Another laptop or server:** install dotenvx, clone the repo, and copy `.env.keys` into it over a private channel (password manager, `scp`). Never through chat or email.
- **Claude Code on the web (cloud sessions):** at claude.ai/code, open the environment's settings and add `DOTENV_PRIVATE_KEY=...` under environment variables. Add `npm install -g @dotenvx/dotenvx` to its setup script. Make sure the Claude GitHub app can read your private secrets repo.
- **Codex cloud:** in the environment's settings, add `DOTENV_PRIVATE_KEY` as an environment variable, not as a "secret": Codex secrets are only available to the setup script and are removed before the agent runs.

## Revoking a lost machine's key

All machines share one key, so revoking means making a new key pair. The free CLI (v2.38) has no `rotate` command; do it by hand on a trusted machine:

```bash
cd ~/secrets
dotenvx decrypt                           # .env now holds plain values: don't commit this state
sed -i '' '/^DOTENV_PUBLIC_KEY/d' .env    # drop the old public key (Linux: sed -i without '')
rm .env.keys                              # drop the old private key
dotenvx encrypt                           # new key pair, .env encrypted again
git commit -am "rotate key" && git push
```

Then copy the new private key to each remaining machine and cloud environment, and to your password manager.

Finally, change the actual secrets at their source (new app passwords, new webhook URLs). The old key can still decrypt the old values from git history, so rotating the dotenvx key alone protects only future values. This last step is the one that really matters.

## How agents use it

Tell your agents (in your `AGENTS.md`):

```markdown
- Secrets are in ~/secrets/.env (encrypted). Use them only via `dotenvx run --quiet --strict -f ~/secrets/.env -- <command>`.
- Never print, echo or log a secret value, and never ask me to paste one into chat.
```

`dotenvx run` decrypts the values into the environment of that one command and nothing else. To check that a secret works without revealing it, compare a hash or just test that it's set:

```bash
dotenvx run --quiet --strict -f ~/secrets/.env -- sh -c 'test -n "$BLUESKY_APP_PASSWORD" && echo set'
```

An honest caveat: this keeps secrets out of git, chat and logs. It does not stop an agent that has shell access from reading them if it tries; nothing you give an agent the key to can. Only give agents secrets you'd let them use.

## What we tested (2026-10-20)

- **Local Mac:** passed. A dummy `TEST_SECRET` decrypted correctly with the key in `.env.keys`, and again with the key only in `DOTENV_PRIVATE_KEY` and `.env.keys` removed (how cloud environments work). With no key, `dotenvx run --strict` stops with `DECRYPTION_FAILED` and exit code 1. Rotating to a new key pair (below) worked and the old key then failed.
- **Claude Code cloud session (claude.ai/code):** passed. `DOTENV_PRIVATE_KEY` was set as an environment variable in the cloud environment's settings, with network access on Trusted. dotenvx wasn't preinstalled; `npm install -g @dotenvx/dotenvx` worked in the session (v2.38.1), and the same check printed PASS with exit code 0.
- **Codex cloud:** not tested. The setup above follows Codex's documented settings but hasn't been run.

## Gotchas found in testing

- **`dx` name clash.** The npm package installs a `dx` shortcut alongside `dotenvx`. If you have Deno installed through Homebrew, `/opt/homebrew/bin/dx` already exists and `npm install -g` fails with `EEXIST`. Install to your home directory instead: `npm install -g --prefix ~/.local @dotenvx/dotenvx` (with `~/.local/bin` on your `PATH`). Don't use `--force`; it would overwrite Deno's.
- **Cloud sessions don't come with dotenvx.** Install it per session (`npm install -g @dotenvx/dotenvx`) or put that line in the environment's setup script. It needs network access to npm, which the Trusted setting allows.
- **The cloud session must be able to clone the private secrets repo.** If the Claude GitHub app only has access to selected repositories, add the secrets repo.
- **Homebrew install can fail** on a Mac whose Command Line Tools are older than Homebrew expects. npm works without them.
- **`dotenvx run` prints a status line** ("injecting env (1) from .env"). Add `--quiet` to keep agent logs clean. It never prints values.
- **Without `--strict`, a missing key doesn't stop the command.** dotenvx prints `DECRYPTION_FAILED` but still runs your command with exit code 0, and the variable holds the encrypted string (`encrypted:...`), so a naive "is it set?" check passes. Always use `--strict`, and test a new machine against the real value or its hash.
- **`dotenvx ext precommit` is deprecated** in v2.38 in favour of `dotenvx protect`; the old hook still works.
