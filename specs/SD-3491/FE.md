# SD-3491 — Sanity entry (FE)

The page reads **title, heading, description, image** from the `/enquire` singleton, each with a hard-coded fallback. The image is lazy-loaded, with explicit dimensions.

The same singleton now also carries the capacity type list and Custom label (SD-3583).

_Outdated on 14 Oct. Previously: "Four fields, and nothing else; no option lists."_

Still not CMS-controlled: field labels, validation copy, capacity-per-month options, bench types, countries, skills, consent/legal copy, emails, the menubar CTA.

---
Jira: SD-3491 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
