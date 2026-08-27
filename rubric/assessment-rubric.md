# Assessment rubric (Deliverable 4)

**Version:** `rubric-v0.1-2026-08-27`  
**Status:** draft — team must pilot on real documentary evidence  
**Depends on:** register `register-v0.3-mvp-2026-08-27`, matrix consensus, [`scoring-protocol.md`](scoring-protocol.md)

---

## Scope claim (mandatory in every use)

The rubric assesses whether described or supplied evidence shows **compliant patterns** relative to derived criteria. Pattern presence is **necessary but not sufficient** for legal compliance. Organisational process (e.g. HDMP cl.16.4 non-exclusion as operational policy) may fall outside code-visible assessment.

---

## Unit of assessment

One **assessment item** = one obligation register row (`derived_criterion` + `assessment_question` + `evidence_required`).

The cross-mapping matrix informs **which Bašić category assessments might surface evidence** for that item — it does not replace criterion-level judgement.

---

## Ordinal levels (criterion-level)

| Level | Code | Definition | Matrix analogue |
|---|---|---|---|
| **Pass** | P | Evidence satisfies the `assessment_question` for the criterion as stated | `fully_covered` *for some CAT* is **not** automatic Pass — rater must confirm criterion evidence directly |
| **Partial** | Pt | Some required observables present; obligation-specific elements missing or weak | Aligns with `partially_covered` *hint* only |
| **Fail** | F | Criterion observables absent or contradicted by evidence | — |
| **Not assessable via CWE taxonomy** | NA | No Bašić category RCM guarantees evidence toward this criterion; assess only via obligation-specific review | Matrix `not_visible` for **all** CATs → strong NA *hint*, not a skip of human review |

**Important:** Matrix `not_visible` means category-only assessment would not see the duty — **not** that the module is compliant. NA + separate obligation review still required.

---

## Evidence types (documentary only — no code generation)

Acceptable evidence in this project:

- Excerpts from design documents, audit reports, policy packs supplied by the team  
- Described UI flows, API contracts, log-configuration descriptions  
- Third-party audit findings (case study track)

Not in scope: running static analysis, generating code, executing modules.

---

## Matrix-informed guidance (by consensus pattern)

### Gap 1 — logging (`access_logging_demonstrability`)

| Register rows | Matrix | Rubric default |
|---|---|---|
| R-006-02, HDMP-27-05a | 10/10 `not_visible` | **Do not infer Pass from any Bašić category alone.** Require direct evidence: access logs, monitoring, audit-trail records. NA via CWE taxonomy; Pass/Fail from obligation review. |

### Security safeguard slice

| Row | Matrix | Rubric note |
|---|---|---|
| A-008-05 | 10/10 `partially_covered` | Category remediation may show *some* safeguards; rater must still apply holistic “reasonable safeguards” question — Partial common. |
| R-006-01 | CAT-07 F; CAT-05 Pp | Crypto category evidence supports encryption path; exposure category does not alone satisfy r.6(1)(a) menu. |

### Consent / notice / breach / FHIR

Matrix uniformly `not_visible` except noted partials → **obligation-specific evidence mandatory**; CWE-only review insufficient.

---

## Aggregation (reporting only — not a compliance score)

For a module assessment report:

1. Score each register row (P / Pt / F / NA).  
2. Report counts by **obligation family** and by **taxonomy dimension**.  
3. Report **Gap 1 items explicitly** (logging rows) even if NA via CWE.  
4. Do **not** sum to a single “compliance percentage” without mentor-approved denominator.

---

## Items excluded from automated matrix hinting

| Row | Reason |
|---|---|
| OB-ABDM-HDMP-16-04 | `criterion_underspecified` for code-pattern assessment — organisational policy |

---

## Pilot requirement (human)

Before thesis claims: apply rubric to **≥1 real documentary artefact** (case study) and record inter-rater agreement on **criterion scores** (separate from matrix κ).
