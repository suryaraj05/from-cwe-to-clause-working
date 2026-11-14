# Validation report

**Version:** `validation-v0.2-2026-11-14`  
**Status:** matrix sample human-validated; case study + Delphi still open  
**Full plan:** [`validation-plan.md`](validation-plan.md)

---

## 1. Matrix inter-rater reliability

### 1a. Agent pass (historical, exploratory)

| Metric | Result |
|---|---|
| Linearly weighted Cohen’s κ | 0.949 |
| *n* (non-pilot) | 158 |
| Note | Coder B was agent; prevalence of `not_visible` inflates κ |

### 1b. Human sample pass (2026-11-14) — primary trust signal now

| Metric | Result |
|---|---|
| Coders | Surya (A), Rahul (B) |
| Cells | 50 (10 CATs × 5 obligations) |
| Raw agreement | **46/50 = 92%** |
| Disagreements adjudicated | 4 |
| Gap 1 (logging columns) | **20/20 `not_visible`** (unanimous) |

Artifacts: `mapping/human-coder-A.md`, `human-coder-B.md`, `human-sample-compare.md`, `human-sample-results.md`

---

## 2. Structural findings (post human patch)

| Finding | Evidence |
|---|---|
| Logging Gap 1 | 20/20 `not_visible` — human-confirmed |
| Sparse visibility | **158/170** `not_visible` (92.9%) |
| Fully covered | **0** after human correction of CAT-07 × R-006-01 to Pp |
| A-008-05 | Not uniform: CAT-08/09 = N; several Pd; others Pp |

---

## 3. WASA transparency finding

Unchanged — no public official WASA specification.  
`paper/findings-wasa-transparency.md`

---

## 4. Coverage ratio (MVP)

18 register rows; partial instrument coverage by design.  
`validation/coverage-ratio.md`

---

## 5. Nickerson taxonomy check

Objective conditions largely met; subjective conditions pending Delphi (if required).  

---

## 6. Evaluation checklist

| Component | Status |
|---|---|
| Human sample coding (50 cells) | **Done** |
| Matrix patched to human consensus | **Done** |
| Mentor sign-off on reconciliation | Pending |
| Rubric case study | **Next** — evidence index ready |
| Expert Delphi | Only if guide requires |
| Full 170 human dual coding | Optional |

---

## 7. Conclusion (interim)

Human sample coding **confirms Gap 1** and **tightens** the earlier agent “fully covered” crypto cell to partial. The instrument works as designed: CWE-shaped categories do not guarantee Indian logging duties. Next evaluation step is a **documentary case study** applying the rubric to a healthcare evidence pack.
