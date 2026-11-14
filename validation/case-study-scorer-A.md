# Case study scorer A — Bahmni HIP

**Scorer:** Surya  
**Date:** 2026-11-14  
**System:** Bahmni India Distro HIP (`openmrs-module-hip` + `hip-service`)  
**Rule/rubric:** `assessment-rubric.md` v0.1 · register `register-v0.3-mvp`  
**Scores:** `P` Pass · `Pt` Partial · `F` Fail · `NA` not assessable via CWE (still cite evidence)

**Do not look at scorer B until both finish.**

Evidence index: [`case-study-evidence-index.md`](case-study-evidence-index.md)

---

## Gap 1 (mandatory)

### R-006-02 — Access logs / monitoring present?

| Field | Your answer |
|---|---|
| Score (P/Pt/F/NA) | Pt |
| Evidence cited (file + what you saw) | `HealthInformationController.java` (handles `/health-information/fetch` requests) and `HipControllerAdvice.java` (logs exceptions via SLF4J `log.error` on failure). Operational error logging exists, but dedicated user-access monitoring/review logs for detecting unauthorized personal-data reads are not evidenced in the HIP module code. |
| Matrix hint | All CATs `not_visible` |
| Notes | CWE scanning (even CAT-10 CWE-117) only inspects log string sanitization, completely missing the absence of structured access-monitoring logs. |

### HDMP-27-05a — Audit trail of personal-data access/processing?

| Field | Your answer |
|---|---|
| Score | Pt |
| Evidence cited | `DataFlowController.cs` & `ConsentController.cs` (persist consent-artefact status and transaction state transitions in DB), alongside `HipControllerAdvice.java` (error-only logging). State records exist for ABDM gateway transactions, but a strict, immutable audit trail of all personal-data processing/access activities is absent from the indexed HIP layer. |
| Matrix hint | All CATs `not_visible` |
| Notes | Confirms Gap 1: transaction state tracking ≠ strict audit trail, and CWE categories cannot detect this gap. |

---

## Security

### A-008-05 — Reasonable security safeguards?

| Field | Your answer |
|---|---|
| Score | Pt |
| Evidence cited | `EncryptionService.cs` (ECDH + AES-GCM payload encryption), `HipControllerAdvice.java` (controlled exception responses avoiding raw stack leaks), and `DataFlowController.cs` (consent-artefact verification before data transfer). Technical safeguards exist for gateway exchange, while deployment/network/at-rest controls sit outside this repository slice. |
| Matrix hint | Mixed Pp/Pd/N by category |
| Notes | Illustrates why technical CWEs give `Pp`/`Pd` coverage (in-transit crypto, error handling) without guaranteeing holistic organizational safeguards. |

### R-006-01 — Encryption / masking / tokens for personal data?

| Field | Your answer |
|---|---|
| Score | Pt |
| Evidence cited | `EncryptionService.cs` (`Encrypt` / `GenerateKeyPair` using Curve25519 ECDH + AES-GCM for health data bundles in transit) vs. `PatientService.java` and `FhirBundleBuilder.java` (construct plain FHIR R4 JSON payloads prior to gateway encryption; OpenMRS DB persistence relies on underlying DB config). |
| Matrix hint | CAT-07 Pp; CAT-05 Pp; others N |
| Notes | Directly mirrors our Phase 1 `CAT-07: F → Pp` correction: strong in-transit crypto exists, but at-rest encryption/masking across all personal data is not guaranteed by the HIP module alone. |

---

## Consent / withdrawal

### A-006-01 — Purpose-specific consent; only necessary data?

