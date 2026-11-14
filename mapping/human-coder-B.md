# Human coder B — sample pass

**Coder name:** Rahul  
**Date:** 2026-11-14  
**Rule:** `cell-coding-rule` v0.3-frozen  
**Do not look at:** `main-matrix-reconciled.csv` / coder A’s file until both finish  

**Labels:** `F` = fully_covered · `P` = partially_covered · `N` = not_visible  
**If P:** write `Pp` or `Pd` in subflag column  

---

## Column 1 — R-006-02 (access logs / monitoring)

**Criterion:** Visibility of access via logs/monitoring for detecting unauthorised access.  
**Question:** Are access logs/monitoring present for personal-data access?

| CAT | Verdict (F/P/N) | Subflag | Justification (short) |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Injection only tracks input/command injection. |
| CAT-02 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Memory Management only tracks memory safety. |
| CAT-03 | N | | RCM can be category-clean while access logs/monitoring remain absent, because File Management only tracks file path and upload controls. |
| CAT-04 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Deserialization only tracks unsafe deserialization. |
| CAT-05 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Sensitive Data Exposure only tracks PII/credential exposure. |
| CAT-06 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Authn/Authz only tracks login and access checks. |
| CAT-07 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Cryptography only tracks crypto strength and keys. |
| CAT-08 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Resource Management only tracks resource leaks/limits. |
| CAT-09 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Coding Standards only tracks safe API/code practices. |
| CAT-10 | N | | RCM can be category-clean while access logs/monitoring remain absent, because Error Handling only tracks exception handling and log injection (CWE-117), not log presence. |

*If all N, you may write one shared justification here:*  
None of the 10 categories require generating or retaining access logs; CAT-10 (CWE-117) only checks log output neutralization when logs exist.

---

## Column 2 — HDMP-27-05a (audit trail)

**Criterion:** Strict audit trail of processing activities with access to personal data.  
**Question:** Is there an audit trail of personal-data access/processing?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while an audit trail remains absent, because Injection only tracks query/command injection. |
| CAT-02 | N | | RCM can be category-clean while an audit trail remains absent, because Memory Management only tracks buffer/pointer safety. |
| CAT-03 | N | | RCM can be category-clean while an audit trail remains absent, because File Management only tracks path traversal/upload validation. |
| CAT-04 | N | | RCM can be category-clean while an audit trail remains absent, because Deserialization only tracks deserialization validation. |
| CAT-05 | N | | RCM can be category-clean while an audit trail remains absent, because Sensitive Data Exposure only tracks data exposure flaws. |
| CAT-06 | N | | RCM can be category-clean while an audit trail remains absent, because Authn/Authz only tracks identity and authorization rules. |
| CAT-07 | N | | RCM can be category-clean while an audit trail remains absent, because Cryptography only tracks cryptographic implementation. |
| CAT-08 | N | | RCM can be category-clean while an audit trail remains absent, because Resource Management only tracks resource release and quotas. |
| CAT-09 | N | | RCM can be category-clean while an audit trail remains absent, because Coding Standards only tracks language/API usage. |
| CAT-10 | N | | RCM can be category-clean while an audit trail remains absent, because Error Handling only tracks error/return handling. |

*Shared justification if all same:*  
Strict audit-trail recording is completely absent from all 10 Bašić CWE inventories.

---

## Column 3 — A-008-05 (reasonable security safeguards)

