# Introduction

**Status:** draft — team rewrite.

## Motivation

Indian healthtech teams adopt AI coding assistants to build patient-data modules faster. Empirical work shows AI-generated code often contains vulnerabilities; Bašić and Giaretta synthesise findings from **21 studies** into ten CWE-mapped categories for remediation-oriented review. That vocabulary is jurisdiction-agnostic. Meanwhile, the Digital Personal Data Protection Act 2023 and the ABDM health-data policy stack impose obligations—purpose-bound consent, access logging, audit trails, breach intimation—that are not expressible as CWE weaknesses alone.

No published instrument tells a team whether an AI-generated module **exhibits patterns consistent with those Indian obligations** when assessed only through ordinary CWE-shaped categories.

## Research question

Given Bašić’s ten-category taxonomy and atomic criteria derived from DPDP and ABDM primary sources, **which regulatory observables are visible—or not—when a patient-data module is assessed and remediated under each category’s ordinary technical standard?**

## Contribution (design science)

We deliver five documentary artefacts: (1) obligation register, (2) extended taxonomy, (3) cross-mapping matrix with dual coding, (4) assessment rubric, (5) validation report. Evaluation combines inter-rater reliability, coverage transparency, Nickerson ending conditions, a planned expert Delphi, and a planned documentary case study.

## Scope honesty

We assess **compliant patterns** in described or supplied evidence. That is necessary but not sufficient for legal compliance, which also depends on organisational process invisible in code.

## Findings preview

- **Gap 1 (logging):** no Bašić category assesses access/audit log existence; Indian rules require it—uniform `not_visible` across the matrix logging columns.  
- **Sparse matrix overall:** 91.8% of reconciled cells are `not_visible`.  
- **WASA transparency:** no public official WASA specification located—reported as its own finding.  
- **κ caution:** high agreement reflects shared emptiness, not automatic correctness.

## Paper structure

Section 2 reviews related work; Section 3 method; Section 4 artefacts; Section 5 results; Section 6 threats; Section 7 conclusion.

## Positioning

We do not build or run software. All work is documentary: registers, matrices, rubrics, and validation protocols grounded in retrieved primary sources.
