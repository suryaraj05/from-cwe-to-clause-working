# Pilot worksheet (pre-freeze stress-test)

**Date:** 2026-08-27  
**Register:** `register-v0.3-mvp-2026-08-27`  
**Profiles:** `cat-profiles-v0.1-2026-08-27`  
**Rule under test:** `cell-coding-rule` v0.2 → fold → **v0.3-frozen**  
**Coder_a:** research assistant (this session)  
**Coder_b:** independent main-matrix pass completed 2026-08-27 — see `main-matrix.md` (pilot cells remain handling A / excluded from κ)  
**Pilot handling:** **A** — these pilot cells are excluded from reported reliability statistics; main pass re-codes after freeze if needed  

Expectations were sealed in `pilot-expectations.md` before this coding pass.

| cell | CAT × obligation | expectation | verdict | subflag / flag | justification | ts | match? |
|---|---|---|---|---|---|---|---|
| P01 | CAT-07 × R-006-01 | full / partial+ | **fully_covered** | — | RCM under crypto entails securing data via sound encryption; r.6(1)(a) satisfied by encryption alternative without imported-list terms. | 2026-08-27T22:40+0530 | yes (full) |
| P02 | CAT-05 × R-006-01 | partial | **partially_covered** | partial_positive | Shared: protecting sensitive data from exposure. Missing: specific r.6(1)(a) measure menu (encryption/masking/tokens). | 2026-08-27T22:41+0530 | yes |
| P03 | CAT-06 × A-006-06 | partial | **partially_covered** | partial_positive | Shared: access control / stopping access. Missing: consent-basis withdrawal + processor cessation. | 2026-08-27T22:42+0530 | yes |
| P04 | CAT-05 × A-006-01 | partial | **partially_covered** | partial_positive | Shared: limiting unnecessary sensitive-data collection/exposure. Missing: purpose-bound consent architecture. | 2026-08-27T22:43+0530 | yes |
| P05 | CAT-05 × HDMP-15-04 | partial | **not_visible** | — | RCM can be exposure-clean with no Health ID linkage evidence; CAT-05 tracks exposure CWEs, not Health ID binding. | 2026-08-27T22:44+0530 | **NO — expected partial** |
| P06 | CAT-01 × R-007-01 | not_visible | **not_visible** | — | Injection-clean while breach-intimation content absent. | 2026-08-27T22:45+0530 | yes |
| P07 | CAT-01 × R-003-01 | not_visible | **not_visible** | — | Injection-clean while itemised notice absent. | 2026-08-27T22:45+0530 | yes |
| P08 | CAT-09 × A-016-01 | not_visible | **not_visible** | — | Coding-standards RCM silent on transfer-restriction mechanism. | 2026-08-27T22:46+0530 | yes |
| P09 | CAT-01 × NRCES-FHIR-01 | not_visible | **not_visible** | — | Injection-clean while NRCeS profile conformance absent. | 2026-08-27T22:46+0530 | yes |
| P10 | CAT-03 × R-006-02 | not_visible | **not_visible** | — | Path/upload CWEs ≠ access-log existence; “logs are files” rejected. | 2026-08-27T22:47+0530 | yes |
| P11 | CAT-10 × R-006-02 | not_visible | **not_visible** | — | CWE-117 presupposes logs; RCM does not evidence access-log existence/sufficiency. | 2026-08-27T22:48+0530 | yes |
| P12 | CAT-06 × HDMP-16-04 | hardest / underspec | *(blank)* | **criterion_underspecified=true** | Criterion is organisational service-delivery (non-exclusion), not a module pattern expressible via AuthZ CWE inventory. Return to register: keep as org-policy row or rewrite to a code-visible gate check. | 2026-08-27T22:49+0530 | yes (flag) |
| P13 | CAT-10 × HDMP-27-05a | not_visible | **not_visible** | — | Same CWE-117 trap vs audit-trail *existence*. | 2026-08-27T22:50+0530 | yes |

## Divergence analysis

| Cell | Signal | Action |
|---|---|---|
| P05 | Expectation too generous (partial); rule yields not_visible | Update expectations sheet; **no rule change** — rule worked |
| P12 | Underspecified as predicted | Mark HDMP-16-04 in register as `org_policy_not_code_pattern`; optional rewrite later |

## Real rule defect folded from pilot

`partially_covered` examples listed “logging” as a concrete shared observable, contradicting the closed-list capability note. **Folded:** shared observables must come from the profile CWE inventory; logging explicitly disallowed as a Bašić shared observable.

No other rule wording defects found. Cosmetic expectation error only.

## Counts (coder_a only; not kappa)

| Verdict | n |
|---|---|
| fully_covered | 1 |
| partially_covered (all partial_positive) | 3 |
| not_visible | 8 |
| criterion_underspecified | 1 |
| partial_by_default | 0 |
