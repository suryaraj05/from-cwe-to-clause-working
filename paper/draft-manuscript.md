# From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM

**Document:** `draft-manuscript.md`  
**Version:** `manuscript-v0.3-2026-11-14`  
**Status:** Citation-polished & internally consistent — ready for mentor sign-off and institutional cover page  

**Artifact pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27` · matrix consensus `main-matrix-reconciled.csv` (post human sample)  

**Scope constraint:** This project produces documentary design-science artefacts only. No application code, executable scripts as deliverables, static analysis runs, or code-generation experiments are included.

---

## Abstract

Healthcare software teams in India increasingly rely on AI coding assistants, yet empirical security literature consolidates LLM-generated vulnerabilities into Common Weakness Enumeration (CWE)-shaped categories devoid of Indian regulatory semantics. We design and evaluate a documentary assessment framework that maps Bašić and Giaretta’s ten vulnerability categories (arXiv:2412.15004v4; 21 studies) [1] against atomic legal-technical obligations derived from India's Digital Personal Data Protection (DPDP) Act 2023 [10], DPDP Rules 2025 [11], and Ayushman Bharat Digital Mission (ABDM) health-data instruments [14, 15]. Following a GuideMe-adapted obligation extraction protocol [2] and a frozen counterfactual-visibility coding rule (`v0.3-frozen`), we construct a $10 \times 17$ cross-mapping matrix (170 cells). Following dual human sample adjudication, **158 of 170 cells (92.9%)** are `not_visible`, demonstrating that remediating a module under standard vulnerability categories does not guarantee compliance with most statutory criteria. Two independent human coders achieved **92.0% raw agreement** (46/50 cells; linearly weighted $\kappa = 0.746$) on a structured sample, with unanimous `not_visible` consensus (20/20) across access-logging and audit-trail obligations (Gap 1). An exploratory agent dual-coding pass yielded $\kappa = 0.949$ ($n = 158$) but is reported strictly as secondary context. Applying the documentary assessment rubric to open-source **Bahmni India Distro HIP** repositories (`openmrs-module-hip` and `hip-service`; dual human scorers, **88.9%** agreement) confirmed Gap 1 on real ABDM-adjacent software: statutory access-monitoring logs scored **Fail** and audit trails scored **Partial**. We extend the vulnerability taxonomy with obligation-level dimensions, provide a practitioner rubric and developer user guide, and document the absence of a public official Web Application Security Assessment (WASA) specification as a regulatory-transparency finding. Pattern assessment is necessary but not sufficient for legal compliance.

**Keywords:** DPDP Act 2023; ABDM; LLM-generated code; CWE; regulatory compliance; design science; cross-mapping.

---

## 1. Introduction

### 1.1 Motivation

Indian healthcare technology teams increasingly adopt AI coding assistants to accelerate the development of patient-data modules. Empirical security research shows that LLM-generated code frequently introduces software weaknesses [3, 4, 5]; Bašić and Giaretta synthesise findings across **21 studies** into ten CWE-mapped vulnerability categories for remediation-oriented code review [1]. However, that technical vocabulary is jurisdiction-agnostic. Simultaneously, India's Digital Personal Data Protection (DPDP) Act 2023 [10], DPDP Rules 2025 [11], and ABDM health-data governance framework [14, 15] impose concrete architectural duties—purpose-bound consent, comparable-ease withdrawal, access logging, immutable audit trails, breach intimation, and FHIR profile conformance—that cannot be expressed purely as CWE weaknesses.

No existing assessment instrument informs engineering teams whether an AI-generated healthcare module **exhibits architectural patterns consistent with Indian statutory obligations** when evaluated solely through standard CWE-shaped vulnerability categories.

### 1.2 Research Question

Given Bašić and Giaretta’s ten-category vulnerability taxonomy [1] and atomic criteria derived from DPDP and ABDM primary regulatory sources [10, 11, 14, 15], **which regulatory observables are visible—or not—when a patient-data module is assessed and remediated under each category’s ordinary technical standard?**

### 1.3 Contributions

Following the Design Science Research (DSR) paradigm of Hevner et al. [7], we contribute five linked documentary artefacts:
1. **Obligation Register:** Atomic regulatory criteria extracted from Indian primary legal and technical instruments (`register-v0.3-mvp-2026-08-27`) [10, 11, 13, 14, 15].
2. **Extended Taxonomy:** Bašić and Giaretta’s ten vulnerability categories augmented with ten obligation-level compliance dimensions [1, 8].
3. **Cross-Mapping Matrix:** A 170-cell ($10 \times 17$) counterfactual-visibility matrix validated via dual human sample coding (`main-matrix-reconciled.csv`).
4. **Assessment Rubric & User Guide:** A four-level documentary evaluation rubric (`Pass` / `Partial` / `Fail` / `Not Assessable`) paired with a practitioner walkthrough (`rubric/user-guide.md`).
5. **Validation Package:** Multi-layered documentary evaluation combining exploratory dual coding, human sample inter-rater reliability (IRR), register coverage transparency, Nickerson ending conditions [8], an optional expert Delphi protocol, and a real-world healthcare case study on Bahmni India Distro HIP.

### 1.4 Scope and Boundary Conditions

Our framework evaluates **compliant architectural and code-level patterns** evidenced in supplied documentation or source files. Pattern presence is **necessary but not sufficient** for legal compliance, which additionally relies on organizational governance, clinical operations, and runtime infrastructure invisible in source code. Consistent with project constraints, all deliverables are documentary artefacts; no software tools, automated scanners, or code-generation experiments were built or executed.

### 1.5 Summary of Key Findings

- **Gap 1 (Access Logging & Audit Trails):** No Bašić category verifies the existence or sufficiency of access logs or processing audit trails, whereas Indian healthcare regulations mandate both [11, 14]. All 20 matrix cells in the logging columns are unanimously `not_visible`, and the Bahmni HIP case study scored **Fail** on access logs and **Partial** on audit trails.
- **High Matrix Sparsity:** After human adjudication, **92.9% (158/170)** of reconciled matrix cells are `not_visible`, **7.1% (12/170)** are `partially_covered`, and **0% (0/170)** are `fully_covered`.
- **Human Inter-Rater Reliability:** Two independent human raters achieved **92.0%** raw agreement ($\kappa = 0.746$) on a 50-cell matrix sample and **88.9%** agreement (16/18 obligations) on the Bahmni HIP case study.
- **WASA Regulatory Transparency:** No publicly available official NHA/ABDM technical specification for WASA was located in citable clause form (Section 5.5).
- **Statistical Caution on $\kappa$:** Exploratory agent $\kappa$ (0.949) is inflated by `not_visible` prevalence; human agreement counts and boundary adjudications serve as our primary reliability evidence (Section 6).

---

## 2. Background and Related Work

### 2.1 Security of AI-Generated Code

Empirical studies and benchmarks consistently demonstrate that AI coding assistants generate code susceptible to injection, insecure cryptography, improper access control, and memory errors [3, 4, 5, 6]. Bašić and Giaretta (arXiv:2412.15004**v4**) consolidate findings from **21 primary studies** into ten CWE-mapped remediation categories [1]. Recent studies on "vibe-coded" applications further highlight structural security omissions when developers rely heavily on conversational generation [6]. However, this entire body of research remains **jurisdiction-agnostic** and does not capture statutory consent workflows, data-principal rights, or health-information exchange standards.

### 2.2 Regulation-to-Controls Extraction Methods

Ayala-Rivera and Pasquale’s *GuideMe* framework operationalises the European Union's GDPR into structured software privacy controls through systematic obligation extraction [2]. While *GuideMe* establishes a rigorous methodological precedent for translating statutory prose into engineering requirements, no equivalent catalogue targets India’s DPDP Act/Rules [10, 11], ABDM Health Data Management Policy (HDMP) [14], or NRCeS FHIR Implementation Guide profiles [15] for assessing AI-generated healthcare code.

### 2.3 Taxonomy Engineering and Design Science

Nickerson et al. [8] (with updates by Kundisch et al. [9]) define formal ending conditions for taxonomy development in information systems. We adopt their framework to extend Bašić and Giaretta’s vulnerability categories with regulatory obligation dimensions. Guided by Hevner et al. [7], we frame our framework as a design-science artefact evaluated through documentary reliability, coverage analysis, and empirical case-study application.

### 2.4 Indian Healthcare Regulatory Landscape

Our obligation register anchors to five primary Indian instruments: (i) the Digital Personal Data Protection Act, 2023 (Act No. 22 of 2023) [10]; (ii) the DPDP Rules, 2025 (G.S.R. 846(E)) [11] and corrigendum G.S.R. 892(E) [12]; (iii) the commencement notification G.S.R. 843(E) [13], establishing staged enforcement dates (with most substantive obligations effective **2027-05-13** under the +18-month schedule); (iv) the ABDM Health Data Management Policy (HDMP) [14]; and (v) the NRCeS FHIR Implementation Guide for ABDM v6.5.0 (`ndhm.in#6.5.0`) [15].

