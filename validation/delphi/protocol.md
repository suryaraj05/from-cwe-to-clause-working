# Delphi study protocol (design only — not executed)

**Purpose:** Expert validation of extended taxonomy (Nickerson subjective conditions) and rubric usefulness (EQ5).  
**Status:** protocol draft — **no panel recruited, no rounds run**

---

## Panel (team to define)

| Criterion | Target |
|---|---|
| Size | 7–15 experts (odd number preferred for median) |
| Background mix | Health informatics, Indian data protection law, application security / CWE practice |
| Conflict | No co-authors on Bašić paper; declare industry ties |

Recruitment log: create `validation/delphi/panel-log.md` when starting (names redactable in public artifact).

---

## Round 1 — clarity and structure

**Instrument:** online questionnaire (Google Form / equivalent — team choice)

**Materials sent blind:** category profiles excerpt, 5 sample matrix cells (Gap 1 + one partial + one full), rubric level definitions, scope disclaimer.

**Likert items (1–7):** disagree → agree

1. The RCM framing is understandable.  
2. The three matrix verdicts are distinguishable.  
3. The logging Gap 1 conclusion follows from the materials shown.  
4. The extended taxonomy dimensions are logically named.  
5. The rubric levels (P/Pt/F/NA) are applicable to documentary evidence.  
6. The instrument would be useful to a healthtech team assessing AI-generated modules.  
7. The WASA transparency finding is fairly stated.

**Open questions:**

- Which cell or criterion was hardest to interpret?  
- What obligation family is missing from the MVP register?  
- Any term from `imported-legal-concepts.md` that confused you?

**Analysis:** median, IQR per item; thematic coding on open answers.  
**Threshold to proceed to Round 2:** median ≥ 5 on items 1–5; no item median < 4 without revision.

---

## Revision gate (team)

If Round 1 fails threshold: revise rubric wording / sample cells only — **do not unfreeze cell-coding rule** unless real defect logged.

---

## Round 2 — consensus

**Materials:** revised pack + summary of Round 1 changes.

**Items:** repeat core Likert set + “overall readiness for case-study pilot” (1–7).

**Consensus rule:** ≥ 70% of panel rating 6–7 on usefulness (item 6) **and** no core item median drop vs Round 1.

**Output:** `validation/delphi/round2-summary.md` (create when run)

---

## Ethics / logistics (team)

- Inform consent + voluntary participation  
- No payment assumption in protocol — team decides  
- Store raw responses in private working repo only; public artifact gets aggregated stats

---

## Relation to other validation

Delphi does **not** replace human matrix re-coding or case study — it validates **face validity** and **expert acceptance**.
