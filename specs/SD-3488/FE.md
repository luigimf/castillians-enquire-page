# SD-3488 — The /enquire page (FE)

Public, unauthenticated, two-step form at `/enquire`. V2 Castillians design system. The prototype is authoritative for layout and copy.

## Steps

| Step | Fields |
|---|---|
| 1 · Your details | Full Name · Position · Company · Work Email · Contact Number |
| 2 · Your engineering needs | Capacity Types · Engineers Based · Capacity per Month (one per type) · Custom core skills (if Custom) · Message (optional) · consent |

_Outdated on 14 Oct. Previously: "Step 2: Hours per Month · Engineers Based · Core Skills · Additional Skills · Message (optional) · consent."_

- Continue validates the step in view only. Back never validates or clears.
- Every pending field marks red at once, plus one summary line.

## Step 2 fields

**Capacity Types** — multi-select dropdown.
- Options are the Sanity list (SD-3583), in Sanity order, then a fixed **Custom** option, last and set apart by a rule. Custom's label comes from Sanity and defaults to "Custom".
- Picked options render as removable chips in the trigger. The menu stays open while picking; it closes on the trigger or on a click outside it.
- At least one is required.

**Engineers Based** — platform bench-type picker (icon tile + description), one answer per request.

| Label | Value sent | Description |
|---|---|---|
| Globally | Global | To access a global pool of vetted engineers for flexible, cost-effective projects. |
| In data regulated countries | Data Regulated | For GDPR-compliant and data-sensitive projects requiring vetted engineers from secure, Data Regulated countries. |

_Outdated on 14 Oct. Previously: "Anywhere / EU & Data Safe Countries."_

**Capacity per Month** — one card per capacity type picked.
- Heading "Capacity per Month", with the helper "Set the monthly engineering hours for each capacity type."
- Each card shows the type name and a select (placeholder "Select capacity amount"). Cards follow Sanity order; Custom is always last.
- Options (code, not CMS): 40 hours · 80 hours · 160 hours · 500 hours · 1,000+ hours · Will decide later.
- Required for every type picked.

_Outdated on 14 Oct. Previously: "Hours per Month — one select for the whole request; last option Not sure yet."_

**Custom core skills** — inside the Custom card only.
- Label: "The skills critical to delivering your custom capacity".
- Picks from the platform skill library, accepts free text, no cap, chips.
- Required while Custom is picked; discarded if Custom is unpicked.

_Outdated on 14 Oct. Previously: "Core Skills (required) and Additional Skills (optional), always shown."_ Additional Skills is removed.

## Unchanged

Contact Number (platform country list + flags, default Malta, digits only), Work Email validation, the Terms/Privacy modals from `manager-sign-up`, mandatory consent, the thank-you card, and "Send another request".

---
Jira: SD-3488 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
