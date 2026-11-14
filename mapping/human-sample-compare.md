# Human sample compare (fill AFTER both A and B finish)

**Date:** 2026-11-14  
**Present:** A: Surya  B: Rahul  

**Do not fill this during coding.**

---

## Agreement summary

| Column | Cells | Agree | Disagree | Notes |
|---|---|---|---|---|
| R-006-02 | 10 | 10 | 0 | Gap 1 confirmed (all N) |
| HDMP-27-05a | 10 | 10 | 0 | Gap 1 confirmed (all N) |
| A-008-05 | 10 | 8 | 2 | Disagreed on CAT-02 and CAT-10 (`Pd` vs `N`) |
| R-006-01 | 10 | 9 | 1 | Disagreed on CAT-07 (`Pp` vs `F`) |
| A-006-04 | 10 | 9 | 1 | Disagreed on CAT-06 (`Pd` vs `N`) |
| **Total** | **50** | **46** | **4** | **92.0% raw agreement** |

---

## Disagreement list

| CAT | Obligation | A | B | Temporary team consensus | Why |
|---|---|---|---|---|---|
| CAT-02 | A-008-05 | P (Pd) | N | P (Pd) | Under the rule's tiebreak, preventing buffer overflows/memory corruption (CWE-119/787) is an arguable technical safeguard against breach, though narrow. |
| CAT-10 | A-008-05 | P (Pd) | N | P (Pd) | Under the tiebreak rule, unchecked exceptions/return values (CWE-703/252) can fail open; candidate shared observable is fail-safe error handling. |
| CAT-07 | R-006-01 | P (Pp) | F | P (Pp) | Cryptography RCM checks that crypto used is sound (CWE-327/326), not that all personal data in the module is encrypted/masked/tokenized. |
| CAT-06 | A-006-04 | P (Pd) | N | N | `HOWTO` explicitly warns not to invent consent/withdrawal into AuthZ unless required by the CWE inventory; CWE-284/287 do not assess consent withdrawal parity. |

---

## Gap 1 check

| Question | Answer |
|---|---|
| Did both coders mark all 10 CATs as N for R-006-02? | Yes |
| Did both mark all 10 as N for HDMP-27-05a? | Yes |
| Did anyone treat CAT-10 as covering logging? | No |

---

## vs old consensus (after compare)

| Notable match / mismatch with `main-matrix-reconciled.csv` | Note |
|---|---|
| Gap 1 (R-006-02, HDMP-27-05a) | **Match** — all N |
| CAT-06 × A-006-04 | **Match** — N |
| CAT-07 × R-006-01 | **Mismatch** — old F → human **Pp** (patched) |
| CAT-08 / CAT-09 × A-008-05 | **Mismatch** — old Pp → human **N** (patched) |
| CAT-02 / CAT-04 / CAT-10 × A-008-05 | Subflag refined to **Pd** (patched) |

Full write-up: [`human-sample-results.md`](human-sample-results.md). Matrix CSV updated 2026-11-14.

---

## Ready for next phase?

- [x] Both worksheets complete  
- [x] This compare file complete  
- [x] Agent applied human patches + validation update  
- [ ] Healthcare evidence search in progress (Phase 2)