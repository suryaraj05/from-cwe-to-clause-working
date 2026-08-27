# Validation report (partial)

**Version:** `validation-v0.1-2026-08-27`  
**Status:** **incomplete** — matrix track only; Delphi and case study not executed  
**Full plan:** [`validation-plan.md`](validation-plan.md)

---

## 1. Matrix inter-rater reliability

**Design:** Two independent coders under frozen rule v0.3; 170 cells; 12 pilot cells excluded from κ (handling A).

| Metric | Result |
|---|---|
| Linearly weighted Cohen’s κ | **0.949** |
| Unweighted κ | 0.949 |
| *n* (non-pilot) | 158 |
| Pre-reconciliation disagreements (non-pilot) | 1 |
| Cells reconciled | 5 |

**Caveat:** Coder B was an independent agent pass, not a named human team member. Mass agreement on `not_visible` inflates κ. See threats to validity.

**Artifacts:** `mapping/main-matrix-kappa.json`, `mapping/main-matrix-reconciled.csv`, `mapping/reconciliation-record.md`

---

## 2. Structural findings (consensus matrix)

| Finding | Evidence |
|---|---|
| Logging Gap 1 | 20/20 cells `not_visible` for R-006-02 and HDMP-27-05a |
| Sparse visibility overall | 156/170 `not_visible` (91.8%) |
| Sole `fully_covered` | CAT-07 × R-006-01 (crypto → encryption safeguard) |
| Uniform partial column | A-008-05: 10/10 `partially_covered` |

Detail: `paper/05-results.md`, `paper/findings-logging-gap1.md`

---

## 3. WASA transparency finding

No public official WASA specification located — reported separately from matrix.  
`paper/findings-wasa-transparency.md`

---

## 4. Coverage ratio (MVP)

18 register rows; partial DPDP/ABDM instrument coverage by design.  
`validation/coverage-ratio.md`

---

## 5. Nickerson taxonomy check

Objective conditions largely met with documented partials; subjective conditions **pending Delphi**.  
`taxonomy/nickerson-ending-conditions.md`

---

## 6. Not yet evaluated

| Component | Status |
|---|---|
| Human second coder (matrix) | Not done |
| Register row dual coding | Not done |
| Rubric application on case evidence | Not done |
| Expert Delphi (2 rounds) | Protocol only |
| Mentor sign-off on reconciliation | Not done |

---

## 7. Conclusion (interim)

The **cross-mapping instrument behaves as designed** under the frozen rule: it surfaces systematic non-visibility of Indian health-data logging duties in Bašić’s taxonomy (Gap 1). Reliability statistics are **exploratory** until human coders complete the validation track. The rubric and case-study/Delphi protocols are ready for team execution.

**When team returns:** items 6 above → update this report to v1.0.