### 2.5 Research Gaps

1. **Structural Gap:** Standard CWE vulnerability categories cannot express legal-architectural duties such as itemised privacy notices or comparable-ease consent withdrawal.
2. **Instrument Gap:** No open, clause-traceable DPDP/ABDM obligation register exists for auditing AI-generated healthcare modules.
3. **Jurisdictional Gap:** LLM security evaluations lack Indian healthcare grounding, leaving teams blind to jurisdiction-specific compliance omissions.

---

## 3. Method

### 3.1 Research Paradigm

We follow Hevner et al.’s Design Science Research methodology [7]: iterative construction of a structured regulatory-mapping artefact paired with multi-method documentary evaluation (coverage accounting, dual coding, human sample reliability, and case-study application).

### 3.2 Input Taxonomy (Matrix Rows)

Matrix rows comprise the ten vulnerability categories defined by Bašić and Giaretta v4 across 21 studies [1]: `CAT-01` Injection, `CAT-02` Memory Management, `CAT-03` File Management, `CAT-04` Deserialization, `CAT-05` Sensitive Data Exposure, `CAT-06` Authentication and Authorization, `CAT-07` Cryptography, `CAT-08` Resource Management, `CAT-09` Coding Standards, and `CAT-10` Error Handling. Pinned category profiles (`cat-profiles-v0.1-2026-08-27`) restrict each row’s vocabulary strictly to the CWEs documented in Bašić v4 §4 and Table 3 [1, 17]. Provisional OWASP Top 10 [16] alignments are annotated for context only and cannot independently justify a `fully_covered` verdict.

