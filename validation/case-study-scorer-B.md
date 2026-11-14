# Case study scorer B — Bahmni HIP

**Scorer:** Rahul  
**Date:** 2026-11-14  
**System:** Bahmni India Distro HIP (`openmrs-module-hip` + `hip-service`)  
**Rule/rubric:** `assessment-rubric.md` v0.1 · register `register-v0.3-mvp`  
**Scores:** `P` Pass · `Pt` Partial · `F` Fail · `NA` not assessable via CWE (still cite evidence)

**Do not look at scorer A until both finish.**

**Minimum required if short on time:** Gap 1 (2) + R-006-01 + A-008-05 + A-006-06 + A-006-04 + HDMP-15-04 + NRCES-FHIR-01  
**Ideal:** all rows below.

Evidence index: [`case-study-evidence-index.md`](case-study-evidence-index.md)

---

## Gap 1 (mandatory)

### R-006-02 — Access logs / monitoring present?

| Field | Your answer |
|---|---|
| Score (P/Pt/F/NA) | F |
| Evidence cited (file + what you saw) | `HealthInformationController.java` and `HipControllerAdvice.java` — only exception/error logging (`@ExceptionHandler`) is implemented; there is no dedicated access-log writer or unauthorized-access monitoring mechanism when clinical records are queried. |
| Notes | Clear confirmation of Gap 1: static CWE scanners see zero violations here yet the system lacks access-monitoring logs. |

### HDMP-27-05a — Audit trail of personal-data access/processing?

| Field | Your answer |
|---|---|
| Score | Pt |
| Evidence cited | `DataFlowController.cs` and `ConsentController.cs` record consent/data-flow request states in the gateway database, providing partial transaction traceability, but lack a comprehensive audit trail of all internal personal-data read/processing events in `openmrs-module-hip`. |
| Notes | Gateway tracks request lifecycle states, not full HDMP cl.27.5(a) processing audit trails. |

---

## Security

### A-008-05 — Reasonable security safeguards?

| Score | Evidence | Notes |
|---|---|---|
| Pt | `EncryptionService.cs` (ECDH/AES-GCM encryption), `DataFlowController.cs` (consent verification), and `HipControllerAdvice.java` (sanitized error responses). | Covers exchange security well, but lacks full-stack safeguards (DB encryption, IAM, network controls) within these repos. |

### R-006-01 — Encryption / masking / tokens?

| Score | Evidence | Notes |
|---|---|---|
| Pt | `EncryptionService.cs` encrypts FHIR bundles in transit using Curve25519 + AES-GCM, while `PatientService.java` and `FhirBundleBuilder.java` process unmasked patient demographics in memory/DB. | In-transit encryption passes; at-rest encryption/masking/tokenization is not evidenced. |

---

## Consent / withdrawal

### A-006-01 — Purpose-specific consent?

| Score | Evidence | Notes |
|---|---|---|
| P | `HealthInformationController.java` & `DataFlowController.cs` enforce consent artefact `hiTypes` (`HiTypeDocumentKind.java`), care-context IDs, and date-range limits before returning data. | Scopes data extraction strictly to consented clinical categories and timeframes. |

### A-006-04 — Comparable-ease withdrawal?

| Score | Evidence | Notes |
|---|---|---|
| NA | `ConsentController.cs` processes incoming `REVOKED` / `EXPIRED` webhook events from ABDM Consent Manager. | Backend API only; user interface effort for granting vs. withdrawing consent is outside this codebase. |

### A-006-06 — Cease processing on withdrawal?

| Score | Evidence | Notes |
|---|---|---|
| P | `ConsentController.cs` persists `REVOKED` state and `DataFlowController.cs` rejects data-flow requests if consent is not `GRANTED` or has expired. | Immediately stops data sharing upon revocation notification. |

---

## Notice / breach / retention / localization

### R-003-01 / R-003-02 / R-003-03 (notice)

| ID | Score | Evidence | Notes |
|---|---|---|---|
| R-003-01 | NA | `FhirBundleBuilder.java` builds FHIR bundles; no user-facing data collection notice UI in HIP module. | Handled externally by ABDM PHR app / Consent Manager. |
| R-003-02 | NA | `ConsentController.cs` receives purpose codes from Consent Manager; no notice text rendered here. | Outside HIP backend scope. |
| R-003-03 | NA | `ConsentController.cs` handles gateway callbacks only; no user notice/withdrawal UI. | Outside HIP backend scope. |

### A-008-06 / R-007-01 / R-007-02 (breach)

| ID | Score | Evidence | Notes |
|---|---|---|---|
| A-008-06 | F | `HipControllerAdvice.java` only returns HTTP error payloads; no breach intimation workflow to Board/principals. | Missing in indexed codebase. |
| R-007-01 | F | `HipControllerAdvice.java` & `Config.java` contain no principal breach-notification content/templates. | Missing in indexed codebase. |
| R-007-02 | F | `HipControllerAdvice.java` & `DataFlowController.cs` contain no 72-hour Board reporting logic. | Missing in indexed codebase. |

### A-008-07 (erasure) / A-016-01 (localization)

| ID | Score | Evidence | Notes |
|---|---|---|---|
| A-008-07 | F | `ConsentController.cs` marks consent `REVOKED` without triggering deletion/erasure of OpenMRS patient records. | No erasure path implemented. |
| A-016-01 | NA | `Config.java` configures ABDM gateway endpoints, but contains no explicit cross-border transfer restriction logic. | Infrastructure/deployment policy rather than code-level geo-restriction. |

---

## ABDM

### HDMP-15-04 — Health ID linkage?

| Score | Evidence | Notes |
|---|---|---|
| P | `PatientService.java` & `CareContextController.java` map OpenMRS patient records and care contexts to ABHA Health IDs. | Directly implements Health ID linkage. |

### NRCES-FHIR-01 — FHIR profile conformance?

| Score | Evidence | Notes |
|---|---|---|
| Pt | `FhirBundleBuilder.java` & `HiTypeDocumentKind.java` generate ABDM-aligned FHIR R4 Bundles/Compositions, but lack explicit runtime `StructureDefinition` profile validation (`ndhm.in#6.5.0`). | Structural mapping is present, without automated IG profile validation checks. |

### HDMP-16-04 — org policy

| Score | Evidence | Notes |
|---|---|---|
| NA | `PatientService.java` & `CareContextController.java` operate only on ABDM linking calls; clinical care workflows are decoupled. | **org_policy / underspecified** — non-exclusion of patients without Health ID is a facility policy. |

---

## Scorer B summary

Gap 1: `F` (R-006-02) / `Pt` (HDMP-27-05a) — error logging and gateway transaction state exist, but access-monitoring logs are absent and audit trails are incomplete.  
Crypto: `Pt` (R-006-01) / `Pt` (A-008-05) — ECDH + AES-GCM secures bundles in transit, but at-rest encryption/masking and holistic safeguards are outside HIP code.  
Consent stop-on-revoke: `P` (A-006-06) — `ConsentController.cs` (`REVOKED`) + `DataFlowController.cs` validation cleanly block subsequent data sharing.  
FHIR / Health ID: `P` (HDMP-15-04) / `Pt` (NRCES-FHIR-01) — ABHA linking is complete; FHIR R4 bundles are built without explicit runtime `ndhm.in#6.5.0` profile validation.  

**Status:** [x] Finished alone — ready to compare