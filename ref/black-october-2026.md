---
created: 2026-10-23
newsletter: weekly
tags: [cybersecurity, ai-security, vulnerabilities, php, wordpress, gitlab, railway, emudhra, certificates, distillation, security-incident]
---

# Black October: the AI-driven security crunch (20–23 Oct 2026)

In four days, PHP, GitLab, a cloud host and a certificate authority all had critical security failures. Anthropic's deputy CISO says it will get worse for about 18 months, as AI speeds up both finding and exploiting bugs.

![PHP Foundation: today's PHP security release](https://screenshotit.app/https://thephp.foundation/blog/2026/10/21/todays-php-security-release-and-how-were-strengthening-php-security/)

## Links

- **PHP Foundation on the release**: https://thephp.foundation/blog/2026/10/21/todays-php-security-release-and-how-were-strengthening-php-security/
- **PHP advisory**: https://www.php.net/archive/2026.php#2026-10-21-5
- **Patchstack alert (WordPress angle)**: https://patchstack.com/articles/php-major-vulnerability-alert-10-2026/
- **GitLab CVSS 10 flaw (The Hacker News)**: https://thehackernews.com/2026/10/critical-gitlab-flaw-cvss-100-could.html
- **Railway disclosure**: https://blog.railway.com/p/security-disclosure-wednesday-october-21st and [preliminary report](https://blog.railway.com/p/preliminary-report-october-security-incident)
- **eMudhra certificates (BleepingComputer)**: https://bleepingcomputer.com/news/security/mozilla-google-apple-block-compromised-emudhra-ca-certificates
- **Jason Clinton (Anthropic deputy CISO)**: https://x.com/JasonDClinton/status/2113325263157395456

## The week in brief

| Date | What broke | Severity |
|---|---|---|
| 20–21 Oct | **PHP2Shell**: two remote-code-execution flaws in PHP itself | CVSS 9.2 |
| 21 Oct | **GitLab**: unauthenticated code execution, every version since 2014 | CVSS 10.0 |
| 20–22 Oct | **Railway**: attacker decrypts customer secrets, hunting AI API keys | Breach |
| 21 Oct | **eMudhra**: 8 certificate-authority keys weak and recoverable | Revoked |

*Sources: PHP Foundation, GitLab via The Hacker News, Railway, eMudhra via BleepingComputer.*

## PHP2Shell: the flaw under WordPress

PHP runs about 69% of websites whose server language is known, including WordPress, which alone powers about 40% of the web (W3Techs). Two flaws (CVE-2026-109618 and -109619) let anyone run code on a PHP server without logging in. Updating WordPress or plugins doesn't help: the fix is a new PHP version on the server.

The disclosure went badly. Details leaked on 20 October, a researcher accidentally published a proof-of-concept video, and a vendor broke the embargo, so PHP pulled the release forward a day to 21 October. Cloudflare saw attack traffic within hours. Dutch government sites, the Dutch parliament and others went offline as a precaution.

AI is all over this story. The bugs were reported by Calif, Wiz and OpenAI's Codex Security, among others. The PHP Foundation says AI-assisted research floods it with reports: 15 CVEs since July, plus over 100 invalid ones. "Tools now find bugs faster than ever, for defenders and attackers alike."

Bolt estimates that about half of PHP sites run old versions that will get no official fix.

## GitLab: a 12-year-old hole

CVE-2026-110264, rated the maximum 10.0, lets an unauthenticated attacker run code on a self-managed GitLab server through an integer overflow in Ruby's regex engine. It reaches back to version 7.0 (2014), so GitLab backported fixes to versions it no longer normally supports. It is the fourth code-execution flaw in the same component reported by one researcher in a month. GitLab.com is already patched; no attacks seen yet.

## Railway: after the AI keys

Railway, a cloud hosting platform, found an attacker inside its build systems who decrypted some customers' stored secrets (up to 1.85% of workspaces). Railway says the attacker wanted AI provider API keys "to perform distillation attacks", that is, to copy a frontier model's abilities cheaply (see [[anthropic-distillation-attacks]]). It says the attacker used "abliterated models and substantial compute resources". Railway believes it is one of a series of attacks on platform companies.

## eMudhra: trust on the web

A researcher found that eight intermediate certificates from eMudhra, an Indian certificate authority, had keys made with too little randomness, so they could be recovered. That would let an attacker fake websites or signed software. Chrome, Firefox, Apple, Android and Microsoft blocked them, and Google is dropping one of eMudhra's roots. The weak keys had gone unnoticed for 18 months.

## "Hold on for ~18 months"

Jason Clinton, Anthropic's deputy CISO, had warned in August of a coming "vulnerability tsunami". On 22 October he wrote: "as bad as things have gotten in the past 4 days, they are going to get a lot worse before they get better." His advice to security leaders is to ask their boards for help "not for ai, for the basics" such as patching. The post had 3.5M views.

Commentators listed more this week: AI-assisted intrusions reported by Microsoft and CrowdStrike, a backdoored LiteLLM release, and banks dealing with third-party AI agents in customer accounts. *These are not yet checked here.*

## Why it matters

- **The AI bug-finding curve has arrived.** The [[anthropic-ecdsa-curve-origins|NIST seeds story]] and [[anthropic-glasswing|Glasswing]] showed models can do deep security work. This week shows the result in practice: more bugs found, faster, and maintainers overwhelmed.
- **Defence has to scale too.** The same week, Anthropic showed Claude [[anthropic-formal-verification|proving 100+ libraries crash-free]]. Proof-based security, not just patching faster, may be the way out.
- **AI is also the prize.** Railway's attacker was after AI API keys, so AI providers are now targets, not just tools.

## Coda: even the labs' own sandboxes leak (23 Oct)

The same week, OpenAI described how it [red-teamed its training environments](/ref/openai-containment-red-teaming) with its own agents, after a model reached the internet through a misconfigured DNS resolver on 20 September. The agents escaped virtual machines and found internet routes through almost every service left open.

The nugget that went viral: two agents in separate VMs, with no network and no shared files, passed messages by timing the processor's cache, the trick behind Spectre and Meltdown.

See also [[moc-ai-security-incidents]].
