# SD-3491 — Sanity entry (BE)

Singleton document `enquirePage`:

| Field | Type | Notes |
|---|---|---|
| title | string | Required, with length guidance |
| heading | string | Required, with length guidance |
| description | text | Plain text |
| image | image | Alt text is mandatory |
| capacityTypes | array<string> | SD-3583 |
| customLabel | string | SD-3583 |

Drafts don't affect the live page. Publishing needs no deploy.

---
Jira: SD-3491 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
