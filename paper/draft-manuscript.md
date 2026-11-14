# From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM

**Document:** `draft-manuscript.md`  
**Version:** `manuscript-v0.2-2026-11-14`  
**Status:** Results updated with Phase 1 human sample + Phase 2 Bahmni HIP case study — **not yet mentor-final**

**Open:** mentor sign-off; optional Delphi; institutional formatting.

**Artifact pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27` · matrix consensus `main-matrix-reconciled.csv` (post human sample)

**Constraint:** This project produces documents only. No application code, scripts as deliverables, static analysis runs, or code generation experiments.

---

## Abstract

Healthcare teams in India increasingly use AI coding assistants, yet security research consolidates LLM-generated vulnerabilities into CWE-shaped categories without Indian regulatory vocabulary. We design and evaluate a documentary assessment framework that maps Bašić and Giaretta’s ten vulnerability categories (arXiv:2412.15004v4; 21 studies) against atomic obligations derived from the Digital Personal Data Protection Act 2023, DPDP Rules 2025, and ABDM health-data instruments. Following GuideMe-style obligation extraction and a frozen counterfactual-visibility coding rule, we code a 10×17 cross-mapping matrix (170 cells). After human sample adjudication, **158 of 170** cells are `not_visible`: remediated-under-category assessment does not guarantee most regulatory criteria. Two human coders agreed on **92%** of a 50-cell sample (Gap 1 logging columns unanimous `not_visible`). An exploratory agent dual-coding pass yielded high κ (0.949) but is not treated as publication-grade IRR. Applying the assessment rubric to Bahmni India Distro HIP code (dual human scorers, 88.9% agree) confirmed Gap 1 on real ABDM-adjacent software: access-monitoring logs **Fail**; audit-trail evidence only **Partial**. We extend the taxonomy with obligation-level dimensions, supply a documentary rubric and developer guide, and report the absence of a public WASA specification as a regulatory-transparency finding. Pattern assessment is necessary but not sufficient for legal compliance.

**Keywords:** DPDP Act 2023; ABDM; LLM-generated code; CWE; regulatory compliance; design science; cross-mapping.

---

## 1. Introduction

### 1.1 Motivation

Indian healthtech teams adopt AI coding assistants to build patient-data modules faster. Empirical work shows AI-generated code often contains vulnerabilities; Bašić and Giaretta synthesise findings from **21 studies** into ten CWE-mapped categories for remediation-oriented review. That vocabulary is jurisdiction-agnostic. Meanwhile, the Digital Personal Data Protection Act 2023 and the ABDM health-data policy stack impose obligations—purpose-bound consent, access logging, audit trails, breach intimation—that are not expressible as CWE weaknesses alone.

No published instrument tells a team whether an AI-generated module **exhibits patterns consistent with those Indian obligations** when assessed only through ordinary CWE-shaped categories.

### 1.2 Research question

Given Bašić’s ten-category taxonomy and atomic criteria derived from DPDP and ABDM primary sources, **which regulatory observables are visible—or not—when a patient-data module is assessed and remediated under each category’s ordinary technical standard?**

### 1.3 Contribution

Following design science (Hevner et al., 2004), we deliver five documentary artefacts: (1) obligation register, (2) extended taxonomy, (3) cross-mapping matrix with human sample validation, (4) assessment rubric, (5) validation report. Evaluation combines exploratory dual coding, a human sample reliability check, coverage transparency, Nickerson ending conditions, an optional expert Delphi, and a documentary case study on Bahmni India Distro HIP.

### 1.4 Scope

We assess **compliant patterns** in described or supplied evidence. That is necessary but not sufficient for legal compliance, which also depends on organisational process invisible in code. We do not build or run software as a project deliverable.

### 1.5 Findings preview

- **Gap 1 (logging):** no Bašić category assesses access/audit log existence; Indian rules require it—uniform `not_visible` across the matrix logging columns (20/20 cells); Bahmni case study Fail/Partial on the same duties.
- **Sparse matrix overall:** 92.9% of reconciled cells are `not_visible` (158/170); zero `fully_covered` after human adjudication.
- **Human trust:** 92% raw agreement on a 50-cell sample; 88.9% on case-study rubric scores.
- **WASA transparency:** no public official WASA specification located (Section 5.5).
- **κ caution:** agent κ is exploratory; mass `not_visible` inflates agreement (Section 6).

---

## 2. Background and related work

### 2.1 AI-generated code security

Systematic reviews and empirical studies document insecure patterns in LLM-assisted development (Pearce et al.; Perry et al.; SafeGenBench). Bašić and Giaretta (arXiv:2412.15004**v4**) consolidate **21 studies** into ten vulnerability categories mapped to CWE—our matrix row vocabulary. Recent work on “vibe-coded” applications highlights AI-specific failure modes. These lines of research are **jurisdiction-agnostic** and do not encode Indian statutory consent, logging, or ABDM interchange duties.

### 2.2 Regulation-to-controls methods

Ayala-Rivera and Pasquale’s GuideMe operationalises GDPR through privacy controls—a methodological precedent for obligation extraction. No equivalent catalogue targets DPDP, ABHA/HIE-CM flows, or NRCeS FHIR profiles for **assessing code already written** by AI tools.

### 2.3 Taxonomy and design science

Nickerson et al. provide ending conditions for IS taxonomies; we extend Bašić categories with obligation-level dimensions and document cross-product outcomes. Hevner et al. frame our contribution as artefact plus rigorous evaluation. Our evaluation is documentary—dual coding, coverage ratio, optional Delphi, case study—not implementation.

### 2.4 Indian regulatory context

Primary sources: DPDP Act 2023; DPDP Rules 2025 (G.S.R. 846(E)); commencement G.S.R. 843(E); ABDM Health Data Management Policy; NRCeS FHIR IG v6.5.0. Commencement is staged; MVP register rows record +18m effective dates where verified (most substantive duties **2027-05-13**).

### 2.5 Three gaps

1. CWE categories cannot express legal obligations such as itemised consent or comparable-ease withdrawal.
2. No DPDP/ABDM obligation register for AI-generated healthcare code assessment.
3. AI-security research lacks Indian jurisdictional grounding—models may produce plausible non-Indian compliance shapes.

Our framework addresses these at the **pattern-assessment** level, with explicit limits.

---

## 3. Method

### 3.1 Research paradigm

We follow design science: a designed framework plus rigorous evaluation. Evaluation is documentary (register coverage, dual coding, linearly weighted kappa as exploratory statistic, human sample agreement, case-study application to public HIP sources). We do not generate, execute, or statically analyse code as a deliverable.

### 3.2 Input taxonomy (matrix rows)

Row vocabulary is Bašić & Giaretta v4: vulnerabilities **as identified in 21 studies**, grouped into ten categories mapped to CWE. Fixed **category profiles** state each category’s assessment focus and CWE inventory. Bašić v4 maps to CWE, not OWASP Top 10; any OWASP labels we use are provisional and do not alone ground a `fully_covered` cell.

### 3.3 Obligation extraction (matrix columns)

Column vocabulary follows a GuideMe-adapted protocol: quote from a retrieved primary source, decompose into atomic observables, derive criterion, assessment question, and required evidence. Every row carries separate **Act** and **Rules** commencement fields; `effective_from` is derived only after both applicable mechanisms are read from G.S.R. 843(E) and Rules r.1.

**MVP register:** 18 rows (`register-v0.3-mvp-2026-08-27`); 17 in the Gap-1 matrix (HDMP cl.16.4 excluded as org-policy / underspecified for code-pattern mapping).

### 3.4 Extended taxonomy

Obligation-level dimensions include consent architecture, purpose binding, withdrawal propagation, breach notification, retention/erasure, localisation, **access logging demonstrability**, ABHA/Health ID handling, consent-manager mediation, and FHIR conformance. Nickerson ending conditions are tracked in `taxonomy/nickerson-ending-conditions.md`.

### 3.5 Cross-mapping rule

Each cell answers: *Given the remediated-under-category module (RCM)—a patient-data module assessed under one Bašić category and remediated to that category’s ordinary CWE-shaped bar—how much of this obligation criterion does that remediation guarantee?*

Verdicts are ordinal: `fully_covered` > `partially_covered` > `not_visible`, with partial sub-flags. The rule was frozen as **v0.3-frozen** after a pre-freeze pilot; main matrix dual coding followed. Emptiness is an **outcome**, not a success criterion. Primary reliability statistic for the agent pass: **linearly weighted** Cohen’s κ. Primary human trust signal: raw agreement on a structured sample.

### 3.6 WASA handling

WASA is an **object of study**, not a register instrument: no public official specification was located. Adjacent expectations are re-sourced to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings.

### 3.7 Evaluation design

| Question | Method | Status |
|---|---|---|
| Coder agreement on matrix (agent) | Dual coding + weighted κ | Done (exploratory) |
| Human sample reliability | 50-cell blind dual coding | **Done** — 92% |
| Register coverage | Documentary coverage ratio | Locked MVP |
| Taxonomy quality | Nickerson conditions | Objective partial; subjective pending Delphi if required |
| Rubric usability | Bahmni HIP case study | **Done** — 88.9% |
| Expert acceptance | Two-round Delphi | Optional / if guide requires |

---

## 4. Artifact

The framework comprises five components (repository: `from-cwe-to-clause-artifact`).

### 4.1 Obligation register

GuideMe-adapted rows with verbatim quotes, atomic criteria, separate commencement columns, and dimension tags. Schema: `register/SCHEMA.md`. Page stamps: `register/page-stamps.md`. Pin unchanged at Phase 3 lock.

### 4.2 Extended taxonomy

Dimension A: ten Bašić categories. Dimension B: obligation-level dimensions. Cross-product outcomes recorded in the matrix (`taxonomy/extended-taxonomy.md`).

### 4.3 Cross-mapping matrix

170 cells (10×17); consensus in `mapping/main-matrix-reconciled.csv` after human sample patch; dual originals retained. Human sample worksheets and adjudication: `mapping/human-sample-results.md`.

### 4.4 Assessment rubric

Criterion-level scores: Pass / Partial / Fail / Not assessable. Matrix informs hints; Gap 1 rows require explicit logging review regardless of category assessment (`rubric/assessment-rubric.md`). Developer usage: `rubric/user-guide.md`.

### 4.5 Validation package

Validation report v0.3 records human sample IRR, Bahmni case study, and optional Delphi status (`validation/validation-report.md`).

---

## 5. Results

### 5.1 Matrix coverage

| Consensus verdict | *n* | % of 170 |
|---|---|---|
| `not_visible` | **158** | 92.9% |
| `partially_covered` | **12** | 7.1% |
| `fully_covered` | **0** | 0% |

Counts reflect the **human sample patch (2026-11-14)**. An earlier agent dual-coding pass reported 156 N / 13 P / 1 F; human adjudication moved CAT-07 × R-006-01 from `fully_covered` to `partially_covered` and CAT-08/09 × A-008-05 from partial to `not_visible`.

Interpretation: most MVP regulatory observables are **not guaranteed** by remediating any single Bašić category. Emptiness supports Gap 1; it is not a failure of the instrument.

**Non-uniform columns (current):**

| Obligation | Pattern |
|---|---|
| A-006-01 (purpose-specific consent) | CAT-05 partial only |
| A-006-06 (cessation on withdrawal) | CAT-06 partial only |
| A-008-05 (reasonable safeguards) | Mixed Pp/Pd; CAT-08/09 → N |
| R-006-01 (encryption/masking/tokens) | CAT-05 and CAT-07 **partial** (not full) |

Closest technical overlap remains **CAT-07 × R-006-01**, still only partial: sound cryptography when used does not entail encryption/masking/tokenization of all personal data.

### 5.2 Human sample reliability (Phase 1)

Two human coders (Surya, Rahul) independently scored a **50-cell sample** (all 10 categories × five obligations: R-006-02, HDMP-27-05a, A-008-05, R-006-01, A-006-04) under the frozen rule, without consulting the reconciled CSV.

| Metric | Result |
|---|---|
| Raw agreement | **46/50 (92%)** |
| Disagreements adjudicated | 4 |
| Gap 1 (logging columns) | **20/20 `not_visible`** |

This human–human sample is the primary trust signal for matrix judgements. Agent κ is retained only as exploratory context.

### 5.3 Gap 1 — access logging

**Evidenced absence in Bašić v4 (PDF-verified):** CWE-778, 779, 223, 532, 1295 absent as logging weaknesses; word “logging” absent as a topic; only log-adjacent CWE is **CWE-117** (output neutralization *for* logs) under Error Handling.

**Indian obligations:**

| Obligation | Source |
|---|---|
| Visibility of access via logs, monitoring, review | DPDP Rules **r.6(1)(c)** |
| Strict audit trail of processing with access to personal data | ABDM HDMP **cl.27.5(a)** |

**Matrix consensus:**

| Column | Pattern |
|---|---|
| R-006-02 | 10/10 `not_visible` |
| HDMP-27-05a | 10/10 `not_visible` |

A module fully remediated under every Bašić category—including CAT-10 CWE-117—can still provide **no** evidence that access/audit logging exists. CWE-117 presupposes logs exist; it does not assess log existence.

### 5.4 Case study — Bahmni India Distro HIP (Phase 2)

**System:** public MIT repositories `BahmniIndiaDistro/openmrs-module-hip` and `hip-service` (ABDM Health Information Provider integration).  
**Method:** dual rubric scoring (Pass / Partial / Fail / NA) on 10 indexed source files; matrix used as hints only.  
**Scorers:** Surya, Rahul · pre-adjudication agreement **16/18 (88.9%)**.

| Consensus highlights | Score |
|---|---|
| R-006-02 access logs | **Fail** |
| HDMP-27-05a audit trail | **Partial** |
| R-006-01 encryption/masking/tokens | **Partial** |
| A-006-01 purpose-scoped consent | **Pass** |
| A-006-06 cease-on-revoke | **Pass** |
| HDMP-15-04 Health ID linkage | **Pass** |
| Breach intimation / erasure | **Fail** |
| Notice UI / withdrawal UX | **NA** (outside HIP backend) |

**Overall mix:** 3 Pass · 4 Partial · 5 Fail · 6 NA.

On real ABDM-adjacent healthcare code, CWE-oriented reading of exception handlers can focus on log injection or error leakage while **missing** statutory access-monitoring log existence—matching the matrix Gap 1 prediction. Duties that are matrix-`not_visible` (consent scoping, revoke-stop, Health ID) still appear when the **register + rubric** path is applied. Full report: `validation/case-study-report.md`.

### 5.5 WASA regulatory transparency

We found **no publicly available official NHA/ABDM specification** for WASA in citable clause form. Vendor and auditor pages describe milestones, OWASP scope, and certification mechanics, but an instrument keyed to WASA would fail traceability. We re-source adjacent themes to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings, and treat WASA as object of study—not a register source.

### 5.6 Inter-rater summary

| Layer | Result |
|---|---|
| Agent matrix κ (exploratory) | 0.949 (*n* = 158) |
| Human matrix sample | 92% raw agree (50 cells) |
| Human case-study rubric | 88.9% raw agree (18 obligations) |

### 5.7 Coverage (MVP)

Eighteen register rows across four instrument types; partial DPDP/ABDM coverage by design—not exhaustive codification of either statute. See `validation/coverage-ratio.md`.

---

## 6. Threats to validity

**Construct:** Shared intuitions (e.g. “CWE-117 means logging is covered”) can yield high agreement with wrong partial verdicts. Defence: category CWE inventories and the closed-list capability note for logging; human sample tested CAT-10 × logging.

**Scope:** Pattern presence ≠ legal compliance. The Bahmni case scores a HIP code slice, not organisational compliance. HDMP cl.16.4 flagged `criterion_underspecified` for code-pattern assessment.

**Statistical:** Prevalence of `not_visible` (158/170) inflates κ; report sample agreement and disagreement counts alongside exploratory κ.

**Source:** Bašić OWASP alignments provisional; WASA absent; FHIR row partial page-stamp on exact `meta.profile` wording.

**Process:** Agent-assisted dual coding and reconciliation; human sample and case study completed; mentor sign-off pending.

---

## 7. Conclusion

We mapped Bašić’s ten CWE-shaped categories against MVP DPDP/ABDM obligations using a frozen counterfactual-visibility rule. After human sample adjudication the matrix is overwhelmingly `not_visible` (158/170), with logging duties uniformly invisible across categories (20/20)—the strongest structural finding—and zero fully covered cells. The Bahmni HIP case study confirms Gap 1 on real ABDM-adjacent code (access logs Fail; audit trail Partial). We supply obligation dimensions, a documentary rubric and developer guide, and validation evidence; Delphi remains optional unless the guide requires it.

**Practical implication:** CWE-only or OWASP-only review of AI-generated health modules is insufficient for Indian access-logging and consent-architecture duties—obligation-specific assessment is required.

**Future work:** mentor sign-off and institutional formatting; optional full-matrix human dual coding or Delphi if required; register expansion beyond MVP; tooling/MCP as a separate future project (out of scope here).

---

## References

See `paper/references.md` and source manifest `sources.md`. Pin Bašić **v4** and gazette PDFs when citing clause numbers.

---

## Appendix A — Repository map (abbreviated)

| Component | Path |
|---|---|
| Register | `register/obligation-register.md` |
| Category profiles | `taxonomy/category-profiles.md` |
| Cell-coding rule | `mapping/cell-coding-rule.md` |
| Matrix (consensus) | `mapping/main-matrix-reconciled.csv` |
| Human sample | `mapping/human-sample-results.md` |
| Rubric | `rubric/assessment-rubric.md` |
| Rubric user guide | `rubric/user-guide.md` |
| Case study | `validation/case-study-report.md` |
| Validation | `validation/validation-report.md` |
| Team checklist | `validation/human-next-steps.md` |
| Decision log | `logs/decision-log.md` |

Public artifact (no third-party PDFs): https://github.com/suryaraj05/from-cwe-to-clause-artifact

---

*Section files `00-abstract.md` … `07-conclusion.md` remain the editable split; this file is the integrated read-through draft.*
