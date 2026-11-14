# Human coder A — sample pass

**Coder name:** Surya  
**Date:** 2026-11-14  
**Rule:** `cell-coding-rule` v0.3-frozen  
**Do not look at:** `main-matrix-reconciled.csv` / coder B’s file until both finish  

**Labels:** `F` = fully_covered · `P` = partially_covered · `N` = not_visible  
**If P:** write `Pp` or `Pd` in subflag column  

---

## Column 1 — R-006-02 (access logs / monitoring)

**Criterion:** Visibility of access via logs/monitoring for detecting unauthorised access.  
**Question:** Are access logs/monitoring present for personal-data access?

| CAT | Verdict (F/P/N) | Subflag | Justification (short) |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Injection only tracks untrusted input in commands/queries. |
| CAT-02 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Memory Management only tracks allocation/bounds safety. |
| CAT-03 | N | | RCM can be category-clean while access logs/monitoring remain absent, because File Management only tracks path traversal/uploads/permissions. |
| CAT-04 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Deserialization only tracks untrusted object deserialization. |
| CAT-05 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Sensitive Data Exposure only tracks PII/secret leaks. |
| CAT-06 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Authn/Authz only tracks identity and access enforcement. |
| CAT-07 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Cryptography only tracks algorithm/key/hashing soundness. |
| CAT-08 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Resource Management only tracks resource lifetime/leaks. |
| CAT-09 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Coding Standards only tracks safe language/API practices. |
| CAT-10 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Error Handling (incl. CWE-117) presupposes logs rather than verifying access-log existence. |

*If all N, you may write one shared justification here:*  
No Bašić category inventory checks for the existence or sufficiency of access logs/monitoring; even CAT-10 (CWE-117) only sanitizes log output if logs already exist.

---

## Column 2 — HDMP-27-05a (audit trail)

**Criterion:** Strict audit trail of processing activities with access to personal data.  
**Question:** Is there an audit trail of personal-data access/processing?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while an audit trail remains absent, because Injection only tracks input/interpreter safety. |
| CAT-02 | N | | RCM can be category-clean while an audit trail remains absent, because Memory Management only tracks memory safety. |
| CAT-03 | N | | RCM can be category-clean while an audit trail remains absent, because File Management only tracks filesystem path/upload controls. |
| CAT-04 | N | | RCM can be category-clean while an audit trail remains absent, because Deserialization only tracks safe deserialization. |
| CAT-05 | N | | RCM can be category-clean while an audit trail remains absent, because Sensitive Data Exposure only tracks exposure prevention. |
| CAT-06 | N | | RCM can be category-clean while an audit trail remains absent, because Authn/Authz only tracks authentication and access enforcement. |
| CAT-07 | N | | RCM can be category-clean while an audit trail remains absent, because Cryptography only tracks cryptographic primitives/keys. |
| CAT-08 | N | | RCM can be category-clean while an audit trail remains absent, because Resource Management only tracks non-memory resource allocation/release. |
| CAT-09 | N | | RCM can be category-clean while an audit trail remains absent, because Coding Standards only tracks safe API/language usage. |
| CAT-10 | N | | RCM can be category-clean while an audit trail remains absent, because Error Handling only tracks exception/return checks and log sanitization (CWE-117). |

*Shared justification if all same:*  
Audit-trail creation and retention are outside every Bašić category's CWE vocabulary; remediating any category leaves audit-trail presence unverified.

---

## Column 3 — A-008-05 (reasonable security safeguards)

