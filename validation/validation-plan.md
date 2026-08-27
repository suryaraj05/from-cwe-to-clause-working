# Validation plan (Hevner evaluation)

**Artifact:** From CWE to Clause — regulatory compliance assessment framework  
**Paradigm:** Design science (Hevner et al., 2004) — build + evaluate  
**Status:** 2026-08-27 — partial execution (matrix track complete)

---

## Evaluation questions

| # | Question | Method | Status |
|---|---|---|---|
| EQ1 | Do coders agree on matrix visibility labels? | Dual coding + linearly weighted κ | **Done (agent)** κ = 0.949, *n* = 158 |
| EQ2 | Does the register cover the intended regulatory surface? | Coverage ratio (documentary) | **Draft** — MVP partial scope |
| EQ3 | Is the extended taxonomy well-formed? | Nickerson ending conditions | **Partial** — objective mostly met; subjective pending |
| EQ4 | Can practitioners apply the rubric to real evidence? | Documentary case study | **Blocked** — needs audit report |
| EQ5 | Do experts find the instrument useful and clear? | Two-round Delphi | **Blocked** — needs panel |
| EQ6 | Are key findings structurally sound? | Worked examples (Gap 1, WASA) + matrix counts | **Done (agent)** |

---

## Activity schedule

| Phase | Activity | Owner | Output |
|---|---|---|---|
| 1 | Freeze cell-coding rule + MVP register | Team + agent | `cell-coding-rule` v0.3-frozen |
| 2 | Pilot + main matrix dual code | Agent (human pending) | `main-matrix-dual.csv`, κ |
| 3 | Reconciliation | Agent (mentor review pending) | `main-matrix-reconciled.csv` |
| 4 | Rubric + scoring protocol | Agent draft | `rubric/` |
| 5 | Coverage + Nickerson checklist | Agent draft | `validation/coverage-ratio.md` |
| 6 | **Human second coder** | **Team** | Updated κ / disagreement log |
| 7 | **Case study** | **Team** | `validation/case-study-report.md` (future) |
| 8 | **Delphi Round 1 & 2** | **Team + experts** | `validation/delphi/results/` (future) |
| 9 | Validation report final | Team | `validation/validation-report.md` |

---

## Acceptance thresholds (proposed — mentor confirm)

| Metric | Proposed threshold | Current |
|---|---|---|
| Matrix κ (weighted) | ≥ 0.70 for exploratory DS study | 0.949 (agent pair; interpret with caution) |
| Delphi Round 2 consensus | ≥ 70% agreement on usefulness items | Not run |
| Case study | ≥1 module assessed with dual rubric scores | Not run |

---

## Threats cross-reference

See `paper/06-threats-to-validity.md` — κ ≠ correctness; MVP scope; WASA absence; agent-as-coder.

---

## Files

| File | Role |
|---|---|
| [`project-status.md`](project-status.md) | Master tracker |
| [`human-next-steps.md`](human-next-steps.md) | Team checklist |
| [`validation-report.md`](validation-report.md) | Running report |
| [`delphi/protocol.md`](delphi/protocol.md) | Expert study design |
| [`case-study.md`](case-study.md) | Case study protocol |
