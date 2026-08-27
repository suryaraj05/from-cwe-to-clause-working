# Main matrix coding — protocol for this pass

**Rule:** `cell-coding-rule` v0.3-frozen  
**Register:** `register-v0.3-mvp-2026-08-27`  
**Profiles:** `cat-profiles-v0.1-2026-08-27`  
**Order:** by obligation column (all CATs for one OB, then next OB)  
**Excluded from Gap-1 matrix:** `OB-ABDM-HDMP-16-04` (`org_policy_not_code_pattern`)  
**Labels:** `F`=fully_covered · `Pp`=partially_covered+partial_positive · `Pd`=partially_covered+partial_by_default · `N`=not_visible · `U`=criterion_underspecified  

**Pilot cells:** excluded from kappa (handling A) — still listed in full matrix for completeness but flagged `pilot_exclude=1` where they match pilot sheet.

**Status (2026-08-27):** dual coding complete · reconciliation complete → [`main-matrix-reconciled.csv`](main-matrix-reconciled.csv). Human validation: [`../validation/human-next-steps.md`](../validation/human-next-steps.md).

## Columns in matrix (17)

A-006-01, A-006-04, A-006-06, R-003-01, R-003-02, R-003-03, A-008-05, R-006-01, R-006-02, A-008-06, R-007-01, R-007-02, A-008-07, A-016-01, HDMP-15-04, HDMP-27-05a, NRCES-FHIR-01

## Pilot-exclude set (handling A)

CAT-07×R-006-01, CAT-05×R-006-01, CAT-06×A-006-06, CAT-05×A-006-01, CAT-05×HDMP-15-04, CAT-01×R-007-01, CAT-01×R-003-01, CAT-09×A-016-01, CAT-01×NRCES-FHIR-01, CAT-03×R-006-02, CAT-10×R-006-02, CAT-10×HDMP-27-05a
