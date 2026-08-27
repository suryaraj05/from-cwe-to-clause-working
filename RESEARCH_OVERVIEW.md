# Research overview — complete project document

**Title:** From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM  

**Team:** Undergraduate CS research (India), mentor-approved  
**As of:** 2026-08-27  
**Constraint:** Documents only — no application code, scripts as deliverables, static analysis, notebooks, or tooling  

**Read next:** Integrated thesis draft → [`paper/draft-manuscript.md`](paper/draft-manuscript.md)  
**Team checklist:** [`validation/human-next-steps.md`](validation/human-next-steps.md)  
**Live tracker:** [`validation/project-status.md`](validation/project-status.md)

**Repositories:**
- Private working (with PDFs): https://github.com/suryaraj05/from-cwe-to-clause-working  
- Public artifact (no third-party PDFs): https://github.com/suryaraj05/from-cwe-to-clause-artifact  

---

## 1. What this research is about

### 1.1 Problem

Healthcare teams in India increasingly use AI coding assistants to build patient-data modules. Security research shows AI-generated code is often vulnerable. Bašić and Giaretta (arXiv:2412.15004**v4**) consolidate findings from **21 studies** into **ten CWE-mapped vulnerability categories** — a jurisdiction-agnostic technical vocabulary.

Indian healthtech is also bound by the **Digital Personal Data Protection Act 2023**, **DPDP Rules 2025**, and **ABDM** instruments (Health Data Management Policy, NRCeS FHIR IG). Those sources impose duties — purpose-bound consent, access logging, audit trails, breach intimation, Health ID linkage, FHIR conformance — that **CWE categories do not express**.

**No existing instrument** tells a team whether an AI-generated patient-data module **exhibits patterns consistent with those Indian obligations** when assessed only through ordinary CWE-shaped categories.

### 1.2 Research question

> Given Bašić’s ten-category taxonomy and atomic obligations derived from DPDP and ABDM primary sources, **which regulatory observables are visible—or not—when a patient-data module is assessed and remediated under each category’s ordinary technical standard?**

### 1.3 The three gaps we address

| Gap | Statement |
|---|---|
| **Gap 1 (structural)** | CWE-shaped categories cannot represent legal obligations (e.g. itemised consent, access-log demonstrability). |
| **Gap 2 (instrument)** | No DPDP/ABDM obligation register for assessing **AI-generated** healthcare code. |
| **Gap 3 (jurisdiction)** | AI-code security research has no Indian regulatory dimension — models may produce plausible non-Indian compliance shapes. |

### 1.4 Scope honesty (standing claim)

We assess whether a module **exhibits compliant patterns** relative to derived criteria. That is **necessary but not sufficient** for legal compliance, which also depends on organisational process invisible in code or design documents.

We do **not** build software, run scans, or generate code. Every deliverable is a **document**.

### 1.5 Paradigm and methods cited

| Method | Role in our work |
|---|---|
| **Hevner et al. (design science)** | Build an artefact (framework) + evaluate it |
| **GuideMe (Ayala-Rivera & Pasquale)** | Obligation extraction → register rows |
| **Nickerson et al.** | Extended taxonomy + ending conditions |
| **Bašić & Giaretta v4** | Matrix row vocabulary (ten categories, 21 studies) |

---

## 2. What we built (the artefact)

Five linked deliverables:

| # | Deliverable | What it is | Primary location |
|---|---|---|---|
| **1** | **Obligation register** | Atomic criteria quoted/derived from DPDP Act, DPDP Rules, ABDM HDMP, NRCeS FHIR IG — with commencement dates, assessment questions, evidence requirements | `register/obligation-register.md` |
| **2** | **Extended taxonomy** | Bašić ten categories **plus** obligation-level dimensions (consent, logging, FHIR, etc.) | `taxonomy/extended-taxonomy.md` |
| **3** | **Cross-mapping matrix** | 10 categories × 17 obligations = **170 cells** — each cell states whether a *remediated-under-category module (RCM)* guarantees the criterion | `mapping/main-matrix-reconciled.csv` |
| **4** | **Assessment rubric** | How to score a real module/document pack: Pass / Partial / Fail / Not assessable via CWE taxonomy | `rubric/assessment-rubric.md` |
| **5** | **Validation report** | Evaluation evidence: κ, coverage, protocols for Delphi and case study | `validation/validation-report.md` |

**Coding rule (frozen):** `mapping/cell-coding-rule.md` v0.3-frozen — defines RCM, three verdicts, partial sub-flags, closed legal-concept list, weighted κ as primary IRR statistic.

---

## 3. What we did till now (timeline summary)

### Phase A — Foundation (2026-08-27)

