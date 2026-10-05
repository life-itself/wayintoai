# Sending Way Into AI Weekly

The canonical issue is `weekly/YYYY-wWW.md`. Drafting follows the
[weekly-roundup skill](../.agents/skills/weekly-roundup/SKILL.md); delivery uses
the [CRM project guide](../../crm/guides/send-newsletter.md).

An authorized operator or agent can prepare the issue and create an unsent
Resend draft. Every send needs explicit human approval of the final rendered
message, sender, exact eligible audience and immediate timing. Editorial
`status: approved` alone does not authorize a broadcast.

## Installed operator setup

Run from `/Users/rgrp/src/life-itself/wayintoai` on the existing operator machine.
The private profile is `~/.config/crm/newsletter-profiles/way-into-ai.json`.
It uses the existing production audience and sender
`Way Into AI <wayintoai@lifeitself.org>`. Credentials, audience details,
authorization records and the issue ledger stay outside Git. The profile's
authorization reference records the scope; it is not final send approval.

These profiles trust processes running as the same OS user. Another operator
using this machine can follow this workflow after authorization. Do not copy
credentials or start an independent ledger on another machine; arrange CRM
operator access and shared recovery state first.

## Prepare and review

For the late week-40 issue, the stable issue key is `weekly-2026-w40`:

```sh
newsletter_cli=/Users/rgrp/src/life-itself/crm/services/mailer/scripts/newsletter.mjs
node "$newsletter_cli" prepare --newsletter way-into-ai \
  --markdown weekly/2026-w40.md --issue-key weekly-2026-w40 \
  --subject 'Opus 5.5: top-tier AI for 40% less' \
  --canonical-url https://wayintoai.com/weekly/2026-w40
node "$newsletter_cli" draft --newsletter way-into-ai --issue-key weekly-2026-w40
```

For another issue, take the subject from its frontmatter and derive the path,
canonical URL and stable issue key from its filename. Verify `status: approved`,
that `publish: false` has been removed, and that the canonical URL is live
(push first) before preparing. Keep the same key through revisions and recovery. For an
existing issue, inspect `status` before restarting; a sent or uncertain send
must not be treated as a new draft.

Review the returned private `preview.html`, neighboring `email.txt` and
`review.json`. Check links and the public issue page, sender, subject, exact
eligible addresses, exclusions and `scheduledAt: null`. A local preview does
not prove inbox rendering. Do not put audience-bearing output in Git or shared
logs.

## Approval, send and recovery

After the human explicitly approves that bundle, follow the receipt creation
snippet in the CRM guide. Record the actual approver and approval timestamp;
copy binding fields exactly from the current private review. Then:

```sh
node "$newsletter_cli" approve --newsletter way-into-ai \
  --issue-key weekly-2026-w40 --approver 'Actual human name' \
  --approval-ref /absolute/private/path/to/approval.json
node "$newsletter_cli" send --newsletter way-into-ai --issue-key weekly-2026-w40
node "$newsletter_cli" status --newsletter way-into-ai --issue-key weekly-2026-w40
```

Any content, audience, mapping or timing change requires fresh review and
approval. On timeout or unknown outcome, use `status` for the same issue and
retain the ledger. Never create a new key or repeat a provider send to recover.
Provider acceptance and broadcast `sent` are distinct from recipient delivery.

After confirmed sending, set the weekly issue's `status: sent` and actual
`sent: YYYY-MM-DD`; retain its original week/date identity for a late issue.
Mark every canonical source in `items` and `try` with `newsletter_sent` and
`newsletter_url`. Record the result in Beads. Follow active Git authorization
for committing and publishing these updates.

## Current automation limits

Way Into AI issues render through the CRM's Way Into AI email template; its
look and rules are in [newsletter-email-design.md](newsletter-email-design.md).
Other publications retain their existing template. The CRM currently omits the frontmatter preheader. It also binds approval to
the entire original source file, including frontmatter. Keep that file unchanged
from preparation through sending; update sent metadata afterward. Follow-up
`wayintoai-94n.6` tracks preheader support and the editorial hash contract.

The routine can automate preparation, unsent drafting, checks, receipt recording
after real approval, sending and bookkeeping. Human approval of the exact
message and current audience remains the send gate.
