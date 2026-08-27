# Pilot cell selection & prior expectations

**Register version:** `register-v0.2-mvp-2026-08-27`  
**Category profiles:** `cat-profiles-v0.1-2026-08-27`  
**Selection rule (stated before coding):** 3 expected `fully_covered`, 3 expected `partially_covered`, 3 expected `not_visible`, +2 hardest boundary cells.  
**Pilot handling at freeze:** choose A or B then (per rule).

| cell_id | category | obligation_id | prior expectation | why expected | actual verdict (fill after) | match? |
|---|---|---|---|---|---|---|
| P01 | CAT-06 AuthZ | OB-DPDP-A-008-05 | fully_covered or partial_positive | “reasonable security safeguards” may overspill AuthZ alone — mark hard if unsure | | |
| P02 | CAT-05 Sens. exposure | OB-DPDP-R-006-01 | partially_covered | encryption/masking overlaps exposure/crypto surface; not full legal safeguard set | | |
| P03 | CAT-07 Crypto | OB-DPDP-R-006-01 | fully_covered or partial_positive | listed technical measures include encryption | | |
| P04 | CAT-06 AuthZ | OB-DPDP-A-006-06 | partially_covered | access may stop; consent/withdrawal specifics not in AuthZ RCM | | |
| P05 | CAT-05 Sens. exposure | OB-DPDP-A-006-01 | partially_covered | over-collection vs exposure share surface; purpose-binding missing | | |
| P06 | CAT-01 Injection | OB-DPDP-R-007-01 | not_visible | injection-clean ≠ breach intimation content | | |
| P07 | CAT-01 Injection | OB-DPDP-R-003-01 | not_visible | injection-clean ≠ itemised notice | | |
| P08 | CAT-09 Coding std | OB-DPDP-A-016-01 | not_visible | coding standards ≠ transfer-restriction mechanism | | |
| P09 | CAT-06 AuthZ | OB-ABDM-HDMP-16-04 | hardest | non-exclusion / no Health ID gate — AuthZ vocabulary misfits | | |
| P10 | CAT-10 Error handling | OB-DPDP-R-007-02 | hardest | error paths vs Board 72h intimation — likely partial_by_default or not_visible | | |
| P11 | CAT-03 File mgmt | OB-DPDP-R-006-02 | partially_covered | logs/monitoring may touch file/audit surfaces weakly | | |

Adjust P01 if needed so the sheet still has clear “expected full” targets (e.g. swap in CAT-07 × r.6(1)(a) as definitive expected full).

**Divergence between expectation and verdict is the learning signal** — record it; do not “fix” the rule to match expectations unless a real defect appears.