**Criterion:** Reasonable security safeguards to prevent personal data breach.  
**Question:** Are reasonable security safeguards present for personal data?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | P | Pp | Shared: preventing SQLi/XSS/command injection data exfiltration (CWE-89/79/78). Missing from RCM guarantee: safeguards outside injection vectors. |
| CAT-02 | N | | RCM can be category-clean while breach-prevention safeguards remain absent, because Memory Management only tracks low-level memory safety (CWE-476/119) rather than data-protection safeguards. |
| CAT-03 | P | Pp | Shared: restricting unauthorized file/path access (CWE-22/434). Missing from RCM guarantee: broader application and storage safeguards. |
| CAT-04 | P | Pd | Tiebreak: blocking untrusted deserialization (CWE-502) mitigates unauthorized data access, though partial. Candidate shared: input/object integrity checks. |
| CAT-05 | P | Pp | Shared: preventing sensitive data leaks in storage/transit (CWE-200/312/319). Missing from RCM guarantee: access control, crypto, and operational safeguards. |
| CAT-06 | P | Pp | Shared: authentication and access-control enforcement (CWE-287/284/285). Missing from RCM guarantee: encryption, input validation, and non-AuthZ safeguards. |
| CAT-07 | P | Pp | Shared: strong encryption and hashing safeguards (CWE-327/328/916). Missing from RCM guarantee: access control and breach-prevention controls beyond crypto. |
| CAT-08 | N | | RCM can be category-clean while breach-prevention safeguards remain absent, because Resource Management only tracks memory/handle leaks and DoS limits (CWE-404/400). |
| CAT-09 | N | | RCM can be category-clean while breach-prevention safeguards remain absent, because Coding Standards only tracks general code hygiene (CWE-758). |
| CAT-10 | N | | RCM can be category-clean while breach-prevention safeguards remain absent, because Error Handling only tracks unchecked returns/exceptions (CWE-703/252), not personal-data safeguards. |

---

## Column 4 — R-006-01 (encryption / masking / tokens)

**Criterion:** Minimum safeguard — encryption / obfuscation / masking / virtual tokens.  
**Question:** Is personal data protected by one of the listed measures?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Injection only tracks input/query safety. |
| CAT-02 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Memory Management only tracks memory safety. |
| CAT-03 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because File Management only tracks file/path handling. |
| CAT-04 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Deserialization only tracks object deserialization. |
| CAT-05 | P | Pp | Shared: prohibiting cleartext storage/transmission of sensitive data (CWE-312/319). Missing from RCM guarantee: explicit encryption/masking/token coverage across all personal data. |
| CAT-06 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Authn/Authz only tracks login and access control. |
| CAT-07 | F | | Cryptography RCM ensures personal-data cryptographic routines use sound algorithms, key lengths, and key handling (CWE-327/326/321) without imported legal terms. |
| CAT-08 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Resource Management only tracks resource lifetime. |
| CAT-09 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Coding Standards only tracks safe API/language practice. |
| CAT-10 | N | | RCM can be category-clean while encryption/masking/tokens remain absent, because Error Handling only tracks exception handling. |

---

## Column 5 — A-006-04 (comparable-ease withdrawal)

**Criterion:** Withdrawal available with ease comparable to grant.  
**Question:** Is withdrawal effort comparable to consent grant?

| CAT | Verdict | Subflag | Justification |
|---|---|---|---|
| CAT-01 | N | | RCM can be category-clean while consent withdrawal remains absent, because Injection only tracks input/interpreter safety. |
| CAT-02 | N | | RCM can be category-clean while consent withdrawal remains absent, because Memory Management only tracks memory safety. |
| CAT-03 | N | | RCM can be category-clean while consent withdrawal remains absent, because File Management only tracks filesystem path/upload safety. |
| CAT-04 | N | | RCM can be category-clean while consent withdrawal remains absent, because Deserialization only tracks deserialization safety. |
| CAT-05 | N | | RCM can be category-clean while consent withdrawal remains absent, because Sensitive Data Exposure only tracks PII/secret exposure. |
| CAT-06 | N | | RCM can be category-clean while comparable-ease consent withdrawal remains absent, because Authn/Authz only tracks login and role/resource access checks (CWE-287/284), not consent lifecycle or UI effort parity. |
| CAT-07 | N | | RCM can be category-clean while consent withdrawal remains absent, because Cryptography only tracks cryptographic implementation. |
| CAT-08 | N | | RCM can be category-clean while consent withdrawal remains absent, because Resource Management only tracks resource allocation/release. |
| CAT-09 | N | | RCM can be category-clean while consent withdrawal remains absent, because Coding Standards only tracks safe API/language usage. |
| CAT-10 | N | | RCM can be category-clean while consent withdrawal remains absent, because Error Handling only tracks exception handling. |

---

## Coder B notes

Hardest cells: CAT-07 × R-006-01 (whether sound crypto in CWE equals guaranteeing encryption/masking/tokens for personal data); A-008-05 boundary for low-level categories like Memory Management and Error Handling.  
Anything that felt underspecified: "Reasonable security safeguards" in A-008-05 lacks an itemized technical baseline in the short criterion text.  

**Status:** [x] Finished alone — ready to compare