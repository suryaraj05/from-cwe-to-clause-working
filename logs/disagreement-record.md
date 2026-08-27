# Disagreement / conflict record

Use when sources conflict (e.g. arXiv version study counts, vendor WASA claims vs absence of primary text, draft vs notified Rules).

| Date | Topic | Source A | Source B | Resolution | Affects register? |
|---|---|---|---|---|---|
| 2026-08-27 | WASA primary specification | Vendor/auditor marketing pages describe M1/M2/M3, VCC, Safe-to-Host, CERT-In | No NHA/ABDM public WASA standard located | Treat as **finding**: no public WASA spec; do not invent register rows; map adjacent obligations to OWASP / ABDM HDMP / CERT-In | Yes — blocks WASA-keyed rows |

---

## Main-matrix dual-coding disagreements (2026-08-27)

Rule pin: `cell-coding-rule` v0.3-frozen · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`.  
Raw dual table: `mapping/main-matrix-dual.csv`. Both coder originals retained.  
**Reconciled 2026-08-27** → `mapping/main-matrix-reconciled.csv`, `mapping/reconciliation-record.md`.

### In reported kappa (*n* = 158)

| Cell | coder_a | coder_b | **Consensus** | Resolution |
|---|---|---|---|---|
| CAT-06 × A-006-04 | Pp | N | **N** | Authn/authz RCM ≠ comparable-ease withdrawal UX; side coder_b |

### Pilot-excluded (handling A — not in κ)

| Cell | coder_a | coder_b | **Consensus** | Resolution |
|---|---|---|---|---|
| CAT-05 × A-006-01 | Pp | N | **Pp** | Pilot P04; side coder_a |
| CAT-06 × A-006-06 | Pp | N | **Pp** | Pilot P03; side coder_a |
| CAT-05 × R-006-01 | Pp | N | **Pp** | Pilot P02; side coder_a |
| CAT-07 × R-006-01 | F | Pp | **F** | Pilot P01; side coder_a |

Agreed non-default pattern: all CAT × A-008-05 = Pp/Pp → consensus Pp.  
Logging columns R-006-02 and HDMP-27-05a = N/N → consensus N (all CATs).
