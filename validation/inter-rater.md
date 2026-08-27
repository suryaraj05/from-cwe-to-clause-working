# Inter-rater reliability plan

**Primary statistic:** linearly weighted Cohen’s kappa on ordinal labels  
`fully_covered` > `partially_covered` > `not_visible`.

**Secondary (comparability):** unweighted Cohen’s kappa on the same labels.

**Exclusions from kappa:** cells flagged `criterion_underspecified` (counted separately as register feedback).

**Pilot cells:** excluded (handling A) or only post-freeze re-codes included (handling B) — as recorded at freeze in `logs/decision-log.md`.

**Partial sub-flags** (`partial_positive` / `partial_by_default`) are reported as descriptive proportions; they do not create extra kappa categories unless a later decision explicitly extends the label set (would require re-freeze).

Raw disagreements: `logs/disagreement-record.md` (both originals kept).