### 3.3 Obligation Extraction (Matrix Columns)

Using a *GuideMe*-adapted protocol [2], each obligation row is extracted verbatim from a retrieved primary PDF [10, 11, 13, 14, 15], decomposed into atomic technical observables, and formulated into a `derived_criterion`, `assessment_question`, and `evidence_required`. Act and Rules commencement mechanisms are tracked separately before deriving `effective_from` dates [11, 13].

The MVP register (`register-v0.3-mvp-2026-08-27`) contains **18 obligations**. Seventeen obligations enter the Gap-1 cross-mapping matrix; one organizational policy obligation (`OB-ABDM-HDMP-16-04`, non-denial of care without Health ID [14]) was flagged `criterion_underspecified` for code-pattern mapping during pilot testing and retained as an organizational-policy row.

### 3.4 Extended Taxonomy

We extend Bašić and Giaretta’s ten technical categories with ten obligation-level compliance dimensions: `consent_architecture`, `purpose_binding`, `withdrawal_propagation`, `breach_notification`, `retention_erasure`, `data_localization`, `access_logging_demonstrability`, `abha_identity`, `consent_manager_mediation`, and `fhir_conformance`. Objective and subjective taxonomy quality criteria are tracked against Nickerson et al.’s ending conditions [8].

### 3.5 Counterfactual Cross-Mapping Rule (`v0.3-frozen`)

