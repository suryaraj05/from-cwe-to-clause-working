# Artifact description

**Status:** draft — pointers to repository deliverables.

The designed artefact is a **documentary compliance assessment framework** comprising five components. No executable software is included.

---

## 1. Obligation register (Deliverable 1)

**Location:** `register/obligation-register.md` (MVP version `register-v0.3-mvp-2026-08-27`)

GuideMe-adapted rows: verbatim quotes, atomic `derived_criterion`, assessment question, evidence required, separate Act/Rules commencement columns, taxonomy dimension tags.

**MVP scope:** 18 rows spanning consent/notice, security, logging, breach, retention, localization, ABDM Health ID, audit trail, FHIR conformance, plus HDMP cl.16.4 (org-policy / underspecified for code).

**Schema:** `register/SCHEMA.md` · **Protocol:** `register/coding-protocol.md`

---

## 2. Extended taxonomy (Deliverable 2)

**Location:** `taxonomy/extended-taxonomy.md`

**Dimension A:** Bašić ten categories with CWE inventories (`category-profiles.md`).  
**Dimension B:** Obligation-level dimensions (e.g. `access_logging_demonstrability`) in `dimension-definitions.md`.

Nickerson checklist: `nickerson-ending-conditions.md`.

---

## 3. Cross-mapping matrix (Deliverable 3)

**Location:** `mapping/main-matrix-reconciled.csv` (consensus); dual originals in `main-matrix-dual.csv`

**Rule:** counterfactual visibility on the **remediated-under-category module (RCM)** — frozen `cell-coding-rule.md` v0.3.

**Size:** 10 × 17 = 170 cells (HDMP-16-04 excluded).

**Reliability:** κ = 0.949 (158 non-pilot cells); reconciliation record for five disputed cells.

---

## 4. Assessment rubric (Deliverable 4)

**Location:** `rubric/assessment-rubric.md`, `rubric/scoring-protocol.md`

Criterion-level scores: Pass / Partial / Fail / Not assessable via CWE taxonomy. Matrix informs hints; raters must still judge obligation evidence directly. Gap 1 rows require explicit logging review.

---

## 5. Validation package (Deliverable 5)

**Location:** `validation/`

| Component | File | Status |
|---|---|---|
| Plan | `validation-plan.md` | Draft |
| Partial report | `validation-report.md` | Matrix track done |
| Coverage | `coverage-ratio.md` | MVP documentary |
| Delphi | `delphi/protocol.md` | Design only |
| Case study | `case-study.md` | Protocol only |

---

## Worked findings (embedded in artefact)

- **Gap 1 logging:** `paper/findings-logging-gap1.md`  
- **WASA transparency:** `paper/findings-wasa-transparency.md`

---

## Traceability

Source manifest: `sources.md`. Decisions: `logs/decision-log.md`. Disagreements: `logs/disagreement-record.md`.

Public deposit: GitHub artifact repo without third-party PDFs; provenance via manifest.
