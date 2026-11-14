# Case study report — Bahmni India Distro HIP

**Version:** `case-study-v1.0-2026-11-14`  
**System under assessment:** Bahmni India Distro ABDM Health Information Provider (HIP) stack  
**Repositories (public, MIT):**  
- https://github.com/BahmniIndiaDistro/openmrs-module-hip  
- https://github.com/BahmniIndiaDistro/hip-service  

**Register pin:** `register-v0.3-mvp-2026-08-27`  
**Rubric:** `assessment-rubric.md` v0.1  
**Matrix pin:** `main-matrix-reconciled.csv` (post human sample 2026-11-14)  
**Scorers:** Surya (A), Rahul (B)  
**Evidence pack:** 10 indexed source files — [`case-study-evidence-index.md`](case-study-evidence-index.md)

---

## 1. Scope disclaimer (mandatory)

This case study assesses whether the indexed HIP evidence exhibits **compliant patterns** relative to MVP DPDP/ABDM criteria.  
Pattern presence is **necessary but not sufficient** for legal compliance. Organisational process, deployment configuration, Consent Manager / PHR UI, and OpenMRS core behaviour outside the indexed files are out of scope unless cited.

We did **not** run static analysis tools as a deliverable; we used documentary/code-reading evidence against the rubric.

---

## 2. Case metadata

