# SD-3583 — Capacity Types list in Sanity (BE)

Fields on the SD-3491 singleton:

| Field | Type | Validation |
|---|---|---|
| capacityTypes | array<string> | At least one entry; trimmed; unique, ignoring case |
| customLabel | string | Optional; empty falls back to "Custom" |

- Submissions store Custom as `type: "custom"` plus `label`. Renaming never breaks a submission.
- Server-side, accept only `type` values in the live list, or `custom`.
- Not related to the platform's two bench types (Engineers Based).

---
Jira: SD-3583 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
