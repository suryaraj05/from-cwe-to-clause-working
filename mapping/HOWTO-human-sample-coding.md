# HOWTO — Two humans score the sample columns

**Time:** ~2–3 hours total (1–1.5h each alone + 30–45 min together)  
**Cells:** 10 categories × 5 obligations = **50 cells**

---

## Golden rules

1. **Two people code separately.** Do not talk about answers until both finish.  
2. **Do NOT open** `main-matrix-reconciled.csv` or `main-matrix.md` while coding.  
3. Each person fills **only their own file**:  
   - Person 1 → `mapping/human-coder-A.md`  
   - Person 2 → `mapping/human-coder-B.md`  
4. Labels only: `F` / `P` / `N`  
   - If `P`, add subflag: `Pp` (positive) or `Pd` (by default / unsure)  
5. One short justification per cell (or per block if many are identical N).

---

## What you are judging

For each cell (**CAT-xx × obligation**), ask:

> If a patient-data module was checked under this category and **all findings were fixed** to that category’s normal standard (the **RCM**), how much of this legal duty does that fix **guarantee**?

| Label | Meaning |
|---|---|
| **F** (`fully_covered`) | Fixing this category **necessarily** satisfies the duty |
| **P** (`partially_covered`) | Some shared technical overlap, but duty is **not guaranteed** |
| **N** (`not_visible`) | Category can be fully clean while the duty still has **no evidence** |

**Hard traps**
- Logging / audit trail → almost always **N** (including CAT-10). CWE-117 ≠ “logs exist.”  
- Do not invent consent/withdrawal into AuthZ unless the category inventory truly requires it.  
- If unsure between P and N → prefer **P** with subflag **Pd** (rule tiebreak). Clear N stays N.

---

## Step-by-step

### Step 1 — Assign people (2 minutes)

| Role | Name | File to fill |
|---|---|---|
| Human A | _____________ | `mapping/human-coder-A.md` |
| Human B | _____________ | `mapping/human-coder-B.md` |
| Not coding (optional) | _____________ | Searches healthcare evidence; does not peek at scores |

### Step 2 — Each coder reads once (15 minutes)

Open only:
1. `mapping/cell-coding-rule.md` (verdicts section)  
2. `taxonomy/category-profiles.md` (what each CAT checks)  
3. `register/obligation-register.md` (the 5 duties below)  
4. Your empty worksheet (`human-coder-A.md` or `B.md`)

### Step 3 — Score column by column (60–90 minutes)

Do obligations in this order (easier → harder):

1. **R-006-02** — access logs exist?  
2. **HDMP-27-05a** — audit trail exists?  
3. **A-008-05** — reasonable security safeguards  
4. **R-006-01** — encryption / masking / tokens  
5. **A-006-04** — withdrawal as easy as giving consent  

For each obligation, score **CAT-01 … CAT-10**.

**Shortcut allowed:** If all 10 are the same (e.g. all N for logging), write one block justification and put N in every CAT row.

### Step 4 — Save and stop

Do not compare yet. Tell the other person “I’m done.”

### Step 5 — Compare together (30–45 minutes)

1. Open both worksheets side by side.  
2. Fill `mapping/human-sample-compare.md` (agree / disagree).  
3. For disagreements: discuss using the rule — pick a temporary team consensus (or leave as open for guide).  
4. **Now** you may look at `main-matrix-reconciled.csv` and see where humans match the old consensus.

### Step 6 — Message me

Send:
- both worksheets filled (or say “done in repo”)  
- list of disagreements  
- whether Gap 1 stayed N for all 10 CATs  

Then I build the next files (compare summary, validation update, case-study scaffold).

---

## The 5 obligations (cheat sheet — from register)

| Short ID | Duty in plain words | Assessment question |
|---|---|---|
| **R-006-02** | Can you see who accessed personal data via logs/monitoring? | Are access logs/monitoring present? |
| **HDMP-27-05a** | Is there a strict audit trail of processing with access to personal data? | Is an audit trail present? |
| **A-008-05** | Reasonable security safeguards to prevent breach | Are reasonable safeguards present? |
| **R-006-01** | Encryption / obfuscation / masking / virtual tokens | Is personal data protected by one of those measures? |
| **A-006-04** | Withdrawal as easy as giving consent | Is withdrawal effort comparable to grant? |

## Categories (cheat sheet)

| CAT | Name | Looks for |
|---|---|---|
| 01 | Injection | SQL/XSS/command injection etc. |
| 02 | Memory Management | overflows, unsafe memory |
| 03 | File Management | path traversal, uploads |
| 04 | Deserialization | unsafe deserialize |
| 05 | Sensitive Data Exposure | PII/secrets exposure |
| 06 | Authn / Authz | login, access control |
| 07 | Cryptography | sound crypto |
| 08 | Resource Management | leaks, resource limits |
| 09 | Coding Standards | unsafe API/practice |
| 10 | Error Handling | bad error handling (**CWE-117 ≠ logging existence**) |

---

## Done when

- [ ] A finished `human-coder-A.md` alone  
- [ ] B finished `human-coder-B.md` alone  
- [ ] Compare file filled  
- [ ] Gap 1 result recorded  
- [ ] Disagreements listed  

**Do not edit** `main-matrix-reconciled.csv` during this exercise.
