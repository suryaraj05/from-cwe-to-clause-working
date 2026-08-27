# Project status — deliverable tracker

**As of:** 2026-08-27 (agent pass; team unavailable)  
**Rule pin:** `cell-coding-rule` v0.3-frozen · register `register-v0.3-mvp-2026-08-27`

Legend: **Done** · **Draft (agent)** — usable structure, team must rewrite · **Blocked (human)** — needs team, mentor, experts, or external document

---

## Five deliverables (Hevner artifact set)

| # | Deliverable | Status | Primary files | Blocked on |
|---|---|---|---|---|
| 1 | Obligation register | **Draft (agent)** — MVP 18 rows, page-stamped | `register/obligation-register.md`, `SCHEMA.md`, `page-stamps.md` | Register row dual-coding; expand beyond MVP; FHIR `meta.profile` exact stamp |
| 2 | Extended taxonomy | **Draft (agent)** | `taxonomy/extended-taxonomy.md`, `dimension-definitions.md`, `nickerson-ending-conditions.md` | Nickerson subjective review with experts |
| 3 | Cross-mapping matrix | **Done (agent)** — dual coded + reconciled | `mapping/main-matrix-reconciled.csv`, `reconciliation-record.md` | Human second coder; mentor reconciliation sign-off |
| 4 | Assessment rubric | **Draft (agent)** | `rubric/assessment-rubric.md`, `scoring-protocol.md` | Pilot scoring on real audit excerpt |
| 5 | Validation report | **Partial (agent)** | `validation/validation-report.md`, `validation-plan.md` | Delphi, case study, human IRR |

---

## Evaluation activities (Hevner)

| Activity | Status | Artifact |
|---|---|---|
| Matrix dual coding + κ | **Done (agent)** | κ = 0.949 (*n* = 158 non-pilot); see `main-matrix-kappa.json` |
| Matrix reconciliation | **Done (agent)** | 5 cells adjudicated → `reconciliation-record.md` |
| Coverage ratio (documentary) | **Draft (agent)** | `validation/coverage-ratio.md` |
| Expert Delphi (2 rounds) | **Blocked (human)** | Protocol only: `validation/delphi/protocol.md` |
| Documentary case study | **Blocked (human)** | Protocol only: `validation/case-study.md` — needs hospital audit report |
| Human inter-rater (register + matrix) | **Blocked (human)** | `validation/human-next-steps.md` |

---

## Paper sections

| Section | Status | File |
|---|---|---|
| Abstract | **Draft (agent)** | `paper/00-abstract.md` |
| Introduction | **Draft (agent)** | `paper/01-introduction.md` |
| Background / related work | **Draft (agent)** | `paper/02-background-related-work.md` |
| Method | **Draft (agent)** — substantive | `paper/03-method.md` |
| Artifact | **Draft (agent)** | `paper/04-artifact.md` |
| Results | **Draft (agent)** — from reconciled matrix | `paper/05-results.md` |
| Threats to validity | **Draft (agent)** — partial | `paper/06-threats-to-validity.md` |
| Conclusion | **Draft (agent)** | `paper/07-conclusion.md` |
| References | **Draft (agent)** — from `sources.md` | `paper/references.md` |
| Gap 1 finding | **Done (agent)** | `paper/findings-logging-gap1.md` |
| WASA transparency | **Done (agent)** | `paper/findings-wasa-transparency.md` |

**Team rewrite:** all `paper/*.md` marked draft — mentor voice, final citation checks, no invented clauses.

---

## What AI completed in this session (incremental)

- Deliverable tracker (this file)
- Extended taxonomy + Nickerson checklist (documentary self-assessment)
- Assessment rubric + scoring protocol
- Validation plan + partial validation report
- Coverage ratio (MVP scope counts)
- Delphi protocol (design only)
- Case-study protocol (template only)
- Paper stubs → structural drafts (abstract through conclusion, artifact, references)
- Updated README status block

---

## What only the team can do next

1. **Human second coder** for matrix (and ideally register rows).  
2. **Mentor sign-off** on reconciliation (especially CAT-06 × A-006-04).  
3. **Delphi** — recruit panel, run two rounds.  
4. **Case study** — obtain permission to use hospital audit report; apply rubric.  
5. **Final paper polish** — voice, submission formatting, institutional copy verification (Hevner MISQ mirror).  
6. **Optional:** expand register beyond MVP; resolve HDMP-16-04 rewrite vs org-policy retention.

See [`human-next-steps.md`](human-next-steps.md) for checklist detail.