| Field | Value |
|---|---|
| Module | ABDM HIP connector for Bahmni/OpenMRS + gateway `hip-service` |
| Why selected | Public healthcare EMR integration exercising consent, encryption, Health ID, FHIR, and data flow |
| Evidence files | 10 (Java + C#) — see index |
| Dual scoring | Yes — independent then reconciled |
| Raw score agreement | **16/18 (88.9%)** before adjudication |

---

## 3. Consensus scoring table

| Obligation | Consensus | Evidence (short) | Matrix hint (visibility) |
|---|---|---|---|
| **R-006-02** access logs | **F** | Error/HTTP logging only (`HipControllerAdvice`, controllers); no dedicated access-monitoring logs | All CATs N |
| **HDMP-27-05a** audit trail | **Pt** | Consent/data-flow state persisted; not a full immutable access/processing audit trail | All CATs N |
| **A-008-05** reasonable safeguards | **Pt** | In-transit crypto, consent checks, sanitized errors; holistic/DB/ops safeguards outside slice | Mixed Pp/Pd/N |
| **R-006-01** encryption/masking/tokens | **Pt** | ECDH + AES-GCM for bundles in transit; at-rest masking/encryption of all PD not evidenced | CAT-07/05 Pp |
| **A-006-01** purpose-specific consent | **P** | Extraction scoped by `hiTypes`, care contexts, date range | Mostly N |
| **A-006-04** comparable-ease withdrawal | **NA** | Backend receives REVOKED/EXPIRED; UX parity not in HIP code | Mostly N |
| **A-006-06** cease on withdrawal | **P** | REVOKED/EXPIRED blocks subsequent data flow | CAT-06 Pp possible |
| **R-003-01** itemised notice | **NA** | No patient-facing notice in HIP backend | All N |
| **R-003-02** purpose notice | **NA** | Purposes consumed from artefacts; notice UI external | All N |
| **R-003-03** notice withdrawal path | **NA** | Webhook only; notice path external | All N |
| **A-008-06** breach intimation | **F** | No Board/principal breach workflow | All N |
| **R-007-01** principal breach content | **F** | No templates/payloads | All N |
| **R-007-02** Board timelines | **F** | No 72-hour Board reporting logic | All N |
| **A-008-07** erasure on withdrawal | **F** | REVOKED stops sharing; no OpenMRS record erasure | All N |
| **A-016-01** transfer restriction | **NA** | ABDM gateway routing; no explicit code-level geo check | All N |
| **HDMP-15-04** Health ID link | **P** | ABHA / Health ID linking in PatientService & CareContextController | All N |
| **NRCES-FHIR-01** FHIR profiles | **Pt** | ABDM-oriented FHIR R4 bundles; no runtime `ndhm.in#6.5.0` StructureDefinition validation | All N |
| **HDMP-16-04** non-exclusion | **NA (org-policy)** | HIP linking decoupled from core care; policy not code gate | Underspecified |

### Score counts (consensus)

| Score | *n* | Obligations |
|---|---|---|
| **P** Pass | 3 | A-006-01, A-006-06, HDMP-15-04 |
| **Pt** Partial | 4 | HDMP-27-05a, A-008-05, R-006-01, NRCES-FHIR-01 |
| **F** Fail | 5 | R-006-02, A-008-06, R-007-01, R-007-02, A-008-07 |
| **NA** | 6 | A-006-04, R-003-01/02/03, A-016-01, HDMP-16-04 |

---

## 4. Disagreements adjudicated

| Obligation | A | B | Consensus | Rationale |
|---|---|---|---|---|
| R-006-02 | Pt | F | **F** | Error logging ≠ access-monitoring logs required by r.6(1)(c); absence is clear in indexed HIP layer |
| A-016-01 | Pt | NA | **NA** | Domestic ABDM gateway binding is architectural/infra, not an explicit transfer-restriction mechanism in code |

Raw agreement before adjudication: **16/18 (88.9%)**.

---

## 5. Gap 1 — logging (primary evaluation claim)

**Matrix prediction:** R-006-02 and HDMP-27-05a are `not_visible` under all ten Bašić categories (human-confirmed 20/20 N).

**Case-study result:**
- **R-006-02 → F:** dedicated access logs/monitoring for unauthorised personal-data access are not evidenced; only exception/operational logging appears.
- **HDMP-27-05a → Pt:** gateway consent/transaction state provides partial traceability, not a strict audit trail of all personal-data access/processing.

**Implication:** A CWE-shaped review of the same files could focus on log *injection* (CWE-117) or error leakage and still miss the statutory **existence/sufficiency** of access logging and audit trails. This is empirical support for Gap 1 on real ABDM-adjacent healthcare code.

---

## 6. What CWE-only review would catch vs miss (narrative)

| Likely visible to CWE-oriented review | Likely missed without obligation checklist |
|---|---|
| Crypto strength of in-transit encryption (CAT-07 slice) | Access-monitoring log *existence* (R-006-02) |
| AuthN/AuthZ on controllers; consent gate as access control | Consent UX comparable-ease (A-006-04); notice content (r.3) |
| Some error-handling hygiene | Breach intimation to Board/principals (s.8(6), r.7) |
| | Erasure on withdrawal (s.8(7)) |
| | Runtime NRCeS StructureDefinition validation |
| | Holistic “reasonable safeguards” beyond the repo slice |

Conversely, the HIP stack **does** show strong patterns for purpose-scoped data release (A-006-01), cease-on-revoke (A-006-06), and Health ID linkage (HDMP-15-04) — duties that are mostly matrix-`not_visible` under CWE categories, so they require the **register/rubric** path, not category remediation alone.

---

## 7. Link back to Phase 1 human matrix correction

Phase 1 moved **CAT-07 × R-006-01** from `fully_covered` to **`partially_covered`**.  
This case study matches that judgement: `EncryptionService` provides strong **in-transit** encryption, but does **not** guarantee encryption/masking/tokenization of all personal data at rest → rubric **Pt**.

---

## 8. Limitations

- Indexed **10 files** only — not the entire Bahmni/OpenMRS platform.  
- Notice/withdrawal UX and some ABDM flows live in Consent Manager / PHR apps not scored here → many **NA**.  
- No dynamic runtime or production log inspection.  
- Pattern scores ≠ DPDP/ABDM legal certification.

---

## 9. Conclusion

Applying the framework to Bahmni’s ABDM HIP integration shows:

1. **Gap 1 holds on real code** — access-monitoring logs fail; audit trail only partial; invisible to CWE-only lenses.  
2. **Register + rubric surface duties** (consent scoping, revoke-stop, Health ID, FHIR structure) that matrix categories cannot guarantee.  
3. **Encryption is partial** in the sense of our corrected matrix cell — transit crypto ≠ full r.6(1)(a) coverage.  
4. Dual human scoring was feasible (**88.9%** pre-adjudication agreement) on a documentary evidence pack.

**Next (optional):** mentor review of this report; Delphi only if required; manuscript Results section cite this case study.

---

## Appendix — artefact pointers

| Artefact | Path |
|---|---|
| Evidence index | `validation/case-study-evidence-index.md` |
| Scorer A / B | `validation/case-study-scorer-A.md`, `case-study-scorer-B.md` |
| Compare | `validation/case-study-compare.md` |
| Rubric | `rubric/assessment-rubric.md` |
| Matrix | `mapping/main-matrix-reconciled.csv` |
| Gap 1 finding | `paper/findings-logging-gap1.md` |
