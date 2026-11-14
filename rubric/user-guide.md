# Rubric user guide — how a developer uses the framework

**Audience:** Developer, vibe coder, or reviewer assessing a patient-data module  
**Depends on:** obligation register · cross-mapping matrix · assessment rubric  

---

## What you give

An **evidence pack** about one module (docs, configs, relevant source files, audit notes). You do **not** need to run our research scanners — this method is documentary.

## What you do

1. Open the **obligation register** — each row is a duty + assessment question.  
2. Open the **matrix** — if a duty is `not_visible` for all categories, CWE-only review will not guarantee it; check it explicitly.  
3. Score each duty with the **rubric**: Pass / Partial / Fail / NA.  
4. **Always** score logging/audit duties (Gap 1).  
5. Write a short report with citations to evidence.

## What you get

A scored checklist showing which DPDP/ABDM **patterns** are present, partial, missing, or outside this code slice — **not** a legal compliance certificate.

## Worked example

Bahmni ABDM HIP case study: [`../validation/case-study-report.md`](../validation/case-study-report.md).
