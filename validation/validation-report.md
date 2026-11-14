# Validation report

**Version:** `validation-v0.3-2026-11-14`  
**Status:** matrix sample human-validated + documentary case study complete; Delphi optional  
**Full plan:** [`validation-plan.md`](validation-plan.md)

---

## 1. Matrix inter-rater reliability

### 1a. Agent pass (historical, exploratory)

| Metric | Result |
|---|---|
| Linearly weighted Cohen’s κ | 0.949 (*n* = 158 non-pilot) |
| Note | Coder B was agent; prevalence of `not_visible` inflates κ |

### 1b. Human sample pass (2026-11-14)

| Metric | Result |
|---|---|
| Coders | Surya (A), Rahul (B) |
| Cells | 50 |
| Raw agreement | **92%** (46/50) |
| Gap 1 | **20/20 `not_visible`** |

Artifacts: `mapping/human-sample-results.md`

---

## 2. Documentary case study (2026-11-14)

| Field | Result |
|---|---|
| System | Bahmni India Distro HIP (`openmrs-module-hip` + `hip-service`) |
| Scorers | Surya, Rahul |
| Obligations scored | 18 (17 matrix + HDMP-16-04) |
| Pre-adjudication agreement | **88.9%** (16/18) |
| Gap 1 on real code | **R-006-02 = F**; **HDMP-27-05a = Pt** |
| Full report | [`case-study-report.md`](case-study-report.md) |

**Consensus score mix:** 3 Pass · 4 Partial · 5 Fail · 6 NA  

Case study **confirms Gap 1** empirically: CWE-oriented reading of error handlers would not surface missing access-monitoring logs.

---

## 3. Structural matrix findings (post human patch)

| Finding | Evidence |
|---|---|
| Logging Gap 1 (matrix) | 20/20 `not_visible` |
| Logging Gap 1 (case study) | Access logs **Fail**; audit trail **Partial** |
| Matrix counts | 158 N / 12 P / 0 F |
| Crypto cell | CAT-07 × R-006-01 = Pp (human); case study R-006-01 = Pt |

---

## 4. WASA transparency

Unchanged — no public official WASA specification.  
`paper/findings-wasa-transparency.md`

---

## 5. Coverage / Nickerson

MVP register coverage documentary only. Nickerson subjective conditions still pending Delphi **if** guide requires.

---

## 6. Evaluation checklist

| Component | Status |
|---|---|
| Human sample matrix coding | **Done** |
| Matrix patched | **Done** |
| Bahmni HIP case study | **Done** |
| Mentor sign-off | Pending |
| Expert Delphi | Optional / if required |
| Full 170 human dual coding | Optional |
| Manuscript cite case study | **Done** (`paper/05-results.md`, `draft-manuscript.md` v0.2) |

---

## 7. Conclusion

The framework is **usable on real ABDM-adjacent healthcare code**. Dual human scoring worked for both the matrix sample and the Bahmni case study. Gap 1 is supported by matrix emptiness **and** case-study Fail/Partial on logging/audit duties. Remaining work is primarily mentor sign-off and final report polish (Delphi only if required).
