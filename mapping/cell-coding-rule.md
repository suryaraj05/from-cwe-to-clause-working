# Cross-mapping cell coding rule

**Document ID:** `cell-coding-rule`  
**Rule version:** `v0.2-amended-unfrozen` (2026-08-27)  
**Status:** APPROVED IN PRINCIPLE — **seven amendments folded; DO NOT FREEZE YET.**  
**Depends on register version:** pin at freeze (see freeze checklist). Current working register tip: see `register/VERSION.md`.  
**Depends on category profiles:** `taxonomy/category-profiles.md` (row vocabulary). Coding against an undefined category name is invalid.

**Do not run the main coding pass until this file is marked FROZEN** in `logs/decision-log.md` with named assent, rule version, register version, **category-profile version**, and content hash.

---

## Unit of analysis

One **cell** = one **row** (a Bašić & Giaretta vulnerability category, as used in our extended taxonomy input) × one **column** (one atomic `derived_criterion` from a **pinned** obligation-register version).

---

## Defined counterfactual object (mandatory)

Coders do **not** imagine an arbitrary “module.” Every verdict is a claim about this object:

> **Remediated-under-category module (RCM):** a patient-data module that has been assessed under *this* vulnerability category and has had **all findings remediated to that category’s own ordinary standard** (the CWE/OWASP-shaped bar used for that category in the literature we cite for the row).

The three matrix verdicts are statements about **what the RCM guarantees** with respect to the column criterion — checkable against category definition + criterion text, not against a silently imagined system.

**Deliberately not an existential claim.** Do **not** read `not_visible` as “there exists some pathological implementation that is category-clean but non-compliant.” That bar is almost always true and would inflate `not_visible`. Anchor every verdict to the **RCM**.

---

## Question the cell answers

*Given the RCM for this category, how much of this obligation criterion does that remediation guarantee?*

We are **not** asking whether the obligation is important, whether we hope the cell is empty, or whether a creative stretch could map the category. We ask what the category’s **ordinary technical vocabulary** already forces into evidence when the RCM is achieved.

---

## Matrix verdicts (exactly three; ordinal)

Order for reliability: `fully_covered` > `partially_covered` > `not_visible`.

### `fully_covered`

**All must hold:**

1. Every observable named in the column’s `derived_criterion` and `evidence_required` is an instance of, or is strictly entailed by, the observables that category already assesses under its ordinary CWE/OWASP reading; **and**
2. The **RCM necessarily satisfies** the criterion (evidence sufficient to pass the column’s `assessment_question` on the pattern); **and**
3. The entailment can be stated in one sentence **without using any term from the closed imported-legal-concepts list** (`mapping/imported-legal-concepts.md`), unless that term already appears in the category’s own definition sheet. Lookup against the closed list — not free judgement.

**Fail any one → do not code `fully_covered`.**

### `partially_covered`

**Use when:**

1. The category and the criterion share at least one concrete technical observable (e.g. access control, encryption, logging, input validation); **but**
2. Achieving the **RCM** does **not** require the obligation-specific elements of the criterion — the RCM **may or may not** satisfy the criterion; the category assessment produces some relevant evidence without guaranteeing the criterion.

**Always record a sub-flag (data field; same matrix cell colour/label):**

| Sub-flag | When |
|---|---|
| `partial_positive` | Coder positively determined shared observable **and** missing obligation-specific element (can name both). |
| `partial_by_default` | Coder used the imprecision / uncertainty tiebreak (below), or could not cleanly separate shared vs missing without forcing. |

Report the proportion of `partially_covered` cells that are `partial_positive` vs `partial_by_default` in results. The matrix display may collapse them; the dataset must not.

**Tiebreak (imprecision):** when unsure between `partially_covered` and `not_visible`, choose **`partially_covered`** with sub-flag **`partial_by_default`** if any non-trivial candidate shared observable is arguable. Do **not** use this tiebreak to avoid a clear `not_visible`.

**Justification (required):**  
`partial_positive`: “Shared: [observable]. Missing from RCM guarantee: [obligation-specific element].”  
`partial_by_default`: “Tiebreak: [why uncertain]. Candidate shared: [X].”

### `not_visible`

**All must hold:**

1. The **RCM can fully satisfy the category** while producing **no** evidence toward the `derived_criterion`; **and**
2. The criterion’s observables are not expressible as weaknesses or controls inside that category’s ordinary vocabulary; **and**
3. The coder is **not** choosing `not_visible` because the mapping feels imprecise, difficult, or narratively convenient. Imprecision → `partially_covered` + `partial_by_default` (or raise `criterion_underspecified`), **not** `not_visible`.

**Justification (required):**  
“RCM can be category-clean while [criterion observable] remains absent, because [category] only tracks [X].”

---

## Process flag (not a matrix verdict): `criterion_underspecified`

If the coder cannot apply the tests because the **register criterion** (or its `assessment_question` / `evidence_required`) is too vague, contradictory, or non-atomic — **do not force a verdict**.

1. Set flag `criterion_underspecified = true` on the cell attempt.
2. Leave the matrix verdict blank for that cell.
3. Send the obligation row back to the register for rewording (`register/CHANGELOG.md` + disagreement/feedback note).
4. After the criterion is revised under a new register version, code the cell afresh.

This flag is **not** a fourth coverage label. Counts of flagged criteria are reportable as instrument quality (Deliverable 1 feedback), not as Gap 1 coverage.

---

## Closed list: imported legal concepts

