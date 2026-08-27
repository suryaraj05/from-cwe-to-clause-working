# From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM

**Document:** `draft-manuscript.md`  
**Version:** `manuscript-v0.1-2026-08-27`  
**Status:** agent-integrated draft — **not submission-final**

**Validation pending:** human second coder; mentor reconciliation sign-off; Delphi; case study (see `validation/human-next-steps.md`).

**Artifact pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27` · matrix consensus `main-matrix-reconciled.csv`

**Constraint:** This project produces documents only. No application code, scripts as deliverables, static analysis runs, or code generation experiments.

---

## Abstract

Healthcare teams in India increasingly use AI coding assistants, yet security research consolidates LLM-generated vulnerabilities into CWE-shaped categories without Indian regulatory vocabulary. We design and evaluate a documentary assessment framework that maps Bašić and Giaretta’s ten vulnerability categories (arXiv:2412.15004v4; 21 studies) against atomic obligations derived from the Digital Personal Data Protection Act 2023, DPDP Rules 2025, and ABDM health-data instruments. Following GuideMe-style obligation extraction and a frozen counterfactual-visibility coding rule, we dual-code a 10×17 cross-mapping matrix (170 cells). Inter-rater agreement is high (linearly weighted κ = 0.949 on 158 non-pilot cells), but agreement is dominated by shared `not_visible` outcomes: 156 of 170 reconciled cells show that remediated-under-category assessment does not guarantee the regulatory criterion. The clearest structural gap is access-logging demonstrability—DPDP Rules r.6(1)(c) and ABDM HDMP cl.27.5(a) require visibility of personal-data access, yet no Bašić category assesses log existence (20/20 matrix cells `not_visible`). We extend the taxonomy with obligation-level dimensions, provide an assessment rubric for documentary evidence, and report the absence of a public WASA specification as a regulatory-transparency finding. Pattern assessment is necessary but not sufficient for legal compliance.

**Keywords:** DPDP Act 2023; ABDM; LLM-generated code; CWE; regulatory compliance; design science; cross-mapping.

---

## 1. Introduction

### 1.1 Motivation

Indian healthtech teams adopt AI coding assistants to build patient-data modules faster. Empirical work shows AI-generated code often contains vulnerabilities; Bašić and Giaretta synthesise findings from **21 studies** into ten CWE-mapped categories for remediation-oriented review. That vocabulary is jurisdiction-agnostic. Meanwhile, the Digital Personal Data Protection Act 2023 and the ABDM health-data policy stack impose obligations—purpose-bound consent, access logging, audit trails, breach intimation—that are not expressible as CWE weaknesses alone.

No published instrument tells a team whether an AI-generated module **exhibits patterns consistent with those Indian obligations** when assessed only through ordinary CWE-shaped categories.

### 1.2 Research question

Given Bašić’s ten-category taxonomy and atomic criteria derived from DPDP and ABDM primary sources, **which regulatory observables are visible—or not—when a patient-data module is assessed and remediated under each category’s ordinary technical standard?**

### 1.3 Contribution

Following design science (Hevner et al., 2004), we deliver five documentary artefacts: (1) obligation register, (2) extended taxonomy, (3) cross-mapping matrix with dual coding, (4) assessment rubric, (5) validation report. Evaluation combines inter-rater reliability, coverage transparency, Nickerson ending conditions, a planned expert Delphi, and a planned documentary case study.

### 1.4 Scope

We assess **compliant patterns** in described or supplied evidence. That is necessary but not sufficient for legal compliance, which also depends on organisational process invisible in code. We do not build or run software.

### 1.5 Findings preview

- **Gap 1 (logging):** no Bašić category assesses access/audit log existence; Indian rules require it—uniform `not_visible` across the matrix logging columns (20/20 cells).
- **Sparse matrix overall:** 91.8% of reconciled cells are `not_visible` (156/170).
- **WASA transparency:** no public official WASA specification located—reported as its own finding (Section 5.3).
- **κ caution:** high agreement reflects shared emptiness, not automatic correctness (Section 6).

---

## 2. Background and related work

### 2.1 AI-generated code security

Systematic reviews and empirical studies document insecure patterns in LLM-assisted development (Pearce et al.; Perry et al.; SafeGenBench). Bašić and Giaretta (arXiv:2412.15004**v4**) consolidate **21 studies** into ten vulnerability categories mapped to CWE—our matrix row vocabulary. Recent work on “vibe-coded” applications highlights AI-specific failure modes. These lines of research are **jurisdiction-agnostic** and do not encode Indian statutory consent, logging, or ABDM interchange duties.

### 2.2 Regulation-to-controls methods

Ayala-Rivera and Pasquale’s GuideMe operationalises GDPR through privacy controls—a methodological precedent for obligation extraction. No equivalent catalogue targets DPDP, ABHA/HIE-CM flows, or NRCeS FHIR profiles for **assessing code already written** by AI tools.

### 2.3 Taxonomy and design science

Nickerson et al. provide ending conditions for IS taxonomies; we extend Bašić categories with obligation-level dimensions and document cross-product outcomes. Hevner et al. frame our contribution as artefact plus rigorous evaluation. Our evaluation is documentary—dual coding, coverage ratio, Delphi, case study—not implementation.

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

We follow design science: a designed framework plus rigorous evaluation. Evaluation is documentary (register coverage, dual coding, linearly weighted kappa, Delphi, case-study application to an existing hospital audit report). We do not generate, execute, or statically analyse code.

### 3.2 Input taxonomy (matrix rows)

Row vocabulary is Bašić & Giaretta v4: vulnerabilities **as identified in 21 studies**, grouped into ten categories mapped to CWE (Section 4 / Table 3). Fixed **category profiles** state each category’s assessment focus and CWE inventory. Bašić v4 maps to CWE, not OWASP Top 10; any OWASP labels we use are provisional and do not alone ground a `fully_covered` cell.

### 3.3 Obligation extraction (matrix columns)

Column vocabulary follows a GuideMe-adapted protocol: quote from a retrieved primary source, decompose into atomic observables, derive criterion, assessment question, and required evidence. Every row carries separate **Act** and **Rules** commencement fields; `effective_from` is derived only after both applicable mechanisms are read from G.S.R. 843(E) and Rules r.1.

**MVP register:** 18 rows (`register-v0.3-mvp-2026-08-27`); 17 in the Gap-1 matrix (HDMP cl.16.4 excluded as org-policy / underspecified for code-pattern mapping).

### 3.4 Extended taxonomy

Obligation-level dimensions include consent architecture, purpose binding, withdrawal propagation, breach notification, retention/erasure, localisation, **access logging demonstrability**, ABHA/Health ID handling, consent-manager mediation, and FHIR conformance. Nickerson ending conditions are tracked in `taxonomy/nickerson-ending-conditions.md`.

### 3.5 Cross-mapping rule

Each cell answers: *Given the remediated-under-category module (RCM)—a patient-data module assessed under one Bašić category and remediated to that category’s ordinary CWE-shaped bar—how much of this obligation criterion does that remediation guarantee?*

Verdicts are ordinal: `fully_covered` > `partially_covered` > `not_visible`, with partial sub-flags. The rule was frozen as **v0.3-frozen** after a pre-freeze pilot; main matrix dual coding followed. Emptiness is an **outcome**, not a success criterion. Primary reliability statistic: **linearly weighted** Cohen’s κ.

### 3.6 WASA handling

WASA is an **object of study**, not a register instrument: no public official specification was located. Adjacent expectations are re-sourced to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings.

### 3.7 Evaluation design

| Question | Method | Status |
|---|---|---|
| Coder agreement on matrix | Dual coding + weighted κ | Done (exploratory; agent-assisted) |
| Register coverage | Documentary coverage ratio | MVP draft |
| Taxonomy quality | Nickerson conditions | Objective partial; subjective pending Delphi |
| Rubric usability | Case study on audit report | Protocol only |
| Expert acceptance | Two-round Delphi | Protocol only |

---

## 4. Artifact

The framework comprises five components (repository: `from-cwe-to-clause-artifact`).

### 4.1 Obligation register

GuideMe-adapted rows with verbatim quotes, atomic criteria, separate commencement columns, and dimension tags. Schema: `register/SCHEMA.md`. Page stamps: `register/page-stamps.md`.

### 4.2 Extended taxonomy

Dimension A: ten Bašić categories. Dimension B: obligation-level dimensions. Cross-product outcomes recorded in the matrix (`taxonomy/extended-taxonomy.md`).

### 4.3 Cross-mapping matrix

170 cells (10×17); consensus in `mapping/main-matrix-reconciled.csv`; dual originals retained. Five cells reconciled after disagreement (`mapping/reconciliation-record.md`).

### 4.4 Assessment rubric

Criterion-level scores: Pass / Partial / Fail / Not assessable via CWE taxonomy. Matrix informs hints; Gap 1 rows require explicit logging review regardless of category assessment (`rubric/assessment-rubric.md`).

### 4.5 Validation package

Partial validation report (matrix track); Delphi and case-study protocols prepared; human validation pending (`validation/validation-report.md`).

---

## 5. Results

### 5.1 Matrix coverage

| Consensus verdict | *n* | % of 170 |
|---|---|---|
| `not_visible` | 156 | 91.8% |
| `partially_covered` | 13 | 7.6% |
| `fully_covered` | 1 | 0.6% |

All thirteen partial cells are `partial_positive`. Interpretation: most MVP regulatory observables are **not guaranteed** by any single Bašić category RCM.

**Non-uniform columns:**

| Obligation | Pattern |
|---|---|
| A-006-01 (purpose-specific consent) | CAT-05 partial only |
| A-006-06 (cessation on withdrawal) | CAT-06 partial only |
| A-008-05 (reasonable safeguards) | all ten categories partial |
| R-006-01 (encryption/masking/tokens) | CAT-07 full; CAT-05 partial |

Sole `fully_covered` cell: **CAT-07 (Cryptography) × R-006-01**—crypto RCM entails sound encryption, satisfying Rules r.6(1)(a) encryption path.

### 5.2 Gap 1 — access logging (primary worked example)

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

No dual-coding or reconciliation dispute. A module fully remediated under every Bašić category—including CAT-10 CWE-117—can still provide **no** evidence that access/audit logging exists or is sufficient. CWE-117 presupposes logs exist; it does not assess log existence.

**Implication:** `access_logging_demonstrability` is an obligation-level dimension with **no home** in the input taxonomy—the cleanest Gap 1 instance.

### 5.3 WASA regulatory transparency

We found **no publicly available official NHA/ABDM specification** for WASA (Web Application Security Assessment) in citable clause form. Vendor and auditor pages describe milestones, OWASP scope, and certification mechanics, but an instrument keyed to WASA would fail traceability. We re-source adjacent themes to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings, and treat WASA as object of study—not a register source.

### 5.4 Inter-rater reliability

| Metric | Value |
|---|---|
| Linearly weighted κ (non-pilot, *n* = 158) | 0.949 |
| Non-pilot disagreements (pre-reconciliation) | 1 |
| Cells reconciled | 5 |

κ measures agreement, not correctness. Coder B was an independent agent pass; human replication is required before publication-grade IRR claims.

### 5.5 Coverage (MVP)

Eighteen register rows across four instrument types; partial DPDP/ABDM coverage by design—not exhaustive codification of either statute. See `validation/coverage-ratio.md`.

---

## 6. Threats to validity

**Construct:** Shared intuitions (e.g. “CWE-117 means logging is covered”) can yield high κ with wrong partial verdicts. Defence: category CWE inventories and the closed-list capability note for logging.

**Scope:** Pattern presence ≠ legal compliance. HDMP cl.16.4 flagged `criterion_underspecified` for code-pattern assessment.

**Statistical:** Prevalence of `not_visible` (156/170) inflates κ; report disagreement counts alongside κ.

**Source:** Bašić OWASP alignments provisional; WASA absent; FHIR row partial page-stamp on exact `meta.profile` wording.

**Process:** Agent-assisted dual coding and reconciliation; mentor sign-off pending.

---

## 7. Conclusion

We mapped Bašić’s ten CWE-shaped categories against MVP DPDP/ABDM obligations using a frozen counterfactual-visibility rule. The matrix is overwhelmingly `not_visible` (156/170), with logging duties uniformly invisible across categories (20/20)—the strongest structural finding. We supply obligation dimensions, a documentary rubric, and validation protocols; Delphi and case study remain for the research team.

**Practical implication:** CWE-only or OWASP-only review of AI-generated health modules is insufficient for Indian access-logging and consent-architecture duties—obligation-specific assessment is required.

**Future work:** human second coder; mentor reconciliation review; expert Delphi; case study on existing audit report; register expansion beyond MVP.

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
| Rubric | `rubric/assessment-rubric.md` |
| Validation | `validation/validation-report.md` |
| Team checklist | `validation/human-next-steps.md` |
| Decision log | `logs/decision-log.md` |

Public artifact (no third-party PDFs): https://github.com/suryaraj05/from-cwe-to-clause-artifact

---

*Section files `00-abstract.md` … `07-conclusion.md` remain the editable split; this file is the integrated read-through draft.*