Every matrix cell evaluates a defined counterfactual object—the **Remediated-under-Category Module (RCM)**: *a patient-data module assessed under one Bašić category and remediated to that category’s ordinary CWE-shaped standard.* Coders ask: *How much of the column’s obligation criterion does achieving the RCM necessarily guarantee?*

Verdicts follow an ordinal scale (`fully_covered` > `partially_covered` > `not_visible`), with `partially_covered` subdivided into `partial_positive` (`Pp`, explicit shared observable and missing legal element) and `partial_by_default` (`Pd`, tiebreak under imprecision). A closed list of imported legal terms prevents coders from projecting statutory concepts onto technical CWE definitions. Matrix sparsity is treated strictly as an empirical outcome rather than a target.

### 3.6 Handling of WASA

During source verification, no publicly accessible official NHA/ABDM specification defining citable technical clauses for Web Application Security Assessment (WASA) was located. Rather than inventing unverified register rows, WASA is treated as an object of regulatory-transparency study (Section 5.5), while adjacent security expectations are anchored to OWASP Top 10 [16], ABDM HDMP [14], and CERT-In empanelment guidelines [18].

### 3.7 Evaluation Design

| Evaluation Question | Method | Status |
|---|---|---|
| Matrix coder consistency (exploratory) | Dual coding + linearly weighted $\kappa$ | Complete (exploratory) |
| Human inter-rater reliability | 50-cell blind dual human coding | **Complete** — 92.0% ($\kappa = 0.746$) |
| Register scope transparency | Documentary coverage ratio | Locked MVP (18 rows / 17 matrix) |
| Taxonomy structural quality | Nickerson et al. ending conditions [8] | Objective met; subjective optional |
| Rubric practical applicability | Bahmni India Distro HIP case study | **Complete** — 88.9% agreement |
| External expert consensus | Two-round Delphi protocol | Designed; optional per mentor |

---

## 4. Artefact Overview

All five framework components are published in the public repository (`from-cwe-to-clause-artifact`):
1. **Obligation Register (`register/obligation-register.md`):** 18 page-stamped DPDP and ABDM criteria with commencement lookups (`register/page-stamps.md`, `register/commencement-lookup.md`).
2. **Extended Taxonomy (`taxonomy/extended-taxonomy.md`):** Cross-product specification linking CWE vulnerability categories (`taxonomy/category-profiles.md`) with Indian regulatory dimensions and Nickerson ending-condition tracking (`taxonomy/nickerson-ending-conditions.md`).
3. **Cross-Mapping Matrix (`mapping/main-matrix-reconciled.csv`):** 170 reconciled cells integrating exploratory dual passes and Phase 1 human adjudication (`mapping/human-sample-results.md`).
4. **Assessment Rubric & User Guide (`rubric/assessment-rubric.md`, `rubric/user-guide.md`):** Four-tier evidence rubric (`Pass`, `Partial`, `Fail`, `NA`) with mandatory Gap 1 logging checks and developer instructions.
5. **Validation Package (`validation/validation-report.md`):** Consolidated reliability statistics, coverage ratios (`validation/coverage-ratio.md`), Bahmni HIP case study (`validation/case-study-report.md`), and Delphi protocol (`validation/delphi/protocol.md`).

---

## 5. Results

### 5.1 Matrix Coverage Distribution

| Consensus Verdict | Cell Count (*n*) | Share of 170 Cells |
|---|---|---|
| `not_visible` | **158** | 92.9% |
| `partially_covered` | **12** | 7.1% |
| `fully_covered` | **0** | 0.0% |

