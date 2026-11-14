# Case study scorer A — Bahmni HIP

**Scorer:** _________________  
**Date:** _________________  
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
| Score (P/Pt/F/NA) |  |
| Evidence cited (file + what you saw) |  |
| Matrix hint | All CATs `not_visible` |
| Notes | Look at HealthInformationController / HipControllerAdvice — is there *access* audit logging, or only error handling? |

### HDMP-27-05a — Audit trail of personal-data access/processing?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Matrix hint | All CATs `not_visible` |
| Notes | DataFlowController may move data under consent — does it *record* an audit trail? |

---

## Security

### A-008-05 — Reasonable security safeguards?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Matrix hint | Mixed Pp/Pd/N by category |
| Notes | EncryptionService, auth on controllers, exception handling — slice vs holistic |

### R-006-01 — Encryption / masking / tokens for personal data?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Matrix hint | CAT-07 Pp; CAT-05 Pp; others N |
| Notes | In-transit ECDH/AES vs at-rest masking of all PD fields |

---

## Consent / withdrawal

### A-006-01 — Purpose-specific consent; only necessary data?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Notes | HI-types / care context / consent artefact scoping |

### A-006-04 — Withdrawal as easy as grant?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Notes | ConsentController REVOKED/EXPIRED — is UX/comparable ease visible in these files? |

### A-006-06 — On withdrawal, cease processing (incl. processors)?

| Field | Your answer |
|---|---|
| Score |  |
| Evidence cited |  |
| Notes | DataFlowController validating active consent before fetch/push |

---

## Notice (Rules r.3)

### R-003-01 — Itemised personal data in notice?

| Score | Evidence | Notes |
|---|---|---|
|  |  | Likely weak/absent in HIP code alone |

### R-003-02 — Purposes / uses in notice?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

### R-003-03 — Notice path for comparable-ease withdrawal?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

---

## Breach

### A-008-06 — Intimate Board + affected principals on breach?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

### R-007-01 — Principal breach notice content?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

### R-007-02 — Board intimation timelines?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

---

## Retention / localization

### A-008-07 — Erasure on withdrawal / purpose-end?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

### A-016-01 — Cross-border transfer restriction mechanism?

| Score | Evidence | Notes |
|---|---|---|
|  |  |  |

---

## ABDM

### HDMP-15-04 — Personal data linked to Health ID?

| Score | Evidence | Notes |
|---|---|---|
|  |  | PatientService / CareContextController ABHA linking |

### NRCES-FHIR-01 — NRCeS ABDM FHIR profile conformance?

| Score | Evidence | Notes |
|---|---|---|
|  |  | FhirBundleBuilder / HiTypeDocumentKind — meta.profile / StructureDefinition? |

### HDMP-16-04 — Care without requiring Health ID (org policy)

| Score | Evidence | Notes |
|---|---|---|
|  |  | Mark **org_policy / underspecified** if not code-visible |

---

## Scorer A summary

| Family | Quick read (1 line) |
|---|---|
| Gap 1 logging |  |
| Crypto / safeguards |  |
| Consent |  |
| FHIR / Health ID |  |
| Notice / breach / erasure |  |

**Status:** [ ] Finished alone — ready to compare
