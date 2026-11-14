# Case Study Evidence Index (Phase 2)

**Target System:** Bahmni India Distro — ABDM Health Information Provider (HIP) Integration  
**Primary Repository:** `https://github.com/BahmniIndiaDistro/openmrs-module-hip` (Java / OpenMRS OMOD; MIT License)  
**Companion Gateway Repo:** `https://github.com/BahmniIndiaDistro/hip-service` (C# / .NET Core, forked from `ProjectEKA/hip-service`; MIT License)  
**Domain:** Healthcare / Electronic Medical Records (EMR) & ABDM Health Information Exchange  
**Date Indexed:** 2026-11-14  
**Status:** Evidence pack ready — rubric scoring next  

---

## System Overview & Selection Rationale

`BahmniIndiaDistro/openmrs-module-hip` exposes OpenMRS clinical encounters, diagnostic reports, prescriptions, and patient demographics as ABDM-compliant Health Information Provider (HIP) endpoints, working alongside `hip-service` for consent-artefact verification, ECDH payload encryption, and gateway callbacks. It directly exercises both **DPDP Act/Rules** obligations (purpose-limited consent, revocation propagation, encryption/masking, access logging) and **ABDM / NRCeS FHIR IG v6.5.0** criteria (Health ID linking, StructureDefinition profile conformance, audit trails).

---

## Indexed Evidence Files (10 Files)

| # | Repository | File Path | Architectural Role | Primary Obligations Exercised |
|---|---|---|---|---|
| 1 | `openmrs-module-hip` | `api/src/main/java/org/bahmni/module/hip/Config.java` | Environment & runtime configuration for location, phone attributes, and ABDM/HIP identifiers | `OB-DPDP-A-008-05`, `OB-ABDM-HDMP-15-04` |
| 2 | `openmrs-module-hip` | `omod/src/main/java/org/bahmni/module/hip/web/controller/HipControllerAdvice.java` | Global Spring REST exception handler (`@ControllerAdvice`) mapping errors to HTTP responses | `OB-DPDP-R-006-02` (Gap 1 test), `OB-DPDP-A-008-05` |
| 3 | `openmrs-module-hip` | `api/src/main/java/org/bahmni/module/hip/model/HiTypeDocumentKind.java` | Enum defining supported ABDM Health Information types (Immunization, DiagnosticReport, Prescription, Wellness, etc.) | `OB-ABDM-NRCES-FHIR-01`, `OB-DPDP-A-006-01` |
| 4 | `openmrs-module-hip` | `api/src/main/java/org/bahmni/module/hip/service/PatientService.java` | Patient demographic lookup and ABHA Number / Health ID identifier linking in OpenMRS | `OB-ABDM-HDMP-15-04`, `OB-ABDM-HDMP-16-04` |
| 5 | `openmrs-module-hip` | `api/src/main/java/org/bahmni/module/hip/builder/FhirBundleBuilder.java` | Constructs NRCeS ABDM FHIR R4 Bundles (`Patient`, `Encounter`, `Composition`, `Organization`) from clinical data | `OB-ABDM-NRCES-FHIR-01`, `OB-DPDP-R-003-01` |
| 6 | `openmrs-module-hip` | `omod/src/main/java/org/bahmni/module/hip/web/controller/CareContextController.java` | REST endpoints for care-context discovery and HIP-initiated linking against patient ABHA IDs | `OB-ABDM-HDMP-15-04`, `OB-DPDP-A-006-01` |
| 7 | `openmrs-module-hip` | `omod/src/main/java/org/bahmni/module/hip/web/controller/HealthInformationController.java` | Extracts and returns clinical bundles scoped to requested HI-types and date ranges | `OB-DPDP-A-006-01`, `OB-DPDP-R-006-02` |
| 8 | `hip-service` | `src/In.ProjectEKA.HipService/Consent/ConsentController.cs` | Receives ABDM Consent Manager notifications (`GRANTED`, `REVOKED`, `EXPIRED`) and updates consent state | `OB-DPDP-A-006-04`, `OB-DPDP-A-006-06` |
| 9 | `hip-service` | `src/In.ProjectEKA.HipService/DataFlow/DataFlowController.cs` | Validates active consent artefacts before fetching health records and pushing encrypted bundles to HIU | `OB-DPDP-A-006-06`, `OB-ABDM-HDMP-27-05a` |
| 10 | `hip-service` | `src/In.ProjectEKA.HipService/EncryptionBit/EncryptionService.cs` | Implements ECDH key exchange and AES-GCM encryption for health information payloads in transit | `OB-DPDP-R-006-01`, `OB-DPDP-A-008-05` |

---

## Expected Gap 1 & Coverage Hypotheses for Phase 2 Rubric Scoring

1. **Logging & Audit Trail (`OB-DPDP-R-006-02`, `OB-ABDM-HDMP-27-05a`):** Static CWE scanners (CAT-01..CAT-10) will evaluate exception handlers/controllers for CWE-117 / CWE-209, yet cannot verify whether structured, immutable access audit logs exist across health-information and data-flow paths — validating the `20/20 N` Gap 1 finding on real healthcare code.
2. **FHIR Conformance (`OB-ABDM-NRCES-FHIR-01`):** FHIR bundle builders and HI-type enums govern ABDM StructureDefinition profiles (`ndhm.in#6.5.0`), which are invisible to CWE-based vulnerability categories.
3. **Consent Revocation Propagation (`OB-DPDP-A-006-04`, `OB-DPDP-A-006-06`):** Consent and data-flow controllers enforce consent state transitions (`REVOKED` blocking data flow), illustrating why AuthZ CWEs (CAT-06) only partially overlap without capturing consent-specific lifecycle semantics.
4. **Encryption Safeguards (`OB-DPDP-R-006-01`):** Encryption service implements payload encryption in transit (CAT-07 `Pp`), while persistence layers demonstrate why sound crypto routines alone do not guarantee encryption/masking of all stored personal data.

---

## Scoring worksheets

- Lead: [`case-study-scorer-A.md`](case-study-scorer-A.md)  
- Second rater: [`case-study-scorer-B.md`](case-study-scorer-B.md)  
- HOWTO: [`HOWTO-case-study-scoring.md`](HOWTO-case-study-scoring.md)
