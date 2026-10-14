# SD-3490 — Email notifications (BE)

- Both emails send in one run from the same payload (see `SD-3488/BE.md`).
- Pick the template by whether `capacity` contains `type: "custom"`.
- Internal **To**: `brand@castillians.com` only. **Reply-To**: the prospect's work email.
- Receipt **To**: the prospect. **Reply-To** must reach a human.
- A submission is complete only when both are accepted by the mail provider. Log and alert on failures.
- Hours render as "<n> hours a month". `unsure` renders as "Will decide later". `1000+` renders as "1,000+ hours a month".
- Test once with Custom and once without.

_Outdated on 14 Oct. Previously: "Internal To: four recipients."_

---
Jira: SD-3490 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
