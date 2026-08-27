# Threats to validity

## Construct — shared wrong intuitions and kappa

Inter-rater reliability (linearly weighted kappa) measures **agreement**, not **correctness**. If both coders share a plausible but false intuition — e.g. “logs are files” (CAT-03) or “CWE-117 means logging is covered” (CAT-10) — they may agree on a wrong `partially_covered` verdict and kappa will look excellent.

**Defence:** category **CWE inventories** in `taxonomy/category-profiles.md` are the authority on what an RCM guarantees. Shared observables must be named from that inventory, not from colloquial security vocabulary. The closed-list clearance for “logging” does not establish capability (see `mapping/imported-legal-concepts.md`). Pilot cells CAT-10 × R-006-02 and CAT-03 × R-006-02 are designed to surface this threat before main coding.

## Scope

Pattern presence ≠ legal compliance. Organisational process (e.g. HDMP cl.16.4 non-exclusion) may be `criterion_underspecified` as a code criterion.

## External / source

WASA has no public official specification (separate finding). Bašić OWASP alignments are provisional. Register rows require page-stamps before freeze.

## Internal — commencement and version pin

Act vs Rules commencement are separate; effective dates depend on 843(E) and Rules r.1 as read. Matrix coding pins register + category-profile versions; rewording after pin requires a re-code decision.

## Statistical — κ after main matrix (2026-08-27)

Reported linearly weighted κ = **0.949** (*n* = 158 non-pilot cells). **Prevalence effect:** when 156/170 reconciled cells are `not_visible`, chance-corrected agreement can remain high even if both coders share systematic blind spots on the few non-empty cells. Report κ alongside **cell-level disagreement counts** (1 non-pilot; 5 total before reconciliation) and **prevalence-aware interpretation** (not only a single κ headline).

**Coder composition:** coder_b was an independent agent pass — human replication required before publication-grade IRR claims (`validation/human-next-steps.md`).

**Reconciliation:** five cells adjudicated; mentor review still pending for CAT-06 × A-006-04 (`not_visible` over `partially_covered`).
