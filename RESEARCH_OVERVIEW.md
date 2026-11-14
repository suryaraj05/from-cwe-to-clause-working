# Research overview — complete project document

**Title:** From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM  

**Team:** Undergraduate CS research (India), mentor-approved  
**As of:** 2026-11-14  
**Constraint:** Documents only — no application code, scripts as deliverables, static analysis, notebooks, or tooling  

**Read next:** Integrated thesis draft → [`paper/draft-manuscript.md`](paper/draft-manuscript.md)  
**Live tracker:** [`validation/project-status.md`](validation/project-status.md)  
**Roadmap:** [`validation/COMPLETION_ROADMAP.md`](validation/COMPLETION_ROADMAP.md)

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

Five linked deliverables (**Phase 3 locked**):

| # | Deliverable | What it is | Primary location | Status |
|---|---|---|---|---|
| **1** | **Obligation register** | Atomic criteria from DPDP Act, DPDP Rules, ABDM HDMP, NRCeS FHIR IG | `register/obligation-register.md` | Locked MVP |
| **2** | **Extended taxonomy** | Bašić ten categories + obligation-level dimensions | `taxonomy/extended-taxonomy.md` | Locked draft |
| **3** | **Cross-mapping matrix** | 10 × 17 = **170 cells** | `mapping/main-matrix-reconciled.csv` | Locked + human sample |
| **4** | **Assessment rubric** | Pass / Partial / Fail / NA (+ developer guide) | `rubric/assessment-rubric.md`, `user-guide.md` | Locked + tried |
| **5** | **Validation report** | κ (exploratory), human sample, Bahmni case study | `validation/validation-report.md` | v0.3 |

**Coding rule (frozen):** `mapping/cell-coding-rule.md` v0.3-frozen.

---

## 3. What we did till now (timeline summary)

### Phase A–E — Foundation through agent completion (2026-08-27)

Sources pinned; register MVP; rule frozen; Gap 1 PDF-evidenced; main matrix dual-coded (agent); reconciliation; rubric/taxonomy/protocols; manuscript draft; split GitHub repos. Detail retained in prior overview versions / decision log.

### Phase 1 — Human sample (2026-11-14) — **DONE**

Surya + Rahul blind-coded **50 cells** (92% agree). Gap 1: 20/20 `not_visible`. Matrix patched → **158 N / 12 P / 0 F** (CAT-07 × R-006-01 F→Pp; CAT-08/09 × A-008-05 Pp→N).

### Phase 2 — Bahmni HIP case study (2026-11-14) — **DONE**

Public MIT HIP modules dual-scored with rubric (88.9% agree). R-006-02 = **Fail**; HDMP-27-05a = **Partial**. Gap 1 confirmed on real ABDM-adjacent code.

### Phase 3 — Lock deliverables (2026-11-14) — **DONE**

Register/taxonomy/matrix/rubric/validation status pages + user guide locked; coverage ratio refreshed.

### Phase 4 — Manuscript Results (2026-11-14) — **IN PROGRESS**

`paper/05-results.md` and `draft-manuscript.md` updated with Phase 1–2 evidence. Remaining: mentor sign-off, citation/formatting polish, optional Delphi.

---

## 4. Outcomes (what we found)

### 4.1 Primary quantitative result — matrix consensus (post human)

| Verdict | Cells | % of 170 |
|---|---|---|
| `not_visible` | **158** | 92.9% |
| `partially_covered` | **12** | 7.1% |
| `fully_covered` | **0** | 0% |

**Interpretation:** Bašić’s ten CWE-shaped categories do not collectively guarantee most Indian regulatory observables in our MVP set. There is **no** sole fully-covered cell after human adjudication.

### 4.2 Gap 1 — access logging (strongest finding)

| Obligation | Source | Matrix (all 10 categories) |
|---|---|---|
| R-006-02 | DPDP Rules r.6(1)(c) | **10/10 `not_visible`** |
| HDMP-27-05a | ABDM HDMP cl.27.5(a) | **10/10 `not_visible`** |

**20/20 cells** — human sample unanimous. Case study: access logs **Fail**; audit trail **Partial**.

### 4.3 Other structural patterns

| Pattern | Result |
|---|---|
| **A-008-05** | Mixed Pp/Pd; CAT-08/09 → N after human |
| **R-006-01** | CAT-05 + CAT-07 **partial only** (not full) |
| Consent / notice / breach / erasure / localization / FHIR | Mostly uniform `not_visible` except noted partials |

### 4.4 WASA transparency finding

No public official WASA specification — object of study, not a register source.

### 4.5 Reliability

| Layer | Result |
|---|---|
| Agent matrix κ (exploratory) | 0.949 (*n* = 158) |
| Human matrix sample | **92%** raw agree (50 cells) |
| Human case-study rubric | **88.9%** raw agree (18 obligations) |

### 4.6 Practical implication

CWE-only or OWASP-only review is insufficient for DPDP/ABDM **logging** and **consent-architecture** duties — use register + matrix + rubric.

---

## 5. What is still pending

| # | Task | Status |
|---|---|---|
| 1 | Mentor sign-off (reconciliation + human patches + case study) | **Open** |
| 2 | Expert Delphi | **Optional** — only if guide requires |
| 3 | Full 170 human dual coding | **Optional** |
| 4 | Final institutional formatting / citation pass | **Open** |
| 5 | MCP / tooling | **Out of scope** (future work paragraph only) |

---

## 6. End goal

Deliver a **validated, auditable, documentary framework** answering:

> *When we assess an AI-generated patient-data module using standard CWE-shaped vulnerability categories, which Indian DPDP/ABDM obligations become visible in the evidence — and which do not?*

Success criteria:

| Criterion | Status |
|---|---|
| Framework artefacts exist and are version-pinned | **Met** |
| Gap 1 demonstrated (PDF + matrix + case study) | **Met** |
| Matrix dual-coded under frozen rule | **Met** |
| Human-validated sample IRR | **Met** (sample) |
| Rubric applied to real case | **Met** (Bahmni HIP) |
| Expert acceptance (Delphi) | Optional |
| Mentor-approved thesis/report | **Pending** |

---

## 7. Key file map

| Need | File |
|---|---|
| Full thesis draft | `paper/draft-manuscript.md` |
| Results | `paper/05-results.md` |
| Matrix | `mapping/main-matrix-reconciled.csv` |
| Human sample | `mapping/human-sample-results.md` |
| Case study | `validation/case-study-report.md` |
| Rubric guide | `rubric/user-guide.md` |
| Status | `validation/project-status.md` |

---

## 8. Version pins (do not mix)

| Artefact | Pin |
|---|---|
| Bašić paper | arXiv:2412.15004**v4** — **21 studies** |
| Cell-coding rule | v0.3-frozen |
| Register | register-v0.3-mvp-2026-08-27 |
| Category profiles | cat-profiles-v0.1-2026-08-27 |
| Manuscript | manuscript-v0.2-2026-11-14 |

Rewording after pin → log in `logs/decision-log.md` and assess re-code need.
