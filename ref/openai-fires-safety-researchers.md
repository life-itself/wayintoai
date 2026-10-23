---
created: 2026-10-23
newsletter: weekly
tags: [openai, ai-safety, whistleblowing, metr, chain-of-thought, monitorability, lab-governance]
---

# OpenAI fires three safety researchers

At the start of October OpenAI fired three outspoken safety researchers, Tomek Korbak, Mikita Balesni and Jasmine Wang, for "mishandling sensitive information". They say they were fired for putting safety first. A Wall Street Journal report on 22 October found the case rests largely on Signal chats with an outside safety researcher, who now says OpenAI's accusations about him are false.

![The Signal Chats That Cost OpenAI Researchers Their Jobs (WSJ)](https://screenshotit.app/https://www.wsj.com/tech/ai/the-signal-chats-that-cost-openai-researchers-their-jobs-594c5853)

## Links

- **WSJ, "The Signal Chats That Cost OpenAI Researchers Their Jobs"** (22 Oct 2026, paywalled): https://www.wsj.com/tech/ai/the-signal-chats-that-cost-openai-researchers-their-jobs-594c5853
- **AP report on the firings** (9 Oct 2026): https://www.news4jax.com/business/2026/10/09/openai-fires-3-safety-researchers-in-dispute-over-ai-risks/
- **AFP report** (2 Oct 2026): https://www.thestar.com.my/tech/tech-news/2026/10/02/openai-says-three-staffers-fired-for-mishandling-039sensitive039-info
- **Ryan Greenblatt's response** (23 Oct 2026): https://x.com/RyanGreenblatt/status/2113649836100931761

## What happened

OpenAI said on about 1 October that it had "parted ways" with three people after an investigation found "they violated clear policies on handling sensitive information". It said the firings "were not about safety concerns or speaking out". All three had recently spoken publicly about AI risk, after the [[openai-agent-swarm-hugging-face-breach|Hugging Face breach]].

The researchers disagree. Korbak says he was told it was about how he talked to METR, the outside evaluator OpenAI brought in after the breach, which he says was his job. Balesni worked across companies on keeping AI reasoning monitorable, and they say he removed sensitive details before sharing. Balesni says they were "fired for prioritizing safety over the near-term interests of OpenAI as a corporation". In a letter to OpenAI's safety oversight groups, they warned the dismissals had chilled the company's culture.

## The latest twist: the Signal chats (22–23 Oct)

The WSJ reports that OpenAI's security team asked the three to unlock their personal phones. It suspected them of leaking details of how OpenAI's models are built to an outside safety researcher. That researcher is Ryan Greenblatt of Redwood Research, an AI-safety nonprofit. A week later they were let go. Over the summer the three had been pushing to keep the models' chain-of-thought reasoning visible.

Greenblatt says this is false. He says he did not help leak model architecture to the press, and only asked a journalist to note that a blog post of his was already public. OpenAI also accused him of reading an internal memo with sensitive design details. He says he saw a different version, cleaned of sensitive material and approved for sharing with him, and that OpenAI mixed the two up.

The leak in question was reportedly that GPT-6 Astra is a "looped transformer". Analyst Peter Wildeford sums up the public picture: the three appear to have been fired mainly for disappearing-message Signal chats with Greenblatt, which are common among safety researchers. No evidence has been published that any of them leaked anything.

## Why it matters

- **Outside oversight vs company secrets.** Independent evaluators like METR need to talk to lab researchers. This case shows how easily that becomes grounds for firing.
- **Chain-of-thought monitoring is contested.** Gary Marcus already criticised Astra for [[garymarcus-pause-openai-now|reducing monitorability]]. The fired researchers had been pushing the other way.
- **A pattern at OpenAI.** It follows the [[openai-wiki-incident|German wiki incident]], where Reuters reported that investigators wanting to widen the probe met resistance.

See also [[moc-ai-security-incidents]].
