# Inter-rater reliability plan

**Primary statistic:** linearly weighted Cohen’s kappa on ordinal labels  
`fully_covered` > `partially_covered` > `not_visible`.

**Secondary (comparability):** unweighted Cohen’s kappa on the same labels.

**Exclusions from kappa:** cells flagged `criterion_underspecified` (counted separately as register feedback).

**Pilot cells:** excluded (handling A) or only post-freeze re-codes included (handling B) — as recorded at freeze in `logs/decision-log.md`.

**Partial sub-flags** (`partial_positive` / `partial_by_default`) are reported as descriptive proportions; they do not create extra kappa categories unless a later decision explicitly extends the label set (would require re-freeze).

Raw disagreements: `logs/disagreement-record.md` (both originals kept).

---

## Main-matrix result (2026-08-27)

**Pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`  
**Artifacts:** `mapping/main-matrix-dual.csv`, `mapping/main-matrix-kappa.json`, `mapping/main-matrix.md`

| Metric | Value |
|---|---|
| Cells total | 170 |
| Excluded (pilot handling A) | 12 |
| *n* for κ | 158 |
| Observed agreement *p_o* | 0.9937 |
| Unweighted Cohen’s κ | 0.949 |
| **Linearly weighted Cohen’s κ (primary)** | **0.949** |
| Non-pilot disagreements | 1 (CAT-06 × A-006-04) |

**Interpretation caution:** mass `not_visible` agreement inflates κ; see `paper/06-threats-to-validity.md` (agreement ≠ correctness). Reconciliation of the one κ disagreement (and pilot disagreements) is still open.
