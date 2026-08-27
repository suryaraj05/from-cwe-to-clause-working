# Scoring protocol

**Pairs with:** [`assessment-rubric.md`](assessment-rubric.md)  
**Status:** draft — for team + case study execution

---

## Roles

| Role | Responsibility |
|---|---|
| Lead rater | Applies rubric to each register row; cites evidence |
| Second rater | Independent scoring on same evidence pack |
| Adjudicator | Resolves score disagreements; logs in `logs/disagreement-record.md` |

Matrix coders and rubric raters may differ; matrix κ does not substitute for rubric IRR.

---

## Procedure (per module / case)

### 1. Pin artefacts

- Register version  
- Matrix consensus file  
- Evidence pack inventory (filenames, dates, redaction notes)

### 2. For each register row (17 matrix rows + optional org-policy rows)

1. Read `derived_criterion`, `assessment_question`, `evidence_required`.  
2. Consult matrix column for that obligation: note which CATs are non-`not_visible` (hints only).  
3. Collect cited evidence from the pack.  
4. Assign **P / Pt / F / NA** per rubric definitions.  
5. Write one-sentence justification with evidence pointer (doc + page/section).  
6. Timestamp.

### 3. Gap 1 mandatory pass

Always score **R-006-02** and **HDMP-27-05a** explicitly, even when matrix says NA via CWE taxonomy.

### 4. Dual score + reconcile

Second rater repeats steps 2–3 blind to first rater’s scores (or with initials hidden).  
Disagreements → adjudication → log.

### 5. Report

Use template in [`../validation/case-study.md`](../validation/case-study.md) § Report skeleton.

---

## NA vs Fail discipline

| Situation | Score |
|---|---|
| Evidence pack silent on criterion; matrix all `not_visible` | **NA** (CWE path) + note “obligation review inconclusive” if no direct evidence either |
| Evidence shows absence (e.g. no logs described) | **F** on obligation review |
| Evidence shows partial implementation | **Pt** |

Do not score **Pass** because “no CWE category checks this anyway.”

---

## Commencement awareness

Rows with `effective_from` after assessment date → flag as **future obligation** in report; still score pattern if team assesses forward-looking design.

MVP commencement: most substantive DPDP rows **2027-05-13** (+18m from G.S.R. 843(E)).

---

## Quality checks before submission

- [ ] Every score has evidence citation or explicit “no evidence in pack”  
- [ ] Gap 1 rows addressed  
- [ ] HDMP-16-04 handled as org-policy (not forced P/F)  
- [ ] Scope disclaimer included in report header
