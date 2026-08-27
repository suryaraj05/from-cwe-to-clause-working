# Pilot cell selection & prior expectations

**Register version:** `register-v0.3-mvp-2026-08-27`  
**Category profiles:** `cat-profiles-v0.1-2026-08-27` (with CAT-10 CWE-117 trap note)  
**Selection rule (before coding):** 3 expected `fully_covered` (or near), 3 `partially_covered`, 3 `not_visible`, + hardest boundary cells (logging trap, FHIR, ABHA).  
**Pilot handling at freeze:** A or B (record in decision log).

| cell_id | category | obligation_id | prior expectation | why expected | actual | match? |
|---|---|---|---|---|---|---|
| P01 | CAT-07 Crypto | OB-DPDP-R-006-01 | fully_covered or partial_positive | Encryption explicitly in r.6(1)(a) and CAT-07 core | | |
| P02 | CAT-05 Sens. exposure | OB-DPDP-R-006-01 | partially_covered | Masking/exposure surface; not full safeguard set | | |
| P03 | CAT-06 AuthZ | OB-DPDP-A-006-06 | partially_covered | Access may stop; consent/withdrawal specifics missing | | |
| P04 | CAT-05 Sens. exposure | OB-DPDP-A-006-01 | partially_covered | Over-collection vs exposure; purpose-binding missing | | |
| P05 | CAT-05 Sens. exposure | OB-ABDM-HDMP-15-04 | partially_covered | Identifier/PII linkage may touch exposure; Health ID binding not in CAT-05 | | |
| P06 | CAT-01 Injection | OB-DPDP-R-007-01 | not_visible | Injection-clean ≠ breach intimation content | | |
| P07 | CAT-01 Injection | OB-DPDP-R-003-01 | not_visible | Injection-clean ≠ itemised notice | | |
| P08 | CAT-09 Coding std | OB-DPDP-A-016-01 | not_visible | Coding standards ≠ transfer restriction | | |
| P09 | CAT-01 Injection | OB-ABDM-NRCES-FHIR-01 | not_visible | Injection-clean ≠ NRCeS profile conformance | | |
| P10 | CAT-03 File mgmt | OB-DPDP-R-006-02 | **not_visible** | Inventory 22/35/377/434/641 — no access-logging existence; “logs are files” is a pun, not a shared observable | | |
| P11 | CAT-10 Error handling | OB-DPDP-R-006-02 | **not_visible (hardest)** | CWE-117 presupposes logs; RCM does not evidence access-log existence/sufficiency | | |
| P12 | CAT-06 AuthZ | OB-ABDM-HDMP-16-04 | hardest / may flag underspecified | Org service-delivery rule; AuthZ vocabulary misfits | | |
| P13 | CAT-10 Error handling | OB-ABDM-HDMP-27-05a | **not_visible** | Same CWE-117 trap against HDMP audit-trail existence | | |

**Learning signal:** expectation vs verdict divergence. Do not bend the rule to match expectations unless a real defect appears.
