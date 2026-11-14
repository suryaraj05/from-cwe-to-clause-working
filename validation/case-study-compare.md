# Case study compare — Bahmni HIP

**Date:** 2026-11-14  
**Scorers:** A: Surya  B: Rahul  

Fill **after** both finish.

---

## Score comparison (matrix obligations)

| Obligation | A | B | Agree? | Temporary consensus | Key evidence |
|---|---|---|---|---|---|
| R-006-02 | Pt | F | No | **F** | `HealthInformationController.java` & `HipControllerAdvice.java`: only HTTP/error logging exists; no dedicated access-monitoring logs for unauthorized reads. |
| HDMP-27-05a | Pt | Pt | Yes | **Pt** | `DataFlowController.cs` & `ConsentController.cs`: gateway transaction/consent state is persisted, but a full processing audit trail is absent. |
| A-008-05 | Pt | Pt | Yes | **Pt** | `EncryptionService.cs`, `DataFlowController.cs`, `HipControllerAdvice.java`: strong transport security, but holistic/DB safeguards sit outside repo. |
| R-006-01 | Pt | Pt | Yes | **Pt** | `EncryptionService.cs`: Curve25519 ECDH + AES-GCM encrypts bundles in transit, while `PatientService.java` / DB lack guaranteed at-rest masking/encryption. |
| A-006-01 | P | P | Yes | **P** | `HealthInformationController.java` & `DataFlowController.cs`: enforces consented `hiTypes` (`HiTypeDocumentKind.java`), care contexts, and date ranges. |
| A-006-04 | NA | NA | Yes | **NA** | `ConsentController.cs`: backend webhook handles `REVOKED`/`EXPIRED`, while UI withdrawal-ease parity lives in Consent Manager / PHR app. |
| A-006-06 | P | P | Yes | **P** | `ConsentController.cs` (`REVOKED` state update) + `DataFlowController.cs` (blocks data fetch/push unless consent is `GRANTED` and unexpired). |
| R-003-01 | NA | NA | Yes | **NA** | `FhirBundleBuilder.java`: builds FHIR bundles; user-facing itemised data notice is external to HIP backend. |
| R-003-02 | NA | NA | Yes | **NA** | `ConsentController.cs`: consumes purpose codes from artefacts; pre-consent purpose notice is external. |
| R-003-03 | NA | NA | Yes | **NA** | `ConsentController.cs`: exposes gateway callback webhook only; patient notice path is external. |
| A-008-06 | F | F | Yes | **F** | `HipControllerAdvice.java`: runtime errors map to HTTP responses; no breach-intimation workflow to Board or principals. |
| R-007-01 | F | F | Yes | **F** | `HipControllerAdvice.java` & `Config.java`: no principal breach-notification content templates present. |
| R-007-02 | F | F | Yes | **F** | `HipControllerAdvice.java` & `DataFlowController.cs`: no 72-hour Board breach-reporting timer or integration. |
| A-008-07 | F | F | Yes | **F** | `ConsentController.cs` & `PatientService.java`: `REVOKED` stops sharing but triggers no record erasure in OpenMRS. |
| A-016-01 | Pt | NA | No | **NA** | `Config.java`: configures ABDM India gateway endpoints, but cross-border transfer restriction is an infra/policy control, not a code check. |
| HDMP-15-04 | P | P | Yes | **P** | `PatientService.java` & `CareContextController.java`: explicitly links OpenMRS patient records and care contexts to ABHA Health IDs. |
| NRCES-FHIR-01 | Pt | Pt | Yes | **Pt** | `FhirBundleBuilder.java` & `HiTypeDocumentKind.java`: emits ABDM FHIR R4 bundles, without runtime `ndhm.in#6.5.0` StructureDefinition validation. |
| HDMP-16-04 | NA | NA | Yes | **NA (org-policy)** | `PatientService.java`: ABDM linking is decoupled from core OpenMRS care delivery; non-exclusion is an organizational policy. |

**Agreement Summary:** **16 / 18 obligations agreed (88.9% raw agreement)**; 2 minor boundary disagreements (`R-006-02` `Pt` vs `F`; `A-016-01` `Pt` vs `NA`) reconciled cleanly to `F` and `NA`.

---

## Gap 1 narrative (3–5 sentences)

Yes — inspecting real Bahmni HIP code directly confirms our Phase 1 matrix finding (`20/20 N` for logging/audit trail). A CWE-based static scanner reviewing `HipControllerAdvice.java` and `HealthInformationController.java` only checks whether log outputs are neutralized against injection (CWE-117) or avoid leaking stack traces (CWE-209), reporting zero logging defects even though dedicated access-monitoring logs (`R-006-02`, Consensus: **F**) do not exist in the module. Similarly, while `DataFlowController.cs` persists gateway transaction states (`HDMP-27-05a`, Consensus: **Pt**), static vulnerability categories cannot distinguish basic operational state rows from a strict, immutable audit trail of personal-data access. Consequently, CWE-only remediation passes a clinical data-exchange module while leaving statutory access-logging and auditability gaps undetected.

---

## Ready for agent final report?

- [x] Compare complete  
- [x] Consensus scores filled  
- [x] Message: “case study scored — write report”