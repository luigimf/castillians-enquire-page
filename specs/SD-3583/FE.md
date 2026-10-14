# SD-3583 — Capacity Types list in Sanity (FE)

- The dropdown options are `capacityTypes`, in array order, then the fixed Custom option, labelled `customLabel` (falls back to "Custom").
- If the list is empty or the document is absent, render the hard-coded default list.
- Custom is always last and can't be removed. Picking it reveals the core skills field (SD-3488).
- Option names wrap in the menu; no truncation.

Prototype: the `capacityTypes` (comma-separated) and `customLabel` tweaks stand in for Sanity. The default list in the prototype is placeholder content.

---
Jira: SD-3583 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
