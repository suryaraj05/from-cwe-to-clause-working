# Project brief

## Who we are
Undergraduate computer science research team in India; mentor-approved research project. We are not building software — we are producing a research artifact.

## HARD CONSTRAINT
This project involves **NO code and NO software**. Do not propose, write, or plan: application code, scripts, static analysis runs, prompt-based code generation experiments, tooling, notebooks, or automation of any kind. Mentor requirement: no application building and no touching of code. Every deliverable is a document. If a next step seems to require running or writing code, **stop and say so** instead of doing it.

## Project title
From CWE to Clause: A Regulatory Compliance Assessment Framework for AI-Generated Healthcare Code under India's DPDP Act 2023 and ABDM

## What the project is
Healthcare software teams in India increasingly write code with AI coding assistants. Research shows AI-generated code is often insecure; one systematic review consolidates findings into ten vulnerability categories. That work measures code against CWE and OWASP — jurisdiction-agnostic catalogues. Indian healthtech is bound by the DPDP Act 2023 and ABDM health data standards. No instrument yet tells a team whether an AI-generated patient-data module exhibits patterns consistent with those obligations. We build and validate that instrument.

**Scope honesty (standing):** We assess whether code (or described system behaviour in a documentary case study) exhibits a *compliant pattern*. That is necessary but not sufficient for legal compliance, which also depends on organizational process invisible in code. State this explicitly in the paper.

## The three gaps
1. **CWE cannot express a legal obligation.** The ten vulnerability categories map to CWEs (technical weaknesses). They cannot represent requirements such as itemized purpose-bound consent or withdrawal that propagates to access decisions. Flawless access control can still violate DPDP.
2. **Regulation-to-controls research exists for GDPR (GuideMe), for human-authored requirements.** Nothing covers DPDP, ABDM machinery (ABHA, HIE-CM consent mediation, FHIR R4), or assessing code a model already wrote.
3. **AI-code security research has no jurisdictional dimension.** Assistants trained mostly on Western corpora produce HIPAA/GDPR-shaped flows that look professional but are not what Indian law requires — a directional failure, not random error.

## Base papers
- Bašić, E. & Giaretta, A. "From Vulnerabilities to Remediation…" **Cite arXiv:2412.15004v4** (version in the reference). Ten vulnerability categories. **Study count in v4: 21 studies** (read off §4; recorded in sources.md). Profiles: `taxonomy/category-profiles.md`.
- "Understanding the (In)Security of Vibe-Coded Applications." arXiv:2606.23130, 2026. AI-specific patterns; agent-limitation account; prompting/models reduce but do not eliminate risk.
- Ayala-Rivera, V. & Pasquale, L. "The Grace Period Has Ended…" IEEE RE 2018, pp. 136–146. GuideMe: six-step GDPR → 40 privacy controls. **Method source.**

## Method references
- Hevner et al., MISQ 2004 — design science: artifact + rigorous evaluation.
- Nickerson, Varshney & Muntermann, EJIS 2013 — taxonomy method; objective/subjective ending conditions.

## Primary regulatory sources
DPDP Act 2023; DPDP Rules 2025 (G.S.R. 846(E)) + corrigendum (G.S.R. 892(E)) + commencement (G.S.R. 843(E)); ABDM Health Data Management Policy; NRCeS FHIR IG / API materials; OWASP Top 10 and CERT-In empanelment listings where security-assessment-adjacent obligations are needed.

## WASA (object of study — not a primary register source)
No public official WASA specification located (see `logs/wasa-absence-finding.md`). **No register row may be keyed to WASA.** Re-source to OWASP Top 10, ABDM HDMP, and CERT-In empanelment listings. Write the absence as a reported finding on regulatory transparency (own subsection). Reopen if official NHA milestone/certification text surfaces.

## Matrix coding (Gap 1)
Emptiness / `not_visible` rate is an **outcome**, not a success criterion. Freeze `mapping/cell-coding-rule.md` before coding any cell; dual-code; report kappa; let Gap 1’s claim follow the numbers (including narrowing if most cells are partial/full).

Never cite a clause/section/quoted obligation unless it comes from a supplied or retrieved source document. Never reconstruct legal text from memory.

## Five deliverables
1. Obligation register  
2. Extended taxonomy  
3. Cross-mapping matrix  
4. Assessment rubric  
5. Validation report  

## Quality / citation / working conventions
Publication-worthy auditability; paper shape from day one; related work only in service of the gap; no invented citations; maintain decision log, source version stamps, citation ledger, disagreement record.

## What we want from the assistant
Research collaborator: push back on weak reasoning; flag missing sources; refuse out-of-scope accommodations; precision over encouragement.
