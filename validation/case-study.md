# Documentary case study protocol

**Purpose:** Apply assessment rubric to an **existing** hospital / healthtech audit report (or equivalent documentary pack) — Hevner evaluation EQ4.  
**Status:** protocol only — **no case selected, no scores recorded**

---

## Preconditions (team)

| # | Requirement |
|---|---|
| 1 | Written permission to use audit excerpts in thesis (anonymised) |
| 2 | Evidence pack indexed (PDFs, redactions logged) |
| 3 | Two raters available for dual scoring |
| 4 | Register + rubric versions pinned in case header |

---

## Case selection criteria

Prefer a report that:

- Covers a **patient-data module** or health app backend (not pure org policy only)  
- Mentions security testing or CWE-style findings (optional — Gap 1 still applies if absent)  
- Is recent enough to reference DPDP 2023 / Rules 2025 awareness (even if pre-commencement)

**Do not** generate new code or run new scans for this project.

---

## Procedure

Follow [`../rubric/scoring-protocol.md`](../rubric/scoring-protocol.md).

Additional case-study steps:

1. **Characterise artefact** — system description, assessment scope, date, assessor identity (anonymised).  
2. **Map evidence to register rows** — table of doc section → obligation_id.  
3. **Score all 17 matrix obligations** (+ note HDMP-16-04 separately if relevant).  
4. **Cross-check matrix hints** — where matrix said all `not_visible`, confirm rubric NA then obligation review.  
5. **Gap 1 focus** — explicit subsection on logging/audit evidence in the pack vs R-006-02 / HDMP-27-05a.  
6. **Dual rate + reconcile** — record κ or percent agreement on P/Pt/F/NA (4-level — report both).  
7. **Write narrative** — 2–3 pages: what the rubric surfaced that CWE-only review missed.

---

## Report skeleton (create as `validation/case-study-report.md` when run)

```markdown
# Case study report

## Case metadata
- Evidence pack: …
- Register: register-v0.3-mvp-2026-08-27
- Rubric: rubric-v0.1-2026-08-27
- Raters: …

## System summary (from documents)
…

## Scoring summary table
| obligation_id | Rater A | Rater B | Consensus | Key evidence |
…

## Gap 1 (logging)
…

## Matrix hint audit
| obligation | Matrix pattern | Rubric outcome | Comment |
…

## Limitations
Pattern assessment ≠ legal compliance; pack may omit org-process evidence.

## Appendix
Redacted evidence index
```

---

## Public vs private repo

- **Private working repo:** full audit PDFs  
- **Public artifact:** report with redacted excerpts only, or aggregated scores if mentor prefers

---

## Blocked until

Team supplies audit report + permission. No placeholder scores.
