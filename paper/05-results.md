# 05 Results

**Status:** draft from reconciled matrix (2026-08-27). Team rewrites in mentor voice; do not invent citations.

**Pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`  
**Artifacts:** [`mapping/main-matrix-reconciled.csv`](../mapping/main-matrix-reconciled.csv), [`mapping/main-matrix-summary.json`](../mapping/main-matrix-summary.json)

---

## Cross-mapping coverage (10 Bašić categories × 17 MVP obligations = 170 cells)

| Consensus verdict | *n* | % of 170 |
|---|---|---|
| `not_visible` | 156 | 91.8% |
| `partially_covered` | 13 | 7.6% |
| `fully_covered` | 1 | 0.6% |

All thirteen `partially_covered` cells carry sub-flag **`partial_positive`** (none `partial_by_default`).

### Interpretation

Most Indian regulatory observables in the MVP register are **not expressible** as guarantees of a remediated-under-category module (RCM) under Bašić’s ten CWE-shaped categories. That is the expected shape for Gap 1: security-assessment vocabulary ≠ statutory compliance vocabulary.

The sole `fully_covered` cell is **CAT-07 (Cryptography) × R-006-01** (DPDP Rules r.6(1)(a) encryption path): a crypto-clean RCM necessarily applies sound encryption.

The uniform **`partially_covered`** column **A-008-05** (Act s.8(5) reasonable safeguards) shows every category contributes *some* security-safeguard evidence without guaranteeing the holistic statutory bar.

---

## Gap 1 — access logging (primary worked example)

| Column | Reconciled pattern |
|---|---|
| R-006-02 (r.6(1)(c) — visibility via logs/monitoring) | 10/10 `not_visible` |
| HDMP-27-05a (cl.27.5(a) — audit trail) | 10/10 `not_visible` |

No disagreement after dual coding or reconciliation. Detail: [`findings-logging-gap1.md`](findings-logging-gap1.md).

CAT-10 (Error Handling) does **not** rescue logging: CWE-117 presupposes logs exist and concerns output neutralization, not access-log existence.

---

## Inter-rater reliability (agent pass)

| Metric | Value |
|---|---|
| Linearly weighted Cohen’s κ (non-pilot, *n* = 158) | 0.949 |
| Non-pilot disagreements before reconciliation | 1 (CAT-06 × A-006-04) |
| Cells reconciled after dual coding | 5 |

κ measures **agreement**, not correctness ([`06-threats-to-validity.md`](06-threats-to-validity.md)). Mass agreement on `not_visible` inflates κ. **Human second coder and mentor reconciliation review still required** ([`../validation/human-next-steps.md`](../validation/human-next-steps.md)).

---

## Other findings (unchanged)

- **WASA transparency:** no public official WASA specification located — reported as object-of-study finding ([`findings-wasa-transparency.md`](findings-wasa-transparency.md)).
- **HDMP cl.16.4:** excluded from Gap-1 matrix; pilot flagged `criterion_underspecified` for code-pattern mapping.

---

## Columns with any non-`not_visible` cell

| Obligation | Non-N cells |
|---|---|
| A-006-01 | CAT-05 → P |
| A-006-06 | CAT-06 → P |
| A-008-05 | CAT-01…10 → P (all) |
| R-006-01 | CAT-05 → P; CAT-07 → F |

All other MVP columns: uniformly `not_visible` across ten categories.
