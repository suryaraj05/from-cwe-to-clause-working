# Disagreement / conflict record

Use when sources conflict (e.g. arXiv version study counts, vendor WASA claims vs absence of primary text, draft vs notified Rules).

| Date | Topic | Source A | Source B | Resolution | Affects register? |
|---|---|---|---|---|---|
| 2026-08-27 | WASA primary specification | Vendor/auditor marketing pages describe M1/M2/M3, VCC, Safe-to-Host, CERT-In | No NHA/ABDM public WASA standard located | Treat as **finding**: no public WASA spec; do not invent register rows; map adjacent obligations to OWASP / ABDM HDMP / CERT-In | Yes — blocks WASA-keyed rows |

---

## Main-matrix dual-coding disagreements (2026-08-27)

Rule pin: `cell-coding-rule` v0.3-frozen · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`.  
Raw dual table: `mapping/main-matrix-dual.csv`. Both originals kept; **reconciliation pending**.

### In reported kappa (*n* = 158)

| Cell | coder_a | coder_b | Notes |
|---|---|---|---|
| CAT-06 × A-006-04 | `partially_covered` / `partial_positive` — shared user-facing auth/access controls; missing comparable-ease withdrawal | `not_visible` — category-clean with no criterion evidence | Sole non-pilot disagreement |

### Pilot-excluded (handling A — not in κ)

| Cell | coder_a | coder_b |
|---|---|---|
| CAT-05 × A-006-01 | Pp | N |
| CAT-06 × A-006-06 | Pp | N |
| CAT-05 × R-006-01 | Pp | N |
| CAT-07 × R-006-01 | F | Pp |

Agreed non-default pattern: all CAT × A-008-05 = Pp/Pp.  
Logging columns R-006-02 and HDMP-27-05a = N/N for all CATs (no disagreement).
