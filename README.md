# Indian Cyber Regulation Register

Every cybersecurity and data-protection instrument binding Indian regulated entities, with
its reference number, issue date, status and the dates it sets.

**23 instruments** across the RBI, SEBI, IRDAI, IFSCA, CERT-In and MeitY.
Oldest verification in the current set: **2026-08-18**.

## Files

| File | What it is |
|------|------------|
| `india-cyber-regulations.json` | The register. One object per instrument, deadlines nested. |
| `india-cyber-regulations.csv` | The same rows, flattened. Deadlines as `kind:date:label`, semicolon-separated. |
| `schema.json` | JSON Schema for a record. Validate against this rather than guessing at the shape. |

Also served directly, with permissive CORS, if you would rather fetch than clone:

    https://www.bitscore.in/register/india-cyber-regulations.json
    https://www.bitscore.in/register/india-cyber-regulations.csv

## How it is maintained

Every entry is read from the issuing regulator's own notification, not from secondary
reporting. If an instrument cannot be confirmed on a government source, it does not go in.

The `verifiedOn` field on each record is the date somebody last opened that source and
re-read the reference, the date and the link. It is **not** the date this file was
regenerated, which is a much easier thing to claim and worth nothing.

## Things this register gets right that most summaries do not

- **The RBI's 2026 framework is seven Directions, not one.** Each entity class got its own
  instrument on 31 July 2026. Regional Rural Banks and Local Area Banks have none in the
  family at all.
- **The DPDP Rules are dated 13 November 2025, not the 14th.** The same PDF carries both;
  the 14th is the e-gazette upload stamp. The eighteen-month clock to 13 May 2027 runs from
  the 13th, so "notified 14 November" and "13 May 2027" cannot both be right.
- **CERT-In's Directions took effect on 27 June 2022, not 28 April 2022.** They say they
  "become effective after 60 days from the date on which it is issued".
- **The CSCRF deadline of 31 August 2025 never applied to MIIs, KRAs or QRTAs.** Both
  extensions carved those three out.
- **IRDAI's 2026 compliance date precedes its issue date.** The circular of 6 April 2026
  requires compliance "from the current financial year", which opened on 1 April.

## Licence

The data is published under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Use it, and credit **BitScore Cybertech LLP — bitscore.in**.

The underlying instruments are Government of India works and are nobody's to license. What
is licensed here is the compilation, the structured metadata and the verification dates.

## This repository is generated

The source of truth is `lib/regulations.ts` in the bitscore.in site repository, and this
mirror is overwritten on each publish. **Pull requests against these files will be lost.**
If something here is wrong — and if it is, that matters — open an issue instead, or write to
nimitt@bitscore.ai.in.

Full register with notes: https://www.bitscore.in/resources/india-cyber-regulation-register
