# Threats to validity

## Construct — shared wrong intuitions and kappa

Inter-rater reliability measures **agreement**, not **correctness**. If both coders share a plausible but false intuition — e.g. “logs are files” (CAT-03) or “CWE-117 means logging is covered” (CAT-10) — they may agree on a wrong verdict and statistics will look excellent.

**Defence:** category **CWE inventories** in `taxonomy/category-profiles.md` are the authority on what an RCM guarantees. Shared observables must be named from that inventory. The closed-list clearance for “logging” does not establish capability (see `mapping/imported-legal-concepts.md`). Human sample coding explicitly tested CAT-10 × logging columns — all `not_visible`.

## Scope

Pattern presence ≠ legal compliance. Organisational process (e.g. HDMP cl.16.4 non-exclusion) may be `criterion_underspecified` as a code criterion. The Bahmni case study scores **patterns in a HIP code slice**, not organisational compliance.

## External / source

WASA has no public official specification (separate finding). Bašić OWASP alignments are provisional. FHIR row retains a partial page-stamp on exact `meta.profile` wording.

## Internal — commencement and version pin

Act vs Rules commencement are separate; effective dates depend on 843(E) and Rules r.1 as read. Matrix coding pins register + category-profile versions; rewording after pin requires a re-code decision. Phase 3 left the register pin unchanged.

## Statistical — prevalence and coder composition

Reported linearly weighted κ = **0.949** (*n* = 158 non-pilot cells) for the **agent** dual-coding pass. **Prevalence effect:** when most reconciled cells are `not_visible` (now **158/170**), chance-corrected agreement can remain high even if both coders share systematic blind spots on the few non-empty cells.

**Primary human trust signal:** 50-cell human sample at **92%** raw agreement — not a full-matrix κ. Report sample agreement alongside exploratory κ; do not headline agent κ alone.

**Reconciliation / human patches:** five agent-reconciled cells plus human moves (CAT-07 × R-006-01 F→Pp; CAT-08/09 × A-008-05 Pp→N). Mentor review still pending.
