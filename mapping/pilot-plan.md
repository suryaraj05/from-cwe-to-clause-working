# Pilot plan (pre-freeze)

**Purpose:** Stress-test `cell-coding-rule` v0.2 **before** freeze.  
**Size:** 8–12 cells.  
**Coders:** independent; no discussion until both finish.

## Selection (do before coding)

Choose cells that include at least:

- 2 expected obvious `fully_covered` (or near)
- 2 expected obvious `not_visible`
- 4+ hard boundaries (AuthZ×consent/withdrawal; logging×breach intimation; crypto×localization; etc.)

Record the exact cell IDs (category × `obligation_id`) and the **register version** used.

## After both finish

1. Tally disagreements (verdict and partial sub-flag).
2. Revise `cell-coding-rule.md` and/or `imported-legal-concepts.md` from those disagreements.
3. Decision log: what changed and why.
4. At freeze, record pilot handling **A** (exclude from kappa) or **B** (re-code after freeze).

## Worksheet

Create `pilot-worksheet.md` at pilot start with columns: cell_id, coder, verdict, partial_subflag, underspecified, justification, timestamp.
