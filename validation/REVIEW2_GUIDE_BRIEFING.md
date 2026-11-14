# Major Project Review 2 — Guide briefing

**Audience:** Individual mentor / guide only  
**As of:** 2026-11-10  
**Context:** Review 1 completed (introduction / literature / proposed framework). Review 2 is progress + method + findings + next steps.

**Primary files to open if she asks:**
- Overview: `RESEARCH_OVERVIEW.md`
- Manuscript draft: `paper/draft-manuscript.md`
- Matrix consensus: `mapping/main-matrix-reconciled.csv`
- Gap 1: `paper/findings-logging-gap1.md`
- Pending checklist: `validation/human-next-steps.md`

---

## 1. Current status (honest one-minute version)

**Where we are:** Design + first evaluation pass of a **documents-only** research artefact are largely built. Review 1 covered problem and proposal. Since then we have a frozen coding rule, MVP register, dual-coded matrix, Gap 1 evidence, rubric, and a draft manuscript.

**Where we are not:** Human second-coder validation, mentor sign-off on reconciliation, case study on a real audit report, Delphi (if required), and final paper in our own voice.

| Area | Status |
|---|---|
| Problem, gaps, literature | Done (Review 1) |
| Obligation register (MVP, 18 rows) | Draft, page-stamped |
| Category profiles + coding rule | **Frozen** v0.3 |
| Cross-mapping matrix (170 cells) | Dual-coded + reconciled |
| Gap 1 (logging) | Evidenced (PDF + 20/20 `not_visible`) |
| Rubric + validation plan | Draft / protocols ready |
| Paper | Draft manuscript exists |
| Human IRR / mentor sign-off | **Pending — need guide** |
| Case study + Delphi | **Pending** |

**One sentence for her:**  
*“We have built and first-evaluated the framework; Review 2 is to confirm method and findings, get your sign-off on reconciliation, and lock the next human-validation steps.”*

---

## 2. What to show her (keep short)

1. **Research question** — visibility of DPDP/ABDM obligations under Bašić CWE categories.  
2. **Five deliverables** — register, taxonomy, matrix, rubric, validation.  
3. **Main finding** — Gap 1 logging: 20/20 cells `not_visible`.  
4. **Matrix summary** — 156 N / 13 P / 1 F out of 170.  
5. **What we need from her** — reconciliation sign-off + whether Delphi is mandatory + case-study source.

Do **not** lead with κ = 0.949 as the headline. Lead with Gap 1. Mention κ only as exploratory agreement.

---

## 3. Questions she may ask — and how to answer

### A. Scope and contribution

**Q: What exactly is your contribution?**  
**A:** A documentary assessment framework that maps Bašić’s ten CWE categories against atomic DPDP/ABDM obligations, so we can measure which Indian regulatory duties become visible under ordinary technical security assessment — and which do not.

**Q: Are you building software / a tool / a scanner?**  
**A:** No. Mentor-approved scope is documents only: register, taxonomy, matrix, rubric, validation report. We do not generate or analyse code as a deliverable.

**Q: Is this legal compliance?**  
**A:** No. We assess whether **compliant patterns** are visible. That is necessary but not sufficient for legal compliance, which also needs organisational process.

**Q: How is this different from OWASP / CWE review?**  
**A:** OWASP/CWE answer technical weakness. We ask a different question: after remediating under a CWE category, does the obligation criterion become visible? Many Indian duties (especially logging) do not.

---

### B. Method (guide will probe this)

**Q: What is your unit of analysis?**  
**A:** One matrix cell = one Bašić category × one atomic obligation criterion.

**Q: What is RCM?**  
**A:** Remediated-under-Category Module — a patient-data module assessed under one category and remediated to that category’s ordinary CWE standard. Verdicts are about what that remediation **guarantees**, not about inventing a pathological system.

**Q: Why freeze the coding rule?**  
**A:** So both coders share the same operational definition before main coding. Freeze pin: rule v0.3 + register v0.3-mvp + category profiles v0.1.

**Q: Why weighted kappa?**  
**A:** Verdicts are ordinal: fully > partially > not visible. Linearly weighted κ is primary; unweighted reported alongside.

**Q: Why is κ high (0.949)? Is that suspicious?**  
**A:** Partly yes — prevalence effect. Most cells are `not_visible`, so agreement is easy. κ measures agreement, not correctness. Coder B was an independent agent pass; we treat κ as **exploratory** until a human second coder re-codes.

---

### C. Findings

