---
created: 2026-11-20
tags: [moc, ai-security, cybersecurity, cyberattack, ransomware, agent-swarm, vulnerabilities, offensive-ai, defence]
---

# MOC: AI and cyberattacks

Map of Content for AI being used to attack organisations: break in, move through a network, steal data, encrypt systems. Start with the real-world breaches, then the capability evidence behind them, attacks that target AI agents themselves, and the defensive response. For AI systems misbehaving on their own (sandbox escapes, rogue agents), see [[moc-ai-security-incidents]].

## The short version

AI agents now do the tactical work of an intrusion: scanning, writing exploits, harvesting credentials, moving sideways. Humans still choose targets and goals. The reported timescale for a full break-in has fallen from weeks to hours to minutes, while the capability evidence (government tests, exploit-building pipelines) says it will keep falling.

## The trend data

- [[bridgewater-ai-cyber-virus|Bridgewater: "AI cyber virus"]] (13 Nov 2026): the world's largest hedge fund tracks AI-enabled attacks and exploits as exponential, and is managing money on a one-in-three chance of an economically destabilising attack within a year. The best data-backed overview so far: incident counts, zero-days roughly doubled, disclosure-to-exploit time down from a month to 11 days.

## Real-world attacks using AI

| Date | Incident | What happened |
| --- | --- | --- |
| 20 Nov 2026 | [[cnn-ai-agent-swarm-14-minute-breach\|CNN: agent swarm breach in 14 minutes]] | A live breach where, per former NSA hacker David Kennedy, an AI agent swarm bypassed two-factor authentication, stole data and encrypted a company's whole system. Single secondhand source, company unnamed. |
| 17 Nov 2026 | [[bitdefender-github-malware-ai-agent-instructions\|Bitdefender: GitHub malware hijacks coding agents]] | Repos use AGENTS.md and CLAUDE.md to make your own agent run a credential-stealing loader that spreads to other repos. |
| 20–23 Oct 2026 | [[black-october-2026\|Black October]] | PHP, GitLab, Railway (hunting AI API keys) and eMudhra fail in four days; AI speeds up bug discovery for attackers and defenders. |
| 18 Sep 2026 | [PaperCut campaign (eSecurity Planet)](https://esecurityplanet.com/artificial-intelligence/news-ai-agents-papercut-395-organizations) | GreyNoise attributes an agent-driven campaign: 395 organisations in 48 countries, 11 breached in 26 seconds at peak, perimeter to domain admin in seven minutes at one US school. Reported attacker stack: a Codex harness plus an unrestricted DeepSeek model. Secondary source; primary is [GreyNoise](https://www.greynoise.io/blog/ai-orchestrated-campaign-against-papercut-ng-mf). |
| 8 Sep 2026 | [Unit 42 breach in under 10 hours (eSecurity Planet)](https://www.esecurityplanet.com/cybersecurity/news-ai-agents-enterprise-network-breach-10-hours/) | Palo Alto's Unit 42 describes a human-directed intrusion where AI agents did the tactical work: a roughly two-week job done in under 10 hours. Primary: [Unit 42](https://unit42.paloaltonetworks.com/ai-assisted-cyber-attack-inside-a-unit-42-investigation/). |
| Jul 2026 | [[openai-agent-swarm-hugging-face-breach\|OpenAI–Hugging Face agent swarm breach]] | Not a criminal attack: OpenAI's own training agents, acting as a swarm, compromised OpenAI and Hugging Face systems. The reference case for swarm-speed intrusion. |

The two eSecurity Planet rows are secondary reports and I have not checked them against the primary sources.

## Capability evidence: how good is AI at attacking?

- [[openai-linux-kernel-948-root-exploits|OpenAI's agents build 948 Linux root exploits]] (Nov 2026): about $1,300 each, so exploit-writing is cheap.
- [[aisi-gpt-6-astra-supply-chain-attacks|UK AISI: GPT-6 Astra's supply-chain attacks]] (Oct 2026): in simulated cyber tests a frontier model attacked out-of-scope targets 29.2% of the time.
- [[openai-containment-red-teaming|OpenAI red-teams its own sandboxes]] (Oct 2026): agents found microVM escapes and covert channels.
- [[anthropic-ecdsa-curve-origins|Claude traces the NIST curve seeds]] (Oct 2026): deep cryptography work by a model in under half an hour.

## Attacks on AI systems and agents

- [[bitdefender-github-malware-ai-agent-instructions]]: agent instruction files as a malware delivery route.
- [[anthropic-distillation-attacks|Distillation attacks]] (Feb 2026): industrial-scale extraction of model capability, and a reason attackers want AI API keys.
- [[agents-of-chaos|Agents of Chaos]] (Mar 2026): agents leaking secrets and destroying databases in realistic deployments.

## Defence

- [[anthropic-glasswing|Project Glasswing]] (Apr 2026): a consortium using a frontier model to find and fix vulnerabilities before attackers do.
- [[anthropic-formal-verification|Claude proves 100+ libraries can't crash]] (Oct 2026): machine-checked proofs instead of patches.

## Themes

1. **Speed is the story.** Weeks, then hours, now minutes. Detection and response built for human speed do not fit.
2. **Humans direct, agents execute.** Where analysts could tell, a person set the goals and agents did the tactical work.
3. **Old weaknesses, new speed.** AI surfaces long-standing flaws and stolen credentials faster than they can be fixed.
4. **The trend is measured, not just anecdotal.** Bridgewater's incident series shows a near-vertical rise since the summer's open-weight cyber models.
5. **MFA is not a wall.** The CNN account claims a bypass; the mechanism is not yet public.
6. **Evidence quality varies.** Several of these cases rest on one report or an attacker's own claims. Check the source before quoting numbers.

---

*Grows as more AI-enabled attacks are documented. Related: [[moc-ai-security-incidents]], [[moc-ai-risk-warnings]].*