Normative closed list: [`imported-legal-concepts.md`](imported-legal-concepts.md) (version-pinned).  
Amendments to that list require a decision-log entry and bump of **this** rule’s version. Coders lookup; they do not extend ad hoc mid-coding.

---

## What this rule deliberately does *not* do

- Treat `not_visible`-heavy matrices as success. Emptiness is an **outcome**.
- Forbid narrowing Gap 1 if most cells are `fully_covered` or `partially_covered`.
- Allow coding from hoped-for narrative.
- Use existential “pathological clean-but-noncompliant” constructions for `not_visible`.

---

## Pilot (required before freeze)

1. Both coders independently code **8–12 pilot cells** chosen to span obvious `fully_covered`, obvious `not_visible`, and hard boundary cases (incl. likely partials).
2. Compare disagreements; revise this rule **and** the imported-concepts list from those disagreements.
3. All revisions happen **before** freeze — not after.
4. **Pilot handling (choose one; record in decision log at freeze):**
   - **A:** Exclude pilot cells from the reported reliability statistic; **or**
   - **B:** Re-code pilot cells after freeze under the frozen rule; only post-freeze codes enter kappa.
5. Quietly counting pilot codes in the main kappa without A or B is not allowed.

Pilot worksheet: `mapping/pilot-worksheet.md` (create at pilot start).

---

## Main coding procedure (after freeze only)

1. Confirm freeze entry: rule version, register version, content hash, pilot handling A/B, both initials.
2. Build the cell list for the pinned register × pinned category sheet.
3. **Coding order:** proceed **by obligation column** (all categories for one criterion, then next criterion), **or** use a pre-drawn random cell order recorded in the worksheet. Do **not** code an entire category row straight through in a single uninterrupted block (reduces within-row rhythm carry).
4. Independently code (`coder_a`, `coder_b`). For each cell record: verdict, partial sub-flag if any, `criterion_underspecified` if any, one-sentence justification, **timestamp** (date-time).
5. No discussion during first pass.
6. Reliability: **primary = linearly weighted Cohen’s kappa** on the ordinal three verdicts (`fully_covered` > `partially_covered` > `not_visible`). Report **unweighted Cohen’s kappa** alongside for comparability. Cells with `criterion_underspecified` are excluded from kappa (and counted separately).
7. Record raw disagreements in `logs/disagreement-record.md` (both original labels + sub-flags kept).
8. Reconcile only after kappa is recorded; reconciliations get a short reason.
9. Report counts: verdicts; partial_positive vs partial_by_default; underspecified returns; then interpret Gap 1 from the numbers.

---

## Non-codes / exclusions (not verdicts)

| Label | When |
|---|---|
| `deferred` | Category definition not yet frozen; cell out of this round |
| `out_of_scope_row` | Row is an obligation-dimension extension, not a Bašić input category |
| `criterion_underspecified` | Process flag — return to register (above) |

---

## Worked discrimination (training only — not coded cells)

Reframed on the **RCM**:

| Contrast | Why |
|---|---|
| AuthZ × “access requires authenticated role” | RCM under AuthZ often **necessarily** yields that pattern → candidate `fully_covered` if no imported-list term is required; else strong `partial_positive`. |
| AuthZ × “withdrawal of consent disables consent-based access with ease comparable to grant” | RCM shares access control but does not guarantee withdrawal/consent elements (on imported list) → `partially_covered` / `partial_positive`, not `fully_covered`, and not `not_visible` if access evidence exists. |
| Injection × “notice itemises personal data and purposes” | Injection RCM can be clean with no notice evidence → `not_visible`. |
| **CAT-10 × OB-DPDP-R-006-02** (access logs / r.6(1)(c)) | CWE-117 presupposes logs; RCM under Error Handling does **not** evidence access-log existence/sufficiency → **`not_visible`**. Treating CWE-117 as partial coverage is the instructive trap. |
| CAT-03 × OB-DPDP-R-006-02 | Path/upload CWEs ≠ access logging; “logs are files” is a vocabulary pun → **`not_visible`**. |
| Any Bašić CAT × OB-ABDM-NRCES-FHIR-01 | Profile conformance / StructureDefinition expectations not in CWE inventories → expected **`not_visible`** across rows (second clean Gap 1 column beside logging). |

---

## Freeze checklist (all required)

- [ ] Category profiles pinned (`taxonomy/category-profiles.md` version)
- [ ] Counterfactual object = **RCM** as defined above (amendment 1)
- [ ] `criterion_underspecified` process flag documented (amendment 2)
- [ ] `partial_positive` / `partial_by_default` sub-flags documented (amendment 3)
- [ ] Closed imported-legal-concepts list written, versioned, linked (amendment 4)
- [ ] Pilot run (8–12 cells); disagreements used to revise rule **before** freeze (amendment 5)
- [ ] Pilot handling A or B recorded in decision log (amendment 5)
- [ ] Primary reliability = linearly weighted kappa; unweighted reported alongside (amendment 6)
- [ ] Freeze pins **rule version** + **register version** + **content hash**; standing rule: reworded criteria → log whether affected cells need re-code (amendment 7)
- [ ] Column-wise or randomized cell order + per-cell timestamps required in procedure
- [ ] Both coders initial below
- [ ] Decision-log entry marks FROZEN with versions/hash

**Assent (only at freeze):** coder_a: ________ date: ________ coder_b: ________ date: ________

**At freeze fill-in:** rule version: ________ register version: ________ content hash: ________ pilot handling: A / B
