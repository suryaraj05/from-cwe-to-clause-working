# Obligation-level dimension definitions (draft)

These extend Bašić & Giaretta’s ten technical categories. Full Nickerson validation lives in `extended-taxonomy.md` later.

| Dimension | One-line intent (draft — not yet Nickerson-validated) |
|---|---|
| `consent_architecture` | How consent is requested, recorded, scoped, and presented |
| `purpose_binding` | Processing tied to specified purpose; no silent reuse |
| `withdrawal_propagation` | Withdrawal comparable in ease; processing/access stops accordingly |
| `breach_notification` | Instrumentation/paths to intimate Board and affected principals as prescribed |
| `retention_erasure` | Erasure when purpose ends / on request, subject to legal retention |
| `data_localization` | Cross-border transfer restrictions as notified under the Act |
| `access_logging_demonstrability` | Access logging, monitoring/review of access, and records that demonstrate consent or processing activity (DPDP r.6(1)(c); HDMP audit-trail / consent-record duties). **Not** log-injection sanitization (CWE-117). |
| `abha_identity` | Health ID / ABHA-related identity handling per ABDM primary sources only |
| `consent_manager_mediation` | Consent Manager / HIE-CM mediation per Act/Rules/ABDM sources |
| `fhir_conformance` | FHIR R4 structuring per NRCeS IG (not generic HL7 alone) |

## Note on Gap 1 (logging)

Bašić v4’s ten categories (21 studies, Table 3) contain **no** CWE for existence/sufficiency of audit or access logging (CWE-778/779/223/532/1295 absent; “logging” absent as a topic). The only log-adjacent CWE is **CWE-117** under CAT-10 (output neutralization *for* logs), which presupposes logs exist. Therefore `access_logging_demonstrability` is an obligation-level dimension with **no home** in the input taxonomy — the cleanest Gap 1 instance for the paper’s worked example.