These counts reflect the **human sample patch (2026-11-14)**. While an initial exploratory agent pass produced 156 `not_visible` / 13 `partially_covered` / 1 `fully_covered`, human adjudication reclassified `CAT-07 × R-006-01` from `fully_covered` to `partially_covered` (`Pp`) and `CAT-08` / `CAT-09 × A-008-05` from `partially_covered` to `not_visible`.

**Interpretation:** Remediating a healthcare module under any single Bašić CWE category does **not** guarantee full compliance with any MVP obligation in our register. Only four columns exhibit any non-`not_visible` overlap:

| Obligation ID | Description | Non-`not_visible` Pattern |
|---|---|---|
| `OB-DPDP-A-006-01` | Purpose-specific consent | `CAT-05` → `partially_covered` (`Pp`) |
| `OB-DPDP-A-006-06` | Cessation on withdrawal | `CAT-06` → `partially_covered` (`Pp`) |
| `OB-DPDP-A-008-05` | Reasonable security safeguards | `CAT-01, 03, 05, 06, 07` (`Pp`); `CAT-02, 04, 10` (`Pd`); `CAT-08, 09` (`N`) |
| `OB-DPDP-R-006-01` | Encryption / masking / tokens | `CAT-05` (`Pp`), `CAT-07` (`Pp`) — **not** `fully_covered` |

Notably, even the closest technical pairing (`CAT-07` Cryptography $\times$ `R-006-01` encryption/masking/tokens) achieves only `partially_covered` (`Pp`): verifying that cryptographic primitives are sound when invoked does not guarantee that all personal-data fields in a module are encrypted, masked, or tokenized at rest and in transit.

### 5.2 Human Sample Reliability (Phase 1)

Two human coders (Surya and Rahul) independently scored a **50-cell structured sample** (all 10 categories $\times$ 5 obligations: `R-006-02`, `HDMP-27-05a`, `A-008-05`, `R-006-01`, and `A-006-04`) under `cell-coding-rule` `v0.3-frozen` without viewing reconciled outputs.

| Metric | Result |
|---|---|
| Raw agreement | **46 / 50 (92.0%)** |
| Linearly weighted Cohen’s $\kappa$ | **0.746** (unweighted $\kappa = 0.742$) |
| Boundary disagreements adjudicated | 4 (`CAT-02/10 × A-008-05`, `CAT-07 × R-006-01`, `CAT-06 × A-006-04`) |
| Gap 1 logging columns | **20 / 20 `not_visible`** (unanimous; `CAT-10` CWE-117 trap avoided) |

This human dual-coding sample provides our primary empirical reliability evidence, superseding the exploratory agent pass ($\kappa = 0.949$, $n = 158$).

### 5.3 Gap 1 — Access Logging and Audit Trail Invisibility

Verification against the Bašić v4 PDF [1] confirms that CWE-778 (Insufficient Logging), CWE-779 (Logging of Excessive Data), CWE-223 (Omission of Security-relevant Information), CWE-532 (Insertion of Sensitive Information into Log File), and CWE-1295 (Debug Messages Revealing Unnecessary Information) are absent from the category inventories, and "logging" does not appear as a taxonomy topic. The sole log-related entry is **CWE-117** (*Improper Output Neutralization for Logs*) under `CAT-10` (Error Handling).

| Obligation | Legal Source | Matrix Consensus (All 10 Categories) |
|---|---|---|
| `OB-DPDP-R-006-02` | DPDP Rules r.6(1)(c) — access logs & monitoring [11] | **10 / 10 `not_visible`** |
| `OB-ABDM-HDMP-27-05a` | ABDM HDMP cl.27.5(a) — strict processing audit trail [14] | **10 / 10 `not_visible`** |

Because CWE-117 presupposes that logs already exist and checks only output sanitization, a patient-data module can pass every Bašić category—including `CAT-10`—while generating zero access logs or audit trails.

### 5.4 Case Study — Bahmni India Distro HIP (Phase 2)

