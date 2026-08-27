# Bašić & Giaretta category profiles (matrix row vocabulary)

**Source:** Bašić, E. & Giaretta, A. *From Vulnerabilities to Remediation…* **arXiv:2412.15004v4** (local PDF + arXiv HTML cross-check).  
**Locus:** Section 4 / Table 3 (RQ1).  
**Study count (v4, read off source):** vulnerabilities in LLM-generated code are identified **“as identified in 21 studies”** and grouped into **10 categories** the authors defined for the SLR.  
**Profile version:** `cat-profiles-v0.1-2026-08-27`  
**Status:** draft for pilot; freeze with cell-coding rule.

### Important honesty on OWASP

Bašić v4 maps categories to **CWE**, not to OWASP Top 10. OWASP lines below are **project-provisional** alignments for WASA-adjacent / matrix convenience, marked `OWASP_PROVISIONAL`. They are **not** claims that Bašić asserted those OWASP IDs. Prefer CWE when applying the coding rule; use provisional OWASP only as secondary vocabulary.

**RCM reminder:** for each category, the RCM is a module assessed under that category and remediated to that category’s ordinary CWE-shaped standard.

---

### CAT-01 — Injection

| Field | Content |
|---|---|
| Name (as authors) | Injection |
| What assessment looks for (one line) | Whether untrusted input can change interpreter/command/query/page behaviour (SQL, XSS, OS command, regex, related injection). |
| CWEs frequently cited in §4.1 / Table 3 | **Core:** CWE-79, CWE-89. **Also appear in Table 3 rows:** 77, 78, 80, 83, 90, 93, 94, 95, 99, 113, 116, 134, 564, 601, 643, 918, 943 (union across studies; not every study reports all). |
| OWASP_PROVISIONAL | A03:2021 Injection (also XSS historically under injection family) |

### CAT-02 — Memory Management

| Field | Content |
|---|---|
| Name (as authors) | Memory Management |
| What assessment looks for (one line) | Whether memory is allocated, bounds-checked, and freed safely (overflows, null deref, use-after-free, related memory safety). |
| CWEs frequently cited | **Core in §4.2:** CWE-476. **Also in Table 3:** 119, 120, 125, 129, 190, 191, 401, 416, 761, 787, 788, 843. |
| OWASP_PROVISIONAL | No clean single Top-10:2021 home (often native/memory-safety). Leave blank or note “outside OWASP Top 10:2021 web focus” rather than force-fit. |

### CAT-03 — File Management

| Field | Content |
|---|---|
| Name (as authors) | File Management |
| What assessment looks for (one line) | Whether file/path handling prevents unauthorized filesystem access (path restriction, uploads, permissions). |
| CWEs frequently cited | **Core in §4.3:** CWE-22. **Also in Table 3:** 35, 377, 434, 641. |
| OWASP_PROVISIONAL | A01:2021 Broken Access Control (path traversal / unauthorized file access); upload issues may also touch A04 |

### CAT-04 — Deserialization

| Field | Content |
|---|---|
| Name (as authors) | Deserialization |
| What assessment looks for (one line) | Whether untrusted data is deserialized into objects without safe validation (RCE, tampering, DoS risk). |
| CWEs frequently cited | **Core in §4.4:** CWE-502. |
| OWASP_PROVISIONAL | A08:2021 Software and Data Integrity Failures |

### CAT-05 — Sensitive Data Exposure

| Field | Content |
|---|---|
| Name (as authors) | Sensitive Data Exposure |
| What assessment looks for (one line) | Whether sensitive information (PII, credentials, secrets) is exposed via weak protection, storage, or transmission. |
| CWEs frequently cited | **Core in §4.5:** CWE-200. **Also in Table 3:** 206, 208, 209, 215, 256, 312, 319, 385, 539. |
| OWASP_PROVISIONAL | A02:2021 Cryptographic Failures; exposure paths may also touch A01 |

### CAT-06 — Authentication and Authorization

| Field | Content |
|---|---|
| Name (as authors) | Authentication and Authorization |
| What assessment looks for (one line) | Whether identity is verified soundly and access-control policy is enforced (credentials, hard-coded secrets, improper access control). |
| CWEs frequently cited | **Authn core in §4.6:** CWE-798. **Authz core:** CWE-284. **Also in Table 3:** 250, 259, 269, 283, 285, 287, 297, 306, 352, 384, 425, 522, 601, 732, 841, 915, 941. |
| OWASP_PROVISIONAL | A07:2021 Identification and Authentication Failures; A01:2021 Broken Access Control |

### CAT-07 — Cryptography

| Field | Content |
|---|---|
| Name (as authors) | Cryptography |
| What assessment looks for (one line) | Whether crypto is present and sound (algorithms, certificates, hashing, key handling — not merely “data hidden”). |
| CWEs frequently cited | **Core in §4.7:** CWE-327. **Also in Table 3:** 295, 321, 323, 326, 328, 329, 330, 331, 338, 347, 759, 760, 916, 1204. |
| OWASP_PROVISIONAL | A02:2021 Cryptographic Failures |

### CAT-08 — Resource Management

| Field | Content |
|---|---|
| Name (as authors) | Resource Management |
| What assessment looks for (one line) | Whether non-memory/non-file resources are allocated and released safely (leaks, lifetime, port binds, related control). |
| CWEs frequently cited | **Core in §4.8:** CWE-404, CWE-772. **Also in Table 3:** 367, 400, 406, 414, 605, 664, 770, 776. |
| OWASP_PROVISIONAL | Often A05:2021 Security Misconfiguration / availability side-effects — **weak fit; mark provisional** |

### CAT-09 — Coding Standards

| Field | Content |
|---|---|
| Name (as authors) | Coding Standards |
| What assessment looks for (one line) | Whether code violates safe language/API practice (logic errors, bad calls, undefined behaviour) outside other named categories. |
| CWEs frequently cited | **Named in §4.9:** CWE-758. **Also in Table 3:** 20, 133, 369, 453, 454, 462, 563, 565, 595, 611, 617, 628, 682, 687, 691, 707, 710, 827, 1188, 1287, 1321, 1333 (broad residual bucket — use carefully). |
| OWASP_PROVISIONAL | No stable Top-10:2021 mapping; leave blank rather than invent |

### CAT-10 — Error Handling

| Field | Content |
|---|---|
| Name (as authors) | Error Handling |
| What assessment looks for (one line) | Whether exceptional conditions and return values are checked/handled so failures do not create unsafe behaviour. |
| CWEs frequently cited | **Named in §4.10:** CWE-703. **Also in Table 3:** 117, 252, 614. |
| OWASP_PROVISIONAL | Partial touch A09:2021 Security Logging and Monitoring Failures (for bad logging of errors) — **weak/partial fit only** |

**Coder trap — CWE-117:** “Improper Output Neutralization for Logs” **presupposes logs exist** and concerns sanitizing what is written to them. An RCM remediated under CAT-10 yields **no** evidence that access/audit logging is present or sufficient. Against `OB-DPDP-R-006-02` (and HDMP audit-trail criteria), the correct coverage verdict is **`not_visible`**, not `partially_covered`. Do not treat CWE-117 as a logging-*existence* capability.

---

## How coders must use this file

1. Row vocabulary = this profile’s “what assessment looks for” + listed CWEs.  
2. Do not invent CWEs not in Bašić Table 3 / §4 for that category without a decision-log amendment.  
3. `OWASP_PROVISIONAL` never alone grounds `fully_covered`.  
4. Pin this profile version in the cell-coding freeze entry alongside register version.
