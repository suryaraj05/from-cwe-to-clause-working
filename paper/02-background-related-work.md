# Background and related work

**Status:** draft — verify all citations against `sources.md` before submission.

## AI-generated code security

Systematic reviews and empirical studies document insecure patterns in LLM-assisted development (e.g. Pearce et al.; Perry et al.; SafeGenBench). Bašić and Giaretta (arXiv:2412.15004**v4**) consolidate **21 studies** into ten vulnerability categories mapped to CWE—our matrix row vocabulary. Recent work on “vibe-coded” applications highlights AI-specific failure modes. These lines of research are **jurisdiction-agnostic** and do not encode Indian statutory consent, logging, or ABDM interchange duties.

## Regulation-to-controls methods

Ayala-Rivera and Pasquale’s GuideMe operationalises GDPR through privacy controls—a methodological precedent for obligation extraction. No equivalent catalogue targets DPDP, ABHA/HIE-CM flows, or NRCeS FHIR profiles for **assessing code already written** by AI tools.

## Taxonomy development

Nickerson et al. provide ending conditions for IS taxonomies; we extend Bašić categories with obligation-level dimensions and document cross-product outcomes. Kundisch et al. update taxonomy design practice—useful for stating amendment rules.

## Design science

Hevner et al. frame our contribution: an artefact (framework) plus rigorous evaluation. Our evaluation mix is documentary—dual coding, coverage ratio, Delphi, case study—not implementation.

## Indian regulatory context

Primary sources: DPDP Act 2023; DPDP Rules 2025 (G.S.R. 846(E)); commencement G.S.R. 843(E); ABDM Health Data Management Policy; NRCeS FHIR IG v6.5.0. Commencement is staged; MVP register rows record +18m effective dates where verified.

## WASA and production-gate assessment

Vendor materials describe WASA milestones for health applications; we found **no public official specification** (finding in `findings-wasa-transparency.md`). Adjacent expectations are re-sourced to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings—without WASA-keyed register rows.

## Gap statement (three gaps from brief)

1. CWE categories cannot express legal obligations such as itemised consent or comparable-ease withdrawal.  
2. No DPDP/ABDM obligation register for AI-generated healthcare code assessment.  
3. AI-security research lacks Indian jurisdictional grounding—models may produce plausible non-Indian compliance shapes.

Our framework addresses these at the **pattern-assessment** level, with explicit limits.