To evaluate rubric applicability on real healthcare software, Surya and Rahul independently scored 10 core architectural files from the MIT-licensed **Bahmni India Distro ABDM Health Information Provider (HIP)** repositories (`BahmniIndiaDistro/openmrs-module-hip` and `hip-service`) across all 18 register obligations, using the reconciled matrix solely as review hints.

| Consensus Outcome | Count | Obligations & Key Code Evidence |
|---|---|---|
| **Pass (`P`)** | **3** | `A-006-01` (purpose/HI-type scoping in `HealthInformationController.java`), `A-006-06` (cease-on-revoke in `ConsentController.cs` + `DataFlowController.cs`), `HDMP-15-04` (ABHA Health ID linking in `PatientService.java` + `CareContextController.java`) |
| **Partial (`Pt`)** | **4** | `HDMP-27-05a` (gateway transaction state in `DataFlowController.cs` $\neq$ strict audit trail), `A-008-05` (transport safeguards), `R-006-01` (ECDH/AES-GCM in `EncryptionService.cs` vs. unguaranteed at-rest masking), `NRCES-FHIR-01` (FHIR R4 bundles in `FhirBundleBuilder.java` without runtime `ndhm.in#6.5.0` validation) |
| **Fail (`F`)** | **5** | `R-006-02` (no dedicated access-monitoring logs in `HealthInformationController.java` / `HipControllerAdvice.java`), `A-008-06`, `R-007-01`, `R-007-02` (no breach intimation workflows), `A-008-07` (no post-revocation erasure) |
| **Not Assessable (`NA`)** | **6** | `A-006-04`, `R-003-01`, `R-003-02`, `R-003-03` (Consent Manager UI outside HIP backend), `A-016-01` (infra routing), `HDMP-16-04` (organizational care-access policy) |

Pre-adjudication inter-rater agreement was **16 / 18 obligations (88.9%)**. The case study empirically confirms our matrix predictions: a CWE-oriented scan of `HipControllerAdvice.java` checks for log injection (CWE-117) or stack-trace leaks (CWE-209) without detecting the complete absence of statutory access-monitoring logs (`R-006-02`: **Fail**), while the register-plus-rubric workflow successfully surfaces both statutory gaps and compliant consent/ABHA patterns.

### 5.5 WASA Regulatory Transparency Finding

Exhaustive searches of NHA and ABDM portals identified no publicly available official specification defining citable technical clauses for WASA. While third-party auditors reference WASA milestones and OWASP Top 10 [16] testing scopes, keying a compliance register to unpublished criteria would violate auditability. Documenting this specification gap and re-sourcing technical controls to public standards (OWASP Top 10 [16], ABDM HDMP [14], and CERT-In empanelment norms [18]) preserves traceability.

### 5.6 Consolidated Reliability Summary

| Evaluation Layer | Sample Size | Primary Metric | Result |
|---|---|---|---|
| Exploratory agent matrix pass | 158 non-pilot cells | Linearly weighted $\kappa$ | **0.949** (exploratory) |
| Human matrix validation sample | 50 cells ($10 \times 5$) | Raw agreement / weighted $\kappa$ | **92.0%** / **0.746** |
| Human Bahmni HIP case study | 18 obligations (10 files) | Pre-adjudication raw agreement | **88.9%** (16/18) |

### 5.7 Register Coverage Transparency

The 18-row MVP register intentionally samples high-impact technical and architectural duties across DPDP Act/Rules [10, 11], ABDM HDMP [14], and NRCeS FHIR IG v6.5.0 [15] rather than claiming exhaustive statutory codification (see `validation/coverage-ratio.md`).

---

## 6. Threats to Validity

