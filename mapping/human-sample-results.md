# Human sample coding — results (2026-11-14)

**Coders:** Surya (A), Rahul (B)  
**Rule:** `cell-coding-rule` v0.3-frozen  
**Sample:** 10 CATs × 5 obligations = **50 cells**  
**Raw agreement:** 46/50 = **92%**  
**Worksheets:** `human-coder-A.md`, `human-coder-B.md`, `human-sample-compare.md`

---

## Headline outcomes

1. **Gap 1 confirmed by humans:** R-006-02 and HDMP-27-05a = **20/20 `not_visible`** (both coders; CAT-10 trap avoided).  
2. **Four disagreements reconciled** by the team (see below).  
3. **Important correction:** CAT-07 × R-006-01 moved from agent `fully_covered` → human consensus **`partially_covered` (Pp)**.  
4. **A-008-05 refined:** CAT-08 and CAT-09 are **`not_visible`** (both humans agreed); not every category is a safeguard slice.

---

## Disagreements → team consensus

| Cell | A | B | Consensus | Effect vs old matrix |
|---|---|---|---|---|
| CAT-02 × A-008-05 | Pd | N | **Pd** | Subflag Pp→Pd |
| CAT-10 × A-008-05 | Pd | N | **Pd** | Subflag Pp→Pd |
| CAT-07 × R-006-01 | Pp | F | **Pp** | **F → Pp** (major) |
| CAT-06 × A-006-04 | Pd | N | **N** | Matches old reconciled N |

Also (both agreed, differs from old all-Pp on A-008-05):

| Cell | Human | Old agent consensus |
|---|---|---|
| CAT-08 × A-008-05 | **N** | Pp |
| CAT-09 × A-008-05 | **N** | Pp |

---

## Updated matrix counts (after human sample patch)

| Verdict | Before | After |
|---|---|---|
| `not_visible` | 156 | **158** |
| `partially_covered` | 13 | **12** |
| `fully_covered` | 1 | **0** |

Source file updated: `main-matrix-reconciled.csv` (`reconciliation_source=human_sample_2026-11-14` on patched cells).

**Interpretation:** Under human coding, **no** Bašić category fully guarantees any MVP obligation in the sample — the closest is CAT-07 × encryption as a **partial**. Gap 1 remains the strongest structural finding.

---

## Reliability note

This is **human–human agreement on a 50-cell sample**, not a replacement full-matrix κ. Report as: sample raw agreement 92%; Gap 1 unanimous; four cells adjudicated.

Agent κ (0.949) remains exploratory historical context only.

---

## Phase 1 status

- [x] Two humans scored sample  
- [x] Compare complete  
- [x] Gap 1 confirmed  
- [x] Matrix patched for human consensus deltas  
- [ ] Case study (Phase 2) — needs healthcare evidence pack  

**Next:** gather healthcare module evidence → apply rubric (`validation/case-study.md`).
