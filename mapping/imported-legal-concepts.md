# Closed list: imported legal / regulatory concepts

**Document ID:** `imported-legal-concepts`  
**List version:** `v1.0-closed-2026-08-27`  
**Status:** CLOSED for coding purposes until a decision-log amendment bumps the version.  
**Used by:** `cell-coding-rule.md` — `fully_covered` test (3): entailment must not require a term from this list unless that term already appears on the category definition sheet.

## Rule of use

If stating why the RCM satisfies the criterion requires any item below (or an obvious morphological variant: *purposes*, *consented*, *Data Principals*, etc.), **`fully_covered` is disallowed**. Move to `partially_covered` or `not_visible` per the cell-coding rule.

Technical words that appear in ordinary CWE/OWASP practice (e.g. authentication, authorization, encryption, logging, input validation, session, token in the *security* sense) are **not** on this list.

### Capability vs closed-list clearance (mandatory)

**Out-of-list status does *not* establish category capability.** It only means the term does not by itself bar `fully_covered` under test 3 of `cell-coding-rule.md`. Test 1 still requires that every criterion observable be entailed by the **category profile’s CWE inventory** (`taxonomy/category-profiles.md`).

**Specific consequence — logging:** No Bašić category profile contains a CWE for the *existence or sufficiency* of access/audit logging (verified absent from v4: CWE-778, 779, 223, 532, 1295; word “logging” absent as a topic). CWE-117 (CAT-10) concerns neutralization of *output written to* logs and **presupposes** logs exist — it does **not** ground coverage of “are access logs present/sufficient?” Therefore **logging / access-monitoring observables cannot ground `fully_covered` or shared-observable `partially_covered` in any Bašić row.** Coders who treat “logging is ordinary security vocabulary” as satisfying test 1 are misapplying this list.

## Closed list

### Identity of persons and roles (regulatory)
1. data principal  
2. data fiduciary  
3. data processor  
4. consent manager  
5. significant data fiduciary  
6. data protection officer (as a DPDP statutory role)  
7. Board (Data Protection Board of India) / DPBI  

### Consent and lawful processing
8. consent (as a legal basis or recorded agreement to process)  
9. purpose / specified purpose / purpose limitation / purpose binding  
10. lawful purpose / lawful basis / legitimate use (as in DPDP s.7-style grounds)  
11. notice (as a DPDP notice to the data principal)  
12. itemised description of personal data (as a notice content duty)  
13. affirmative action (as a consent formality)  
14. withdrawal (of consent)  
15. comparable ease (of withdrawal vs grant)  
16. verifiable consent / parental consent / guardian consent  

### Rights and duties toward the individual
17. right of access (to personal data / processing summary)  
18. correction / completion / updating (of personal data as a data-principal right)  
19. erasure (as a data-principal right or purpose-end duty)  
20. grievance redressal (statutory)  
21. nomination (statutory nominee)  

### Breach, retention, transfer
22. personal data breach (as a statutory intimation trigger)  
23. intimation / notification duty (to Board and/or affected data principal)  
24. retention period (as a regulatory or schedule-prescribed duration)  
25. localization / cross-border transfer restriction / notified country or territory  

### Health-ecosystem regulatory machinery (ABDM-adjacent)
26. ABHA / Ayushman Bharat Health Account (as identity construct)  
27. HIE-CM / health information exchange consent mediation  
28. HIP / HIU (as ABDM participant roles)  
29. FHIR profile / IG conformance (as a regulatory interchange obligation — distinct from “uses JSON”)  

### Catch-alls that smuggle law into technical entailment
30. “compliance with DPDP / ABDM / Rules” (as a blanket claim)  
31. “privacy policy” / “terms of service” **when used as a substitute for DPDP notice or consent**  

## Explicitly out of list (allowed in `fully_covered` entailments)

Examples: password, credential, session fixation, SQL injection, XSS, buffer overflow, insecure deserialization, path traversal, cryptographic algorithm/key management, access-control list, role-based access, audit log (technical), TLS, secrets in source, rate limiting — unless the criterion redefines them via a listed legal concept.

**Again on “audit log (technical)”:** permitted by the closed list only as *not a legal-concept bar*. It still **cannot** support coverage under any Bašić category until a profile’s CWE inventory actually assesses log *existence/sufficiency* — which none currently do. See capability note above.

## Amendment rule

To add/remove an item: decision-log entry, bump this file’s list version, bump `cell-coding-rule` version, and — if freeze already happened — re-evaluate whether affected cells need re-coding.
