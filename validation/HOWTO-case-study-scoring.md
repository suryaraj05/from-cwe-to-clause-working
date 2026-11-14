# HOWTO — Case study rubric scoring (Bahmni HIP)

**Case:** Bahmni India Distro — `openmrs-module-hip` + `hip-service`  
**Evidence index:** [`case-study-evidence-index.md`](case-study-evidence-index.md)  
**Rubric:** [`../rubric/assessment-rubric.md`](../rubric/assessment-rubric.md)  
**Register:** [`../register/obligation-register.md`](../register/obligation-register.md)  
**Matrix hints:** [`../mapping/main-matrix-reconciled.csv`](../mapping/main-matrix-reconciled.csv)

---

## What this is (different from Phase 1)

| Phase 1 (done) | Phase 2 (now) |
|---|---|
| Score **categories × obligations** (visibility) | Score **this real system’s evidence** against each obligation |
| Labels: F / P / N | Labels: **Pass / Pt / Fail / NA** |
| Question: does category remediation guarantee the duty? | Question: does **Bahmni HIP evidence** show the duty pattern? |

---

## Roles

| Role | Who | File |
|---|---|---|
| Lead scorer A | _____________ | `case-study-scorer-A.md` |
| Second scorer B | _____________ | `case-study-scorer-B.md` |
| Evidence helper | _____________ | Keep index updated; help find lines in GitHub |

Work **independently**, then compare.

---

## Scores (rubric)

| Code | Meaning |
|---|---|
| **P** | Pass — evidence satisfies the assessment question |
| **Pt** | Partial — some evidence; missing obligation-specific parts |
| **F** | Fail — evidence shows absence / contradiction |
| **NA** | Not assessable via CWE taxonomy alone — still try obligation review; if no evidence either way, note “inconclusive” and prefer **F** only when absence is clear, else **Pt** or leave note |

**Always score Gap 1** (R-006-02, HDMP-27-05a) explicitly.

**Disclaimer on every report:** pattern assessment ≠ legal compliance.

---

## Steps

1. Open evidence index + register row for the obligation.  
2. Open the linked GitHub files (browser is fine).  
3. Ask the register’s `assessment_question`.  
4. Cite **file + what you saw** (method name / behaviour).  
5. Assign P / Pt / F / NA.  
6. Optionally note matrix hint (all N / some Pp) — hint only.  
7. After both finish → fill `case-study-compare.md` → tell agent to write final report.

---

## Obligation order (recommended)

1. R-006-02, HDMP-27-05a *(Gap 1)*  
2. R-006-01, A-008-05 *(crypto / safeguards)*  
3. A-006-01, A-006-04, A-006-06 *(consent)*  
4. HDMP-15-04, NRCES-FHIR-01 *(ABDM)*  
5. Remaining notice / breach / erasure / localization / HDMP-16-04  

HDMP-16-04 is **org-policy** — score as N/A-org or note underspecified; do not force P/F from code alone.

---

## Done when

- [ ] Scorer A complete  
- [ ] Scorer B complete (at least Gap 1 + encryption + consent + FHIR + Health ID)  
- [ ] Compare filled  
- [ ] Message agent: “case study scored — write report”