- Created markdown-first repository structure; downloaded and catalogued primary sources (`sources.md`).
- Pinned Bašić **arXiv v4**; verified **21 studies** from PDF; extracted **category profiles** with CWE inventories.
- Built register **schema** and GuideMe-adapted **coding protocol**.
- Read **G.S.R. 843(E)** commencement; populated Act/Rules commencement columns (most substantive duties → **2027-05-13**).
- Reclassified **WASA** as object of study (no public official spec) — not a register source.

### Phase B — Instrument design

- Wrote cell-coding rule; incorporated **seven amendments** (RCM counterfactual, partial sub-flags, closed legal concepts, weighted κ, etc.).
- Ran **pre-freeze pilot** (13 cells); fixed one real rule defect (logging as shared observable).
- **Froze** rule v0.3; pinned register v0.3-mvp and category profiles v0.1.
- Added **`access_logging_demonstrability`** dimension; expanded register to **18 MVP rows** (17 in matrix).

### Phase C — Evidence and findings

- **PDF-verified Gap 1:** Bašić v4 has no logging-existence CWEs (778, 779, 223, 532, 1295 absent; “logging” absent as topic; only CWE-117 under Error Handling).
- Documented **WASA transparency finding** (no citable official specification).
- Page-stamped register loci from local gazette PDFs (`register/page-stamps.md`).

### Phase D — Main matrix

- **Dual-coded** all 170 cells (column-wise order).
- **Linearly weighted κ = 0.949** on 158 non-pilot cells (12 pilot cells excluded, handling A).
- **Reconciled** 5 disagreements → consensus matrix.
- Published dual originals + consensus CSV + κ summary.

### Phase E — Completion pass (agent; team unavailable)

- Extended taxonomy, Nickerson checklist, rubric, validation plan/report, coverage ratio.
- Delphi and case-study **protocols** (design only).
- Paper section drafts + **integrated manuscript** (`paper/draft-manuscript.md`).
- Split GitHub repos: private working with PDFs; public artifact without third-party PDFs.

---

## 4. Outcomes (what we found)

### 4.1 Primary quantitative result — matrix consensus

| Verdict | Cells | % of 170 |
|---|---|---|
| `not_visible` | **156** | 91.8% |
| `partially_covered` | **13** | 7.6% (all `partial_positive`) |
| `fully_covered` | **1** | 0.6% |

**Interpretation:** For our MVP obligation set, Bašić’s ten CWE-shaped categories **do not** collectively guarantee most Indian regulatory observables when a module is only assessed through category remediation.

### 4.2 Gap 1 — access logging (strongest finding)

| Obligation | Source | Matrix (all 10 categories) |
|---|---|---|
| R-006-02 | DPDP Rules r.6(1)(c) — visibility of access via logs/monitoring | **10/10 `not_visible`** |
| HDMP-27-05a | ABDM HDMP cl.27.5(a) — audit trail of personal-data access | **10/10 `not_visible`** |

**20/20 cells** — no dual-coding or reconciliation dispute.

A module can pass every Bašić category (including CAT-10 / CWE-117) and still show **no evidence** that access or audit logging exists. CWE-117 concerns sanitizing output *to* logs; it presupposes logs exist.

Detail: `paper/findings-logging-gap1.md`

### 4.3 Other structural patterns

| Pattern | Result |
|---|---|
| **A-008-05** (Act s.8(5) reasonable safeguards) | 10/10 `partially_covered` — categories give a security *slice*, not the full statutory bar |
| **R-006-01** (Rules r.6(1)(a) encryption/masking/tokens) | CAT-07 **fully covered** (crypto → encryption path); CAT-05 partial |
| Consent, notice, breach, erasure, localization, FHIR columns | Uniformly `not_visible` except noted partials (CAT-05×A-006-01, CAT-06×A-006-06) |
| **Sole fully covered cell** | CAT-07 (Cryptography) × R-006-01 |

### 4.4 WASA transparency finding

No publicly available official NHA/ABDM WASA specification in citable clause form. We **do not** invent WASA register rows. Adjacent themes re-sourced to OWASP Top 10, ABDM HDMP, CERT-In empanelment. Reported as regulatory **transparency** finding, not only a limitation.

Detail: `paper/findings-wasa-transparency.md`

### 4.5 Reliability (exploratory)

| Metric | Value |
|---|---|
| Linearly weighted Cohen’s κ | 0.949 (*n* = 158) |
| Non-pilot disagreements before reconciliation | 1 |
| Cells reconciled | 5 |

**Caution:** κ measures **agreement**, not correctness. High κ partly reflects mass agreement on `not_visible`. Coder B was an agent pass — **human replication required** for publication-grade claims.

### 4.6 Practical implication

Healthtech teams using AI assistants should **not** treat CWE-only or OWASP-only review as sufficient for DPDP/ABDM **logging** and **consent-architecture** duties. Those require **obligation-specific** assessment beyond Bašić categories.