| Field | Your answer |
|---|---|
| Score | P |
| Evidence cited | `HealthInformationController.java` and `DataFlowController.cs` (filter clinical extraction strictly by consent artefact's granted `hiTypes` from `HiTypeDocumentKind.java`, `careContexts`, and `dateRange` window). |
| Notes | Strong technical enforcement of purpose/data-minimization bounds per consent artefact. |

### A-006-04 — Withdrawal as easy as grant?

| Field | Your answer |
|---|---|
| Score | NA |
| Evidence cited | `ConsentController.cs` (backend webhook endpoint receiving `GRANTED`, `REVOKED`, `EXPIRED` status notifications from the ABDM Consent Manager). |
| Notes | Backend HIP receives revocation callbacks, but user-facing grant vs. withdrawal effort parity resides in the PHR/Consent Manager UI and cannot be assessed from HIP server code. |

### A-006-06 — On withdrawal, cease processing (incl. processors)?

| Field | Your answer |
|---|---|
| Score | P |
| Evidence cited | `ConsentController.cs` (updates local consent artefact status to `REVOKED`/`EXPIRED` upon CM notification) + `DataFlowController.cs` (checks active `GRANTED` status and expiry before fetching or pushing health records to HIU). |
| Notes | Revoked/expired consent immediately halts subsequent HIP data-flow processing; downstream processor erasure/cease outside HIP depends on HIU. |

---

## Notice (Rules r.3)

### R-003-01 — Itemised personal data in notice?

| Score | Evidence | Notes |
|---|---|---|
| NA | `FhirBundleBuilder.java` & `HiTypeDocumentKind.java` (define clinical resource types exported, not user-facing privacy notices). | Privacy notice UI/text is outside HIP backend scope (handled by Consent Manager / front-end). |

### R-003-02 — Purposes / uses in notice?

| Score | Evidence | Notes |
|---|---|---|
| NA | `ConsentController.cs` (consumes purpose codes inside signed consent artefacts rather than rendering pre-consent notices). | Not evidenced in HIP backend repository. |

### R-003-03 — Notice path for comparable-ease withdrawal?

| Score | Evidence | Notes |
|---|---|---|
| NA | `ConsentController.cs` (exposes gateway notification webhook only, no patient-facing notice path). | Front-end / Consent Manager responsibility; not assessable in HIP code. |

---

## Breach

### A-008-06 — Intimate Board + affected principals on breach?

| Score | Evidence | Notes |
|---|---|---|
| F | `HipControllerAdvice.java` (handles runtime exceptions via HTTP status/logging; no breach-notification workflow to DPDP Board or Data Principals exists across indexed files). | Absent from HIP codebase. |

### R-007-01 — Principal breach notice content?

| Score | Evidence | Notes |
|---|---|---|
| F | `HipControllerAdvice.java` & `Config.java` (no notification templates or principal breach-intimation payloads present). | Absent from HIP codebase. |

### R-007-02 — Board intimation timelines?

| Score | Evidence | Notes |
|---|---|---|
| F | `HipControllerAdvice.java` & `DataFlowController.cs` (no 72-hour breach reporting timer or Board API integration). | Absent from HIP codebase. |

---

## Retention / localization

### A-008-07 — Erasure on withdrawal / purpose-end?

| Score | Evidence | Notes |
|---|---|---|
| F | `ConsentController.cs` & `PatientService.java` (`REVOKED` updates consent status and blocks future sharing, but triggers no erasure/purging of underlying OpenMRS clinical records or cached artefacts). | Clinical retention rules override automatic deletion in EMRs, and no erasure workflow is implemented here. |

### A-016-01 — Cross-border transfer restriction mechanism?

| Score | Evidence | Notes |
|---|---|---|
| Pt | `Config.java` & `DataFlowController.cs` (routes exchanges exclusively through configured ABDM India Gateway URLs; however, no explicit geofencing/country-restriction check exists in code). | Architectural binding to ABDM gateway provides implicit domestic routing, without explicit code-level transfer restrictions. |

---

## ABDM

### HDMP-15-04 — Personal data linked to Health ID?

| Score | Evidence | Notes |
|---|---|---|
| P | `PatientService.java` (queries/links patient records via ABHA Number / Health ID attributes) & `CareContextController.java` (links OpenMRS care contexts to patient ABHA IDs). | Core architectural feature of `openmrs-module-hip`. |

### NRCES-FHIR-01 — NRCeS ABDM FHIR profile conformance?

| Score | Evidence | Notes |
|---|---|---|
| Pt | `FhirBundleBuilder.java` & `HiTypeDocumentKind.java` (builds HAPI FHIR R4 `Bundle`, `Composition`, `Patient`, `Encounter`, and `Organization` resources structured for ABDM HI-types, though runtime `StructureDefinition` profile validation against `ndhm.in#6.5.0` is not enforced in code). | Emits ABDM-structured FHIR bundles, but relies on external/build-time profile validation rather than programmatic IG v6.5.0 schema checks. |

### HDMP-16-04 — Care without requiring Health ID (org policy)

| Score | Evidence | Notes |
|---|---|---|
| NA | `PatientService.java` & `CareContextController.java` (only invoked when ABDM linking/discovery is triggered; standard OpenMRS clinical care operates without ABHA). | **org_policy / underspecified** — non-denial of care is an operational hospital policy, not a code-level gate in the HIP connector. |

---

## Scorer A summary

| Family | Quick read (1 line) |
|---|---|
| Gap 1 logging | `Pt` / `Pt` — error & transaction state logs exist (`HipControllerAdvice`, `DataFlowController`), but dedicated access-monitoring and strict audit trails are missing (and invisible to CWE). |
| Crypto / safeguards | `Pt` / `Pt` — strong ECDH/AES-GCM in-transit encryption (`EncryptionService.cs`), but at-rest PD encryption/masking and holistic safeguards depend on external OpenMRS DB/ops config. |
| Consent | `P` / `NA` / `P` — strong backend enforcement of HI-type/date-range scoping and immediate cessation on `REVOKED` status, while UI withdrawal parity is outside HIP scope. |
| FHIR / Health ID | `P` / `Pt` / `NA` — explicit ABHA Health ID linking and FHIR R4 bundle construction present, though automated `ndhm.in#6.5.0` StructureDefinition validation is not enforced in code. |
| Notice / breach / erasure | `NA` / `F` / `F` — privacy notices reside in the Consent Manager UI (`NA`), while automated breach intimation and post-revocation erasure are absent (`F`). |

**Status:** [x] Finished alone — ready to compare