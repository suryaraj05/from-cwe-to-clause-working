# Obligation register — minimum viable set (pilot corpus)

**Register version:** `register-v0.3-mvp-2026-08-27`  
**Purpose:** Pilot corpus spanning DPDP families **and** ABDM technical criteria.  
**Quote confidence:** extracted from local PDFs / verified extracts; set `clause_id_verified` after human page-stamp.  
**Commencement:** `commencement-lookup.md` (843(E) + Rules r.1).

| obligation_id | family | instrument | clause_id | derived_criterion (short) | assessment_question (short) | act_commencement_status | rule_commencement_status | effective_from | taxonomy_dimensions |
|---|---|---|---|---|---|---|---|---|---|
| OB-DPDP-A-006-01 | consent | Act | s.6(1) | Consent is purpose-specific and limited to personal data necessary for that purpose | Does consent bind processing to a named purpose without non-necessary fields? | +18m → **2027-05-13** | n/a | **2027-05-13** | consent_architecture, purpose_binding |
| OB-DPDP-A-006-04 | consent | Act | s.6(4) | Withdrawal available with ease comparable to grant | Is withdrawal effort comparable to consent grant? | +18m → **2027-05-13** | n/a | **2027-05-13** | consent_architecture, withdrawal_propagation |
| OB-DPDP-A-006-06 | consent | Act | s.6(6) | On withdrawal, cease (and cause processors to cease) consent-based processing except other lawful authority | Does withdrawal stop consent-based processing paths (incl. processors)? | +18m → **2027-05-13** | n/a | **2027-05-13** | withdrawal_propagation |
| OB-DPDP-R-003-01 | consent / notice | Rules | r.3(b)(i) | Notice includes itemised description of personal data | Is personal data itemised in the notice? | n/a | +18m → **2027-05-13** | **2027-05-13** | consent_architecture |
| OB-DPDP-R-003-02 | consent / notice | Rules | r.3(b)(ii) | Notice states specified purpose(s) and goods/services/uses enabled | Are purposes and enabled uses described in the notice? | n/a | +18m → **2027-05-13** | **2027-05-13** | purpose_binding |
| OB-DPDP-R-003-03 | consent / notice | Rules | r.3(c)(i) | Notice gives means to withdraw with comparable ease | Does notice path expose comparable-ease withdrawal means? | n/a | +18m → **2027-05-13** | **2027-05-13** | withdrawal_propagation |
| OB-DPDP-A-008-05 | security | Act | s.8(5) | Reasonable security safeguards to prevent personal data breach | Are reasonable security safeguards present for personal data held/controlled? | +18m → **2027-05-13** | n/a | **2027-05-13** | *(technical; no single obligation dimension)* |
| OB-DPDP-R-006-01 | security | Rules | r.6(1)(a) | Minimum safeguard: encryption/obfuscation/masking/virtual tokens for personal data | Is personal data protected by one of the listed technical measures? | n/a | +18m → **2027-05-13** | **2027-05-13** | *(crypto/exposure surface; not logging)* |
| OB-DPDP-R-006-02 | security / logging | Rules | r.6(1)(c) | Visibility of access via logs/monitoring/review enabling detection of unauthorised access | Are access logs/monitoring present for personal-data access? | n/a | +18m → **2027-05-13** | **2027-05-13** | **access_logging_demonstrability** |
| OB-DPDP-A-008-06 | breach | Act | s.8(6) | On personal data breach, intimate Board and each affected Data Principal as prescribed | Is there a path to intimate Board and affected principals on breach? | +18m → **2027-05-13** | n/a | **2027-05-13** | breach_notification |
| OB-DPDP-R-007-01 | breach | Rules | r.7(1) | Without delay, intimate each affected principal with prescribed content elements | Does principal-facing breach intimation cover prescribed content? | n/a | +18m → **2027-05-13** | **2027-05-13** | breach_notification |
| OB-DPDP-R-007-02 | breach | Rules | r.7(2) | Intimate Board without delay (summary) and within 72 hours (detailed) | Are Board intimation timelines/content paths defined? | n/a | +18m → **2027-05-13** | **2027-05-13** | breach_notification |
| OB-DPDP-A-008-07 | retention | Act | s.8(7) | Erase when consent withdrawn or purpose no longer served (unless law requires retention); cause processors to erase | Is there an erasure path tied to withdrawal/purpose-end? | +18m → **2027-05-13** | n/a | **2027-05-13** | retention_erasure |
| OB-DPDP-A-016-01 | localization | Act | s.16(1) | Transfers restricted to countries/territories as Central Government may notify | Does outbound transfer logic respect notified restriction mechanism? | +18m → **2027-05-13** | n/a | **2027-05-13** | data_localization |
| OB-ABDM-HDMP-15-04 | ABDM identity | ABDM_HDMP | cl.15.4 | Personal data of a data principal is linked to their Health ID | Are patient personal-data records bound to a Health ID identifier where Health ID is used? | n/a (policy) | n/a | **policy — HDMP** | abha_identity |
| OB-ABDM-HDMP-27-05a | ABDM logging | ABDM_HDMP | cl.27.5(a) | Strict audit trail of all processing activities with access to personal data; record enabling audit/review of use | Is there an audit trail of personal-data access/processing activities? | n/a (policy) | n/a | **policy — HDMP** | access_logging_demonstrability |
| OB-ABDM-NRCES-FHIR-01 | ABDM FHIR | NRCeS_FHIR_IG | IG v6.5.0 profiles | Interchange resources declare/conform to applicable NRCeS ABDM StructureDefinition profiles (package `ndhm.in#6.5.0`) | Do exchanged FHIR resources carry/validate against the relevant ABDM profile (e.g. `meta.profile` / StructureDefinition expectations)? | n/a | n/a | **IG v6.5.0 (generated 8 May 2025)** | fhir_conformance |
| OB-ABDM-HDMP-16-04 | ABDM identity (org) | ABDM_HDMP | cl.16.4 | No denial of health facility/service merely for lacking/not disclosing Health ID / non-participation | Can care proceed without requiring Health ID creation/disclosure? | n/a (policy) | n/a | **policy — HDMP** | abha_identity |

**Note on OB-ABDM-HDMP-16-04:** Strong candidate for `criterion_underspecified` if treated as code-pattern criterion — it is primarily an organisational service-delivery rule. Kept for flag exercise; **not** a substitute for technical ABDM rows above.

### Quoted anchors (additions / logging)

**OB-DPDP-R-006-02** — Rules r.6(1)(c): “visibility on the accessing of such personal data, through appropriate logs, monitoring and review, for enabling detection of unauthorised access, its investigation and remediation to prevent recurrence”

**OB-ABDM-HDMP-15-04** — “The personal data of a data principal shall be linked to his/her Health ID, and any data principal in possession of such a Health ID shall be deemed to be the owner of such personal data.”

**OB-ABDM-HDMP-27-05a** — “The data fiduciaries should maintain a strict audit trail of all processing activities which have access to any personal data, at all times. A record of how such personal data is processed by the data fiduciary should also be maintained in a manner that enables the audit and review of any use of such personal data.”

**OB-ABDM-NRCES-FHIR-01** — NRCeS FHIR IG for ABDM v6.5.0: profiles “define the minimum mandatory elements and terminology requirements that MUST be present”; package `ndhm.in#6.5.0` (landing / Profiles page). Exact `meta.profile` wording: stamp from IG StructureDefinition page when coding.

**OB-ABDM-HDMP-16-04** — cl.16.4 non-exclusion (unchanged).

Prior DPDP Act/Rules quotes: see register history / SCHEMA examples; page-verify before freeze.