- **Construct Validity:** Shared coder assumptions (e.g., equating CWE-117 with log existence) can inflate agreement while producing false partial verdicts. We mitigated this via pinned CWE inventories, a closed legal-concept lookup list, and targeted human validation of `CAT-10` logging traps.
- **External & Scope Validity:** Documentary pattern verification is not equivalent to legal compliance certification. Scoring the Bahmni HIP repositories evaluates backend exchange code rather than hospital deployment posture; `HDMP-16-04` was explicitly excluded from code-pattern mapping as an organizational policy.
- **Statistical Validity:** Extreme class prevalence (`158/170` `not_visible`) inflates Cohen’s $\kappa$ due to high expected chance agreement. Consequently, we report exact agreement fractions, disagreement adjudications, and human sample statistics alongside $\kappa$.
- **Source Validity:** OWASP alignments on Bašić’s taxonomy are provisional [1, 16]; WASA lacks a public clause specification; and `OB-ABDM-NRCES-FHIR-01` awaits final StructureDefinition line-level page stamps [15].
- **Process Validity:** Initial matrix coding was agent-assisted and subsequently corrected through human dual coding and case-study validation; formal academic mentor sign-off remains the final gate prior to thesis submission.

---

## 7. Conclusion

Mapping Bašić and Giaretta’s ten CWE vulnerability categories [1] against India’s DPDP Act/Rules [10, 11] and ABDM obligations [14, 15] reveals a structural compliance blind spot: **92.9% (158/170)** of cross-mapped cells are `not_visible`, zero cells achieve `fully_covered` after human adjudication, and statutory access-logging and audit-trail obligations are uniformly invisible across all ten vulnerability categories (**20/20 `not_visible`**). Dual human rubric scoring on the open-source Bahmni India Distro HIP codebase (88.9% agreement) confirms that CWE-based review misses statutory access-monitoring failures (`R-006-02`: **Fail**) while our register-and-rubric workflow reliably identifies both compliance gaps and valid consent/ABHA patterns.

**Practical Implication:** Indian healthcare engineering teams cannot rely on CWE- or OWASP-only security reviews of AI-generated code to satisfy DPDP or ABDM obligations; pairing security scanning with obligation-specific documentary assessment is essential.

**Future Work:** Obtaining formal mentor sign-off and applying institutional thesis formatting; optionally expanding human dual coding across all 170 matrix cells or executing the two-round expert Delphi protocol (`validation/delphi/protocol.md`); expanding the obligation register beyond the 18-row MVP; and investigating automated static/MCP compliance-checking tools in a separate engineering project.

---

## References