**Criterion:** Reasonable security safeguards to prevent personal data breach.  
**Question:** Are reasonable security safeguards present for personal data?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | P | Pp | Shared: SQL/command/XSS input safeguards (CWE-89/79/78). Missing from RCM guarantee: full breadth of reasonable safeguards across non-injection vectors. |
| CAT-02 | P | Pd | Tiebreak: memory-safety fixes (CWE-119/787) prevent memory-corruption breaches, though "reasonable safeguards" is broad. Candidate shared: memory corruption prevention. |
| CAT-03 | P | Pp | Shared: path traversal and file permission controls (CWE-22/732-adjacent file checks). Missing from RCM guarantee: holistic safeguard coverage beyond file handling. |
| CAT-04 | P | Pd | Tiebreak: safe deserialization (CWE-502) prevents RCE/tampering breaches, though narrow. Candidate shared: object integrity validation. |
| CAT-05 | P | Pp | Shared: preventing cleartext storage/transmission and PII leaks (CWE-200/312/319). Missing from RCM guarantee: organizational and non-exposure technical controls. |
| CAT-06 | P | Pp | Shared: authentication and access-control enforcement (CWE-284/287/306). Missing from RCM guarantee: non-AuthN/AuthZ technical and operational safeguards. |
| CAT-07 | P | Pp | Shared: sound cryptographic algorithms and key handling (CWE-327/321/326). Missing from RCM guarantee: access control, input validation, and non-crypto safeguards. |
| CAT-08 | N | | RCM can be category-clean while breach-prevention safeguards remain absent, because Resource Management only tracks resource leaks and lifetime limits (CWE-404/772). |
| CAT-09 | N | | RCM can be category-clean while security safeguards remain absent, because Coding Standards is a residual syntax/API bucket (CWE-758) not defining data-breach controls. |
| CAT-10 | P | Pd | Tiebreak: safe error handling (CWE-703/252) avoids fail-open states, though indirect. Candidate shared: fail-safe exception handling. |

---

## Column 4 — R-006-01 (encryption / masking / tokens)

**Criterion:** Minimum safeguard — encryption / obfuscation / masking / virtual tokens.  
**Question:** Is personal data protected by one of the listed measures?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Injection only tracks input/query sanitization. |
| CAT-02 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Memory Management only tracks memory bounds and lifetime. |
| CAT-03 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because File Management only tracks path and upload safety. |
| CAT-04 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Deserialization only tracks unsafe object deserialization. |
| CAT-05 | P | Pp | Shared: avoiding cleartext storage/transmission of sensitive data (CWE-312/319/256). Missing from RCM guarantee: mandatory encryption/masking/tokenization of all personal data fields. |
| CAT-06 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Authn/Authz only tracks login and access control (note: CWE-522 covers credential protection, not general personal data). |
| CAT-07 | P | Pp | Shared: sound cryptographic algorithms and key management when crypto is used (CWE-327/326/321). Missing from RCM guarantee: ensuring encryption/masking/tokens are actually applied to all personal data at rest/transit. |
| CAT-08 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Resource Management only tracks resource release/limits. |
| CAT-09 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Coding Standards only tracks safe API/language practices. |
| CAT-10 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Error Handling only tracks exception and return-value checks. |

---

## Column 5 — A-006-04 (comparable-ease withdrawal)

**Criterion:** Withdrawal available with ease comparable to grant.  
**Question:** Is withdrawal effort comparable to consent grant?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while consent withdrawal remains absent, because Injection only tracks input/interpreter safety. |
| CAT-02 | N | | RCM can be category-clean while consent withdrawal remains absent, because Memory Management only tracks memory safety. |
| CAT-03 | N | | RCM can be category-clean while consent withdrawal remains absent, because File Management only tracks filesystem path/upload safety. |
| CAT-04 | N | | RCM can be category-clean while consent withdrawal remains absent, because Deserialization only tracks object deserialization safety. |
| CAT-05 | N | | RCM can be category-clean while consent withdrawal remains absent, because Sensitive Data Exposure only tracks PII/secret exposure. |
| CAT-06 | P | Pd | Tiebreak: access revocation/state transitions (CWE-284/285/841) touch permission enforcement, though consent UX parity is missing. Candidate shared: access-state enforcement. |
| CAT-07 | N | | RCM can be category-clean while consent withdrawal remains absent, because Cryptography only tracks crypto algorithm/key soundness. |
| CAT-08 | N | | RCM can be category-clean while consent withdrawal remains absent, because Resource Management only tracks resource allocation/release. |
| CAT-09 | N | | RCM can be category-clean while consent withdrawal remains absent, because Coding Standards only tracks safe language/API usage. |
| CAT-10 | N | | RCM can be category-clean while consent withdrawal remains absent, because Error Handling only tracks exception handling. |

---

## Coder A notes

Hardest cells: CAT-07 × R-006-01 (deciding between F and Pp since Cryptography checks sound crypto but doesn't guarantee every personal-data store is encrypted/masked/tokenized); CAT-06 × A-006-04 (whether AuthZ state enforcement counts as a shared observable for withdrawal); A-008-05 across technical CWE categories.  
Anything that felt underspecified: A-008-05 ("reasonable security safeguards") is very broad, forcing reliance on `partial_by_default` for narrower categories like Memory Management and Error Handling.  

**Status:** [x] Finished alone — ready to compare