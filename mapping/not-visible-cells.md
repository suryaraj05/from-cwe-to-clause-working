# “Not visible” cell catalogue

Populated from **reconciled** main matrix (2026-08-27).  
Rule: `cell-coding-rule` v0.3-frozen · [`main-matrix-reconciled.csv`](main-matrix-reconciled.csv)

**156 / 170** cells are `not_visible`. Emptiness is an **outcome**, not a target.

---

## Column-uniform `not_visible` (10/10 CATs)

These obligation columns yield no Bašić-category visibility for any row:

| Obligation | Family (short) |
|---|---|
| R-003-01, R-003-02, R-003-03 | DPDP notice content |
| A-006-04 | Comparable-ease withdrawal |
| A-008-06 | Breach intimation |
| R-007-01, R-007-02 | Breach notice to principal / Board |
| A-008-07 | Erasure on withdrawal / purpose-end |
| A-016-01 | Cross-border transfer restriction |
| HDMP-15-04 | Health ID linkage |
| **R-006-02** | **Access logging (DPDP r.6(1)(c)) — Gap 1** |
| **HDMP-27-05a** | **Audit trail (HDMP cl.27.5(a)) — Gap 1** |
| NRCES-FHIR-01 | NRCeS FHIR profile conformance |

**Gap 1:** 20 cells (two columns × ten categories), all reconciled `not_visible`, including CAT-10 / CWE-117 trap.

---

## Column with exceptions

| Obligation | Pattern |
|---|---|
| A-006-01 | 9× `not_visible`; **CAT-05** = `partially_covered` (exposure limits ≠ purpose-bound consent) |
| A-006-06 | 9× `not_visible`; **CAT-06** = `partially_covered` (authz cessation ≠ full withdrawal propagation) |
| R-006-01 | 8× `not_visible`; **CAT-05** = `partially_covered`; **CAT-07** = `fully_covered` (crypto → encryption path) |
| A-008-05 | **0× `not_visible`** — all ten CATs = `partially_covered` (security-safeguard slice only) |

---

## Per-cell justifications

Full one-line justifications: `main-matrix-reconciled.csv` column `consensus_just`.  
Disagreement adjudication: [`reconciliation-record.md`](reconciliation-record.md).
