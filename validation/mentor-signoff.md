# Mentor Review & Final Sign-Off Record

**Project Title:** From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM  
**Student Team:** Surya Raj Salve, Rahul  
**Frozen Rule & Register Pins:** `cell-coding-rule` `v0.3-frozen` · `register-v0.3-mvp-2026-08-27` · `cat-profiles-v0.1-2026-08-27`  
**Manuscript Version:** `manuscript-v0.3-2026-11-14`  

---

## 1. Summary of Human-Validated Outcomes for Review

| Validation Stage | Scope | Result | Key Methodological Takeaway |
|---|---|---|---|
| **Phase 1: Dual Human Matrix Coding** | 50 cells ($10 \times 5$ sample; Surya & Rahul) | **92.0%** raw agreement ($\kappa = 0.746$); 4 boundary cells adjudicated | Reconciled matrix updated to **158 N / 12 P / 0 F**. `CAT-07 × R-006-01` corrected (`F → Pp`) because sound crypto primitives do not guarantee encryption/masking of all personal data. Gap 1 logging confirmed **20/20 `not_visible`** (CWE-117 trap avoided). |
| **Phase 2: Bahmni HIP Case Study** | 18 obligations across 10 public MIT files (`openmrs-module-hip` + `hip-service`) | **88.9%** pre-adjudication agreement (16/18) | Consensus: **3 Pass / 4 Partial / 5 Fail / 6 NA**. Confirmed Gap 1 on production healthcare code (`R-006-02`: **Fail**; `HDMP-27-05a`: **Partial**). |
| **Phase 3–4: Deliverable Lock & Manuscript** | 5 Hevner DSR artefacts + `rubric/user-guide.md` + IEEE-formatted manuscript | All internal counts, pins, and citations verified | Documentary scope boundary maintained (no software/MCP deliverables; future work only). |

---

## 2. Scope & Delphi Disposition

- [ ] **Approved without Delphi:** Two-layer human validation (50-cell dual matrix coding + 18-obligation Bahmni HIP case study) is sufficient for undergraduate major-project submission; `validation/delphi/protocol.md` is retained as a documented future-work protocol.
- [ ] **Delphi Required:** Mentor requests executing Round 1 of `validation/delphi/protocol.md` prior to final binding.

---

## 3. Mentor Sign-Off

| Field | Entry |
|---|---|
| **Project Guide / Mentor Name** | ________________________________________ |
| **Department / Institution** | Rajiv Gandhi University of Knowledge Technologies (RGUKT), Basar |
| **Decision** | [ ] Approved for Final Thesis Binding & Submission  /  [ ] Revisions Requested |
| **Mentor Remarks** | ________________________________________ |
| **Signature & Date** | ________________________________________ |