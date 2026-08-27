# Main matrix — dual coding (post-freeze)

**Rule:** `cell-coding-rule` v0.3-frozen  
**Register:** `register-v0.3-mvp-2026-08-27`  
**Profiles:** `cat-profiles-v0.1-2026-08-27`  
**Date:** 2026-08-27  
**Order:** column-wise (all CATs per obligation)  
**Excluded column:** HDMP-16-04 (org policy / underspecified; not in Gap-1 matrix)  
**Cells:** 10 × 17 = **170**  
**Pilot handling A:** 12 pilot cells flagged `pilot_exclude=1` in [`main-matrix-dual.csv`](main-matrix-dual.csv); **excluded from reported kappa**

**Coders:**  
- `coder_a` — research assistant (this session), under frozen rule  
- `coder_b` — independent pass under frozen rule (separate agent; same pinned artifacts)

**Labels:** `F` = fully_covered · `Pp` = partially_covered + partial_positive · `N` = not_visible  
(No `partial_by_default` or `criterion_underspecified` on this pass.)

**Machine table:** [`main-matrix-dual.csv`](main-matrix-dual.csv)  
**Kappa summary:** [`main-matrix-kappa.json`](main-matrix-kappa.json)  
**Protocol:** [`main-matrix-protocol.md`](main-matrix-protocol.md)

---

## Reliability (non-pilot cells only)

| Statistic | Value |
|---|---|
| *n* (kappa) | 158 |
| Pilot excluded | 12 |
| Observed agreement *p_o* | 0.9937 |
| Unweighted Cohen’s κ | **0.949** |
| Linearly weighted Cohen’s κ (primary) | **0.949** |
| Non-pilot disagreements | **1** (CAT-06 × A-006-04) |

High κ is driven in part by mass agreement on `not_visible` (see ToV: agreement ≠ correctness).

---

## Compact dual view

Default cell = **N/N** (coder_a / coder_b). Only non-default and disagreement cells listed below. Full grid in CSV.

### Non-default cells

| Cell | coder_a | coder_b | Pilot exclude? | Agree? |
|---|---|---|---|---|
| CAT-05 × A-006-01 | Pp | N | yes | no |
| CAT-06 × A-006-04 | Pp | N | **no** | **no** ← only κ disagreement |
| CAT-06 × A-006-06 | Pp | N | yes | no |
| CAT-01…10 × A-008-05 | Pp | Pp | no | yes |
| CAT-05 × R-006-01 | Pp | N | yes | no |
| CAT-07 × R-006-01 | F | Pp | yes | no |

All other cells: **N/N**.

### Logging / audit columns (Gap 1)

| Obligation | All 10 CATs (a/b) |
|---|---|
| R-006-02 | N/N |
| HDMP-27-05a | N/N |

Including CAT-10: CWE-117 does not entail access-log / audit-trail *existence*.

### Notice, breach, erasure, localization, Health ID, FHIR

All CAT × {R-003-01, R-003-02, R-003-03, A-008-06, R-007-01, R-007-02, A-008-07, A-016-01, HDMP-15-04, NRCES-FHIR-01}: **N/N**.

---

## Counts (full 170; descriptive)

| Verdict | coder_a | coder_b |
|---|---|---|
| fully_covered | 1 | 0 |
| partially_covered | 14 | 11 |
| not_visible | 155 | 159 |

---

## Reconciliation status

**Not reconciled yet.** Both originals retained. Non-pilot disagreement and pilot disagreements logged in [`../logs/disagreement-record.md`](../logs/disagreement-record.md).  
Working Gap-1 narrative continues to rest on the **agreed** N/N logging columns, which are not in dispute.
