# Way Into AI email styling

Approved direction: adapt the website blue-pencil identity to email. Paper
#fbfbf9, ink #1b1b1d, accent #2140c4, serif prose and monospace structure.
Use a fluid single-column presentation table capped at 640px, inline styles,
Georgia and Courier fallbacks, hairline section rules and a text masthead.
Keep editorial content unchanged and preserve canonical/unsubscribe links.
Apply in the shared CRM renderer only for publicationKey way-into-ai.

Implementation: add a rendering regression test, observe its failure, implement
publication-scoped styling, run package and full script tests, regenerate the
existing week-40 package and update its existing unsent provider draft. Keep
human send approval separate. Browser preview verification remains pending
because the browser tool rejects local-file URLs.

## Separate-thread handoff

Resume bead `wayintoai-7a3` in the Way Into AI repository. Implementation lives
in the sibling CRM repository at
`services/mailer/scripts/lib/newsletter-package.mjs`; its regression is in
`services/mailer/test-node/newsletter-package.test.mjs`.

Visual authority: `docs/brand.md` for the brand and voice, `DESIGN.md` for the
website design system. This document records the email adaptation. Maintain
one reusable renderer implementation; do not paste HTML into each issue.
A future sending skill should reference these sources and
`docs/newsletter-sending.md`, rather than copy brand rules into a new authority.

Current state: existing week-40 Resend broadcast was updated in place and remains
unsent. Private preview and exact audience review are under
`~/.local/share/crm/newsletters/packages/way-into-ai/weekly-2026-w40/`.
The stable issue key is `weekly-2026-w40`; the publication profile is
`way-into-ai`. Latest review contains 30 eligible recipients. No final send
approval receipt exists. Keep recipients and provider identifiers private.

Remaining acceptance: inspect desktop and narrow/mobile rendering through an
allowed preview surface, compare against website identity, and check real inbox
rendering if a separately approved test is arranged. Current local-file browser
attempt was blocked; do not bypass that tool policy. Rendering uses fallback
fonts without loading external font assets; Newsreader/Plex are not guaranteed
in recipient clients. Preheader and editorial hash improvements are tracked in
`wayintoai-94n.6`. Refresh the same unsent draft after any further template edit,
then obtain approval for the new exact message/audience before sending.

Verification so far: focused package tests 8 passing; full CRM script suite
136 passing; mechanical design detector returned no findings; diff whitespace
checks passed. No website deployment, newsletter send or Git push occurred.