**Q: What is your strongest result?**  
**A:** Gap 1 — access logging. DPDP Rules r.6(1)(c) and ABDM HDMP cl.27.5(a) require visibility of personal-data access / audit trails. Bašić v4 has no category that assesses log *existence* (CWE-778 etc. absent; only CWE-117, which presupposes logs). Matrix: **20/20 `not_visible`**, undisputed.

**Q: Only one fully covered cell — isn’t that failure?**  
**A:** No. Emptiness is an **outcome**, not a success criterion. Sparse visibility supports Gap 1: CWE vocabulary ≠ statutory vocabulary. The one full cell (crypto × encryption safeguard) shows the instrument can also detect clear technical entailment.

**Q: Why no WASA rows?**  
**A:** No public official WASA specification found. We report that as a transparency finding and re-source adjacent expectations to OWASP, ABDM HDMP, and CERT-In — we do not invent clauses.

**Q: Is the register complete for all of DPDP?**  
**A:** No. It is an MVP corpus (18 rows / 17 in matrix) spanning families for pilot and Gap 1. We do not claim exhaustive DPDP/ABDM coverage.

---

### D. Progress, AI use, and honesty

**Q: What did you finish after Review 1?**  
**A:** Frozen coding rule and pilot; MVP register with commencement and page stamps; main dual coding of 170 cells; reconciliation; Gap 1 and WASA findings; rubric; validation plan; draft manuscript.

**Q: Did AI help write this?**  
**A:** Yes, as research assistance for drafting, structuring, and an independent coding pass. Primary sources are local PDFs; clause numbers are page-stamped. Human validation and mentor sign-off are still required — we are not claiming AI coding as final IRR.

**Q: What do you need from me (the guide)?**  
**A:**  
1) Sign-off on reconciliation (especially CAT-06 × A-006-04 → `not_visible`).  
2) Confirm whether Delphi is mandatory for our department.  
3) Guidance on case-study evidence (can we use a redacted hospital audit report?).  
4) Feedback on manuscript voice and submission format.

**Q: What is left before final submission?**  
**A:** Human second coder; your reconciliation sign-off; case study; Delphi if required; rewrite paper in team voice; final citation check.

---

### E. Harder / sceptical questions

**Q: Isn’t this just saying “law ≠ CWE,” which is obvious?**  
**A:** The contribution is an **operational instrument** that measures the gap cell-by-cell under a frozen rule, with a worked Indian example (logging) verified against Bašić v4 and primary regulation — not only a verbal claim.

**Q: Can someone game `not_visible`?**  
**A:** The rule forbids existential “pathological clean-but-noncompliant” reasoning. Verdicts must be about the RCM and category CWE inventory. Pilot specifically tested the CWE-117 logging trap.

**Q: Why documents only — isn’t that weak for CS?**  
**A:** Design science allows artefact + rigorous evaluation without building a product. Our artefact is the assessment framework; evaluation is dual coding, coverage, and planned case study/Delphi. Building a scanner would change scope and mentor constraint.

**Q: When is the Act even in force?**  
**A:** Many substantive duties commence **+18 months** from G.S.R. 843(E) → **2027-05-13**. We still assess patterns now; commencement is recorded per register row.

---

## 4. Ask her these three things (end of meeting)

1. **Approve reconciliation** of the five disputed cells (or tell us which to reverse).  
2. **Confirm evaluation bar:** is human dual coding + case study enough, or is Delphi required?  
3. **Approve next milestone** for Review 3 / final: human IRR + one documentary case study + manuscript polish.

---

## 5. 60-second opening you can say

> “After Review 1, we froze the coding rule, built an MVP DPDP/ABDM obligation register, and dual-coded a 10×17 matrix. The main finding is Gap 1: access-logging duties required by DPDP Rules and ABDM are not visible under any of Bašić’s ten CWE categories — 20 out of 20 cells. We also have a draft rubric and manuscript. For Review 2 we need your guidance on reconciliation sign-off and which validation steps you want before final submission.”

---

## 6. Do / don’t

| Do | Don’t |
|---|---|
| Lead with Gap 1 | Lead with κ as proof of quality |
| Say pattern ≠ legal compliance | Claim “we ensure DPDP compliance” |
| Admit human IRR still pending | Hide that coder B was agent-assisted |
| Ask for clear next milestones | Promise Delphi/case study without a plan |
| Cite Bašić **v4**, 21 studies | Say “~20 studies” or mix arXiv versions |
