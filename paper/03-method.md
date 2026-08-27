# Method

## Research paradigm

We follow design science in information systems (Hevner et al., 2004): the contribution is a designed artifact plus rigorous evaluation. The artifact is a regulatory compliance assessment framework for AI-generated healthcare code under India’s DPDP Act 2023 and ABDM-related public instruments. Evaluation is documentary (register coverage, dual coding, linearly weighted kappa, Delphi, case-study application to an existing hospital audit report). We do not generate, execute, or statically analyse code as part of this project.

## Scope claim (stated early)

The framework assesses whether a patient-data module **exhibits compliant patterns** relative to derived criteria. That is necessary but not sufficient for legal compliance, which also depends on organisational processes invisible in code. We state this limit in every use of the rubric.

## Input taxonomy

Row vocabulary is taken from Bašić & Giaretta (arXiv:2412.15004**v4**), who synthesise vulnerabilities in LLM-generated code **as identified in 21 studies** into ten categories mapped to CWE (Section 4 / Table 3). We maintain fixed **category profiles** (`taxonomy/category-profiles.md`) stating each category’s assessment focus and CWE inventory. Bašić v4 does not systematically map categories to OWASP Top 10; any OWASP labels we use are marked provisional and do not alone ground a `fully_covered` cell.

## Obligation extraction

Column vocabulary is built with a GuideMe-adapted coding protocol (Ayala-Rivera & Pasquale, 2018): quote from a retrieved primary source, decompose into atomic observables, derive a criterion, assessment question, and required evidence. Every row carries separate **Act** and **Rules** commencement fields (G.S.R. 843(E) vs Rules r.1), with `effective_from` derived only after both applicable mechanisms are read. Unverified cells are never left blank; they carry an explicit pending string until filled.

## Extended dimensions

Nickerson et al.’s taxonomy method structures how we add obligation-level dimensions (consent architecture, purpose binding, withdrawal propagation, breach notification, retention/erasure, localisation, **access logging / demonstrability**, ABHA/Health ID handling, consent-manager mediation, FHIR conformance) beyond CWE-shaped categories. Ending conditions are checked explicitly before claiming the taxonomy is finished.

## Cross-mapping

Cells answer a counterfactual-visibility question about a **remediated-under-category module (RCM)**. Verdicts are ordinal with partial sub-flags. Primary reliability is **linearly weighted** Cohen’s kappa. Emptiness is an outcome, not a success criterion.

**Worked Gap 1 example:** Bašić v4 (21 studies) has no category assessing access/audit logging existence; DPDP r.6(1)(c) and HDMP cl.27.5(a) require it → dimension `access_logging_demonstrability` (`paper/findings-logging-gap1.md`). Kappa measures agreement, not correctness (`paper/06-threats-to-validity.md`).

## WASA

WASA is an **object of study**, not a register instrument: no public official specification was located. Adjacent obligations are re-sourced to OWASP Top 10, ABDM Health Data Management Policy, and CERT-In empanelment listings. The absence is reported in a dedicated transparency subsection.

Coverage ratio of register vs source instruments; dual coding + weighted kappa; two-round expert Delphi; documentary case study on an existing hospital audit report. Threats to validity are drafted early and updated as coding proceeds.

## Method → artifact correspondence

| Cited method | Our visible output |
|---|---|
| GuideMe | `register/coding-protocol.md`, obligation register |
| Nickerson et al. | extended taxonomy + ending-condition checklist |
| Hevner et al. | artifact set + `validation/` |
| Bašić & Giaretta v4 | category profiles + matrix rows |
| Cell-coding rule | `mapping/cell-coding-rule.md` (frozen v0.3; main matrix dual-coded + reconciled) |