[1] E. Bašić and A. Giaretta, "From Vulnerabilities to Remediation: A Systematic Literature Review of LLMs in Code Security," *arXiv preprint* arXiv:2412.15004v4, 2026. [Online]. Available: https://arxiv.org/abs/2412.15004  
[2] V. Ayala-Rivera and L. Pasquale, "The Grace Period Has Ended: An Approach to Operationalize GDPR Requirements," in *Proc. 26th IEEE Int. Requirements Engineering Conf. (RE)*, 2018, pp. 136–146. [Online]. Available: https://lpasquale.github.io/papers/RE18.pdf  
[3] H. Pearce, B. Ahmad, B. Tan, B. Dolan-Gavitt, and R. Karri, "Asleep at the Keyboard? Assessing the Security of GitHub Copilot’s Code Contributions," in *Proc. IEEE Symp. Security and Privacy (SP)*, 2022, pp. 754–768. [Online]. Available: https://arxiv.org/abs/2108.09293  
[4] N. Perry, M. Srivastava, D. Kumar, and D. Boneh, "Do Users Write More Insecure Code with AI Assistants?" in *Proc. ACM SIGSAC Conf. Computer and Communications Security (CCS)*, 2023, pp. 2785–2799. [Online]. Available: https://arxiv.org/abs/2211.03622  
[5] SafeGenBench Authors, "SafeGenBench: Benchmarking Security of LLM-Generated Code," *arXiv preprint* arXiv:2506.05692, 2025. [Online]. Available: https://arxiv.org/abs/2506.05692  
[6] Vibe-Coded Security Study Authors, "Security Failure Modes in Vibe-Coded Applications," *arXiv preprint* arXiv:2606.23130, 2026. [Online]. Available: https://arxiv.org/abs/2606.23130  
[7] A. R. Hevner, S. T. March, J. Park, and S. Ram, "Design Science in Information Systems Research," *MIS Quarterly*, vol. 28, no. 1, pp. 75–105, Mar. 2004, doi: 10.2307/25148625.  
[8] R. C. Nickerson, U. Varshney, and J. Muntermann, "A Method for Taxonomy Development and Its Application in Information Systems," *European Journal of Information Systems*, vol. 22, no. 3, pp. 336–359, 2013. [Online]. Available: https://opus.bibliothek.uni-augsburg.de/opus4/frontdoor/deliver/index/docId/93439/file/93439.pdf  
[9] D. Kundisch et al., "An Update for Taxonomy Designers: Methodological Guidance from Information Systems Research," *Business & Information Systems Engineering*, vol. 64, pp. 421–439, 2022, doi: 10.1007/s12599-021-00723-x.  
[10] Government of India, *The Digital Personal Data Protection Act, 2023* (Act No. 22 of 2023), *The Gazette of India*, Extraordinary, Part II, Sec. 1, Aug. 11, 2023. [Online]. Available: https://egazette.gov.in/WriteReadData/2023/248045.pdf  
[11] Ministry of Electronics and Information Technology (MeitY), *Digital Personal Data Protection Rules, 2025*, G.S.R. 846(E), *The Gazette of India*, Nov. 13, 2025. [Online]. Available: https://egazette.gov.in/WriteReadData/2025/267650.pdf  
[12] Ministry of Electronics and Information Technology (MeitY), *Corrigendum to the Digital Personal Data Protection Rules, 2025*, G.S.R. 892(E), *The Gazette of India*, 2025.  
[13] Ministry of Electronics and Information Technology (MeitY), *Commencement Notification under Section 1(2) of the DPDP Act, 2023*, G.S.R. 843(E), *The Gazette of India*, Nov. 13, 2025. [Online]. Available: https://egazette.gov.in/WriteReadData/2025/267647.pdf  
[14] National Health Authority (NHA), *Ayushman Bharat Digital Mission (ABDM): Health Data Management Policy*, Government of India. [Online]. Available: https://abdm.gov.in/strapicms/uploads/health_management_policy_bac9429a79.pdf  
[15] National Resource Centre for EHR Standards (NRCeS), *FHIR Implementation Guide for ABDM v6.5.0 (FHIR R4)*, package `ndhm.in#6.5.0`, May 8, 2025. [Online]. Available: https://nrces.in/ndhm/fhir/r4  
[16] OWASP Foundation, *OWASP Top 10:2021 — The Ten Most Critical Web Application Security Risks*. [Online]. Available: https://owasp.org/Top10/  
[17] MITRE Corporation, *CWE Top 25 Most Dangerous Software Weaknesses*. [Online]. Available: https://cwe.mitre.org/top25/  
[18] Indian Computer Emergency Response Team (CERT-In), *Empanelment of Information Security Auditing Organisations*. [Online]. Available: https://cert-in.org.in/certEmpanelment.jsp  

---

## Appendix A — Repository Map

| Component | Repository Path |
|---|---|
| Obligation Register | `register/obligation-register.md` |
| Category Profiles | `taxonomy/category-profiles.md` |
| Extended Taxonomy | `taxonomy/extended-taxonomy.md` |
| Cell-Coding Rule | `mapping/cell-coding-rule.md` |
| Reconciled Matrix | `mapping/main-matrix-reconciled.csv` |
| Human Sample Results | `mapping/human-sample-results.md` |
| Assessment Rubric | `rubric/assessment-rubric.md` |
| Rubric User Guide | `rubric/user-guide.md` |
| Bahmni HIP Case Study | `validation/case-study-report.md` |
| Validation Report | `validation/validation-report.md` |
| Delphi Protocol | `validation/delphi/protocol.md` |
| Decision Log | `logs/decision-log.md` |

Public artefact repository: https://github.com/suryaraj05/from-cwe-to-clause-artifact