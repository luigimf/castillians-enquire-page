# SD-3490 — Email notifications (FE)

| Email | To | Standard | Custom picked |
|---|---|---|---|
| New capacity quote request | brand@castillians.com | `emails/15-quote-request.html` | `emails/15-quote-request-custom.html` |
| Quote request received | The prospect | `emails/15-quote-request-user.html` | `emails/15-quote-request-user-custom.html` |

_Outdated on 14 Oct. Previously: "Internal to humancapital@, brand@, co'toole@, francesca.vella@castillians.com; two templates only."_

## Capacity rows

- One row per capacity type: **Capacity — <type>** → "160 hours a month" or "Will decide later".
- Rows follow Sanity order. Type text is as the prospect saw it.
- Custom variants: Custom's row comes last under its Sanity label, then **<Custom label> — core skills**.
- No Core skills or Additional skills rows otherwise.

_Outdated on 14 Oct. Previously: "One Hours per month row, plus Core skills and Additional skills rows."_

- Preheaders name the capacity types picked.
- House shell unchanged: 600px table, Arial, `mso` rules, hidden preheader, label/value rows, and no unsubscribe link.

---
Jira: SD-3490 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
