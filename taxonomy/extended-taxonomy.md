# Extended taxonomy

**Version:** `ext-tax-v0.1-2026-08-27`  
**Status:** draft — Nickerson subjective validation pending expert review  
**Inputs pinned:** Bašić v4 ten categories (`cat-profiles-v0.1-2026-08-27`); obligation dimensions (`dimension-definitions.md`); matrix consensus (`main-matrix-reconciled.csv`)

---

## Purpose

Bašić & Giaretta provide a **technical vulnerability taxonomy** (CWE-shaped, jurisdiction-agnostic). Indian DPDP and ABDM impose **obligation-level observables** that CWE categories do not express. The extended taxonomy adds obligation dimensions and records, via the cross-mapping matrix, which category assessments make each criterion visible on an RCM.

This is Deliverable 2: not a replacement for Bašić rows, but an **orthogonal dimension set** plus documented cross-product outcomes.

---

## Dimension A — Bašić vulnerability category (fixed input)

| ID | Name | Source |
|---|---|---|
| CAT-01 | Injection | Bašić v4 §4.1 / Table 3 |
| CAT-02 | Memory Management | §4.2 |
| CAT-03 | File Management | §4.3 |
| CAT-04 | Deserialization | §4.4 |
| CAT-05 | Sensitive Data Exposure | §4.5 |
| CAT-06 | Authentication and Authorization | §4.6 |
| CAT-07 | Cryptography | §4.7 |
| CAT-08 | Resource Management | §4.8 |
| CAT-09 | Coding Standards | §4.9 |
| CAT-10 | Error Handling | §4.10 |

**Study basis:** 21 studies consolidated in v4 (not “~20”).

---

## Dimension B — Obligation-level regulatory dimension (project extension)

| Dimension | Definition | Example register rows |
|---|---|---|
| `consent_architecture` | Consent request, record, scope, presentation | A-006-01, R-003-01 |
| `purpose_binding` | Processing tied to specified purpose | A-006-01, R-003-02 |
| `withdrawal_propagation` | Comparable-ease withdrawal; processing/access stops | A-006-04, A-006-06, R-003-03 |
| `breach_notification` | Paths to intimate Board and principals | A-008-06, R-007-01, R-007-02 |
| `retention_erasure` | Erasure on withdrawal / purpose-end | A-008-07 |
| `data_localization` | Cross-border transfer restrictions | A-016-01 |
| `access_logging_demonstrability` | Access logs, monitoring, audit trail | **R-006-02, HDMP-27-05a** |
| `abha_identity` | Health ID linkage / non-exclusion | HDMP-15-04, HDMP-16-04 |
| `consent_manager_mediation` | HIE-CM / Consent Manager flows | *(no MVP row yet)* |
| `fhir_conformance` | NRCeS ABDM FHIR profile conformance | NRCES-FHIR-01 |

Full one-line intents: [`dimension-definitions.md`](dimension-definitions.md).

---

## Cross-product (matrix) — summary of consensus visibility

For each **CAT × obligation** cell, the matrix records whether the RCM for that category guarantees the criterion (`fully_covered`), partially overlaps (`partially_covered`), or guarantees nothing (`not_visible`).

**Structural findings from reconciled matrix:**

1. **`access_logging_demonstrability` has no Bašić home** — 20/20 cells `not_visible` (Gap 1).  
2. **Consent/notice/breach/erasure/localization/FHIR columns** — uniformly `not_visible` except noted partials.  
3. **Holistic security safeguard (A-008-05)** — 10/10 `partially_covered` (slice only).  
4. **Crypto minimum safeguard (R-006-01)** — CAT-07 `fully_covered`; CAT-05 partial.

Detail: [`../mapping/not-visible-cells.md`](../mapping/not-visible-cells.md).

---

## Nickerson ending conditions

Objective/subjective checklist: [`nickerson-ending-conditions.md`](nickerson-ending-conditions.md).  
**Not yet expert-validated** on subjective criteria.

---

## Amendment rule

New obligation dimensions or Bašić row changes require: decision-log entry, register version bump, matrix re-code plan, taxonomy version bump.
