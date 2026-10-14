# Request a Capacity Quote — handoff bundle

Jira epic **SD-3487**, release "Request a Capacity Quote Page". Stories: SD-3488 (the page), SD-3489 (menubar CTA), SD-3490 (the emails), SD-3491 (Sanity entry), SD-3583 (capacity types in Sanity).

```
page/index.html                     the page, self-contained — open it in a browser
emails/15-quote-request.html              internal notification
emails/15-quote-request-custom.html       internal notification, Custom picked
emails/15-quote-request-user.html         receipt to the prospect
emails/15-quote-request-user-custom.html  receipt, Custom picked
emails/assets/castillians-logo.png  the email header logo
specs/<key>/FE.md, BE.md            one folder per story
```

## page/index.html

A **reference implementation**, not production code. It is one self-contained file with the design system inlined, so it opens offline and shows every state: both steps, per-step validation, the country picker, the Capacity Types multi-select, the per-type capacity cards, the Custom core skills field, the bench-type picker and the thank-you.

Build the real page at **`/enquire`** per SD-3488. Four things are **reused from the existing platform, not rebuilt** — the bundle only stands in for them:

| In the bundle | In production |
|---|---|
| Its own 12-country list and flag SVGs | The platform's existing country list and flag assets |
| A short demo skill list | The platform's skill library |
| A placeholder capacity type list | The Sanity list (SD-3583) |
| The two bench types, hard-coded | The platform's bench types |
| Terms / Privacy as plain text | The **existing modals** from `castillians.com/manager-sign-up` |

_Outdated on 14 Oct. Previously: "Title, heading, description and the bottom image come from Sanity (SD-3491). Everything else on the page is code."_

Title, heading, description and the bottom image come from **Sanity** (SD-3491), as do the capacity type options and the Custom label (SD-3583). Everything else on the page is code.

## emails/

Send-ready HTML — 600px table, Arial, inline styles, `mso` line-height rules, tested against Outlook, Apple Mail and Gmail.

**Before sending:** the header logo's `src` is `https://app.castillians.com/assets/castillians-logo.png`. Host `emails/assets/castillians-logo.png` at that URL, or swap the `src` for your ESP's asset URL — a relative path cannot resolve in a sent email.

**Recipients** (SD-3490):

- _Outdated on 14 Oct. Previously: "Internal → humancapital@, brand@, co'toole@, francesca.vella@castillians.com, all on the To line. Reply-To is the prospect's work email."_
- Internal → `brand@castillians.com` only. Reply-To is the prospect's work email.
- Receipt → the prospect. Reply-To must reach a human; the email invites a reply.

**These two emails are the only record an enquiry ever existed** — no queue, no database row, no Zoho lead. So a submission that fails to send must **fail visibly with the form intact**, and send failures must be logged and alerted on. A thank-you shown for an enquiry nobody will see is the failure this bundle most needs to avoid.

Values are placeholders; both emails render the same payload from the form. Use the `-custom` templates when the payload includes the Custom capacity type. Capacity renders as one "Capacity — <type>" row per type.