---

## 5. What is still pending (team work)

### 5.1 Required for “project complete” (mentor sign-off)

| # | Task | Why |
|---|---|---|
| 1 | **Human second coder** on matrix (blind re-code from frozen rule + profiles) | Publication-grade IRR; agent κ is exploratory |
| 2 | **Mentor sign-off** on reconciliation (especially CAT-06 × A-006-04 → `not_visible`) | Five cells were adjudicated without mentor |
| 3 | **Documentary case study** — apply rubric to existing hospital/healthtech audit report | Proves rubric works on real evidence (`validation/case-study.md`) |
| 4 | **Expert Delphi** (2 rounds) — if mentor requires | Face validity + Nickerson subjective conditions (`validation/delphi/protocol.md`) |
| 5 | **Thesis/report finalisation** — rewrite `draft-manuscript.md` in team voice; institution formatting | Agent draft ≠ submission final |

### 5.2 Recommended but optional

| Task | Notes |
|---|---|
| Dual-code register rows themselves | Matrix used MVP criteria; rows still draft in workflow sense |
| Expand register beyond 18 MVP rows | Broader DPDP/ABDM coverage — not claimed exhaustive today |
| Resolve HDMP-16-04 | Keep as org-policy row vs rewrite to code-visible gate (pilot flagged underspecified) |
| FHIR row exact stamp | Confirm `meta.profile` wording on specific StructureDefinition page |

### 5.3 What is **not** pending (agent-complete)

- Source manifest, category profiles, frozen coding rule, pilot, main matrix, reconciliation, consensus CSV  
- Gap 1 and WASA findings (evidenced)  
- Rubric, validation plan, partial validation report, coverage ratio  
- Integrated manuscript draft and section splits  
- Delphi/case-study **protocols** (ready to execute)

---

## 6. End goal

### 6.1 Ultimate aim

Deliver a **validated, auditable, documentary framework** that lets reviewers answer:

> *When we assess an AI-generated patient-data module using standard CWE-shaped vulnerability categories, which Indian DPDP/ABDM obligations become visible in the evidence — and which do not?*

The end product is **not software**. It is:

1. A **traceable obligation register** (quotes → criteria → evidence).  
2. An **extended taxonomy** showing where legal duties live outside CWE vocabulary.  
3. A **cross-mapping matrix** with measured inter-rater agreement.  
4. A **rubric** for applying the framework to documentary evidence.  
5. A **validation report** (κ, coverage, expert review, case study) suitable for a thesis chapter.

### 6.2 Success criteria (realistic)

| Criterion | Status |
|---|---|
| Framework artefacts exist and are version-pinned | **Met** (v0.1 drafts) |
| Gap 1 demonstrated with PDF + matrix evidence | **Met** |
| Matrix dual-coded under frozen rule | **Met** (agent pair) |
| Human-validated IRR | **Pending** |
| Rubric applied to real case | **Pending** |
| Expert acceptance (Delphi) | **Pending** (if required) |
| Mentor-approved thesis/report | **Pending** |

### 6.3 When is the project “done”?

The project is **done** when:

1. The team completes the human validation track (items in §5.1).  
2. The mentor accepts the five deliverables + thesis/report.  
3. The manuscript states scope limits honestly (pattern ≠ legal compliance; MVP register; exploratory κ until human coder confirms).

Agent work has brought the project to **submission-ready draft** status. Team work makes it **defensible**.

---

## 7. Key file map (quick reference)

| Need | File |
|---|---|
| Full thesis draft | `paper/draft-manuscript.md` |
| Matrix results (machine) | `mapping/main-matrix-reconciled.csv` |
| Matrix summary | `mapping/main-matrix-summary.json` |
| Coding rule | `mapping/cell-coding-rule.md` |
| Register (MVP) | `register/obligation-register.md` |
| Gap 1 evidence | `paper/findings-logging-gap1.md` |
| WASA finding | `paper/findings-wasa-transparency.md` |
| Rubric | `rubric/assessment-rubric.md` |
| Validation (partial) | `validation/validation-report.md` |
| Team to-do | `validation/human-next-steps.md` |
| All sources | `sources.md` |
| Decisions | `logs/decision-log.md` |

---

## 8. Version pins (do not mix)

| Artefact | Pin |
|---|---|
| Bašić paper | arXiv:2412.15004**v4** — **21 studies** |
| Cell-coding rule | v0.3-frozen |
| Register | register-v0.3-mvp-2026-08-27 |
| Category profiles | cat-profiles-v0.1-2026-08-27 |
| Manuscript | manuscript-v0.1-2026-08-27 |

Rewording after pin → log in `logs/decision-log.md` and assess re-code need.

---

*This document is the single overview for mentors, team members, and examiners. Update when human validation completes.*
