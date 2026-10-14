# SD-3488 — The /enquire page (BE)

## Submission payload

```json
{
  "fullName": "", "position": "", "company": "", "workEmail": "",
  "phone": { "country": "MT", "number": "" },
  "engineersBased": "Global | Data Regulated",
  "capacity": [
    { "type": "Platform Engineering", "hoursPerMonth": "160" },
    { "type": "custom", "label": "Custom", "hoursPerMonth": "80", "coreSkills": ["Java"] }
  ],
  "message": "", "consent": true
}
```

_Outdated on 14 Oct. Previously: "hoursPerMonth (single value), coreSkills[], additionalSkills[] at the top level."_

- `capacity` holds one entry per type picked, in Sanity order, with Custom last.
- `hoursPerMonth` is one of `40 | 80 | 160 | 500 | 1000+ | unsure`.
- Custom uses the fixed key `type: "custom"`. `label` is the Sanity label at submit time.
- `coreSkills` is present (non-empty) only on the Custom entry.

## Server validation

- All step 1 fields are required. Work email must be valid; phone must be valid for the selected country.
- At least one `capacity` entry, each with `hoursPerMonth`. `coreSkills` must be non-empty when `custom` is present.
- `type` must be a current Sanity option or `custom`.
- `engineersBased` must be one of the two bench types.
- Consent is required. Double-submit is guarded.

## Persistence

None. No user, account, subscription, bench or lead row. The emails (SD-3490) are the only record. If either send fails, return an error so the form stays intact.

---
Jira: SD-3488 · Epic: SD-3487 · Release: Request a Capacity Quote Page
Prototype: `Request a Capacity Quote Page.dc.html` · Bundle: `page/index.html`
