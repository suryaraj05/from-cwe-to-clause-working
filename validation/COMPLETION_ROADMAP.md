# Completion roadmap — 3 members (checklist)

**Goal:** Finish the major project (documents-only artefact + report).  
**As of:** 2026-11-14  

**Roles (fill names):**

| Role | Name | Job |
|---|---|---|
| **Lead (Member A)** | _________________ | Main path — can do almost everything |
| **Side quest 1 (Member B)** | _________________ | Paper polish + sources/citations |
| **Side quest 2 (Member C)** | _________________ | Case-study evidence + second coding support |

**Pins (do not change without logging):**  
rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`

**End package you must have:**

1. Obligation register
2. Extended taxonomy
3. Cross-mapping matrix (human-validated)
4. Assessment rubric (tried on one real case)
5. Validation report (updated)
6. Final report/thesis (`paper/draft-manuscript.md` rewritten)

---

## Phase 0 — Align (Day 1, all three together) — ~1 hour

- [x] Read `RESEARCH_OVERVIEW.md` together (15 min)
- [x] Agree: end product = **5 artefacts + report**, not software / not MCP now
- [x] Fill names in the roles table above
- [x] Ask guide (if not done):  
  - [ ] Approve reconciliation (`mapping/reconciliation-record.md`)  
  - [ ] Is Delphi **required** or optional?  
  - [ ] Can we use a redacted audit / sample evidence pack for case study?
- [x] Create a shared folder note: “Guide said: _______________”

**Exit:** Everyone can say the one-sentence end product.

---

## Phase 1 — Human trust on the matrix (Days 1–3) — CRITICAL

### Lead (A) + Member C — **DONE 2026-11-14**

- [x] Blind sample coding: 10 CATs × `R-006-02`, `HDMP-27-05a`, `A-008-05`, `R-006-01`, `A-006-04`
- [x] Worksheets: `human-coder-A.md` (Surya), `human-coder-B.md` (Rahul)
- [x] Compare + adjudicate 4 disagreements → `human-sample-results.md`
- [x] Gap 1 unanimous N; matrix patched (158N / 12P / 0F)
- [ ] Mentor sign-off on human patches (esp. CAT-07 × R-006-01 F→Pp)

### Member B (side quest)

- [ ] Prepare “what we show guide” tab list (overview, matrix.md, gap1, human-sample-results)
- [ ] Write 5 bullet “progress since Review 1” for the final report intro

**Exit:** Sample dual-human coding done + Gap 1 undisputed. **→ Phase 2 case study next.**

---

## Phase 2 — Case study (Days 2–5) — CRITICAL

**Purpose:** Prove a developer/team can *use* register + matrix + rubric on real evidence.

### Member C (owns evidence pack) — **DONE 2026-11-14**

- [x] Evidence pack selected: **Bahmni India Distro HIP** (`openmrs-module-hip` + `hip-service`, MIT, public)
- [x] Indexed 10 files in `validation/case-study-evidence-index.md`
- [x] Public MIT — no redaction blocker

### Lead (A) + Member B — **DONE 2026-11-14**

- [x] Scorer A (Surya) + Scorer B (Rahul) completed
- [x] Compare adjudicated (88.9% raw agree)
- [x] Report written: `validation/case-study-report.md`
- [x] Validation report bumped to v0.3

**Exit:** Case study complete. **→ Phase 3 lock deliverables + Phase 4 paper polish.**

---

## Phase 3 — Lock deliverables 1–5 (Days 4–6)

### Lead (A)

- [ ] **Register:** skim all 18 rows; fix unclear wording only if needed (log changes; if meaning changes, note re-code impact)
- [ ] **Taxonomy:** confirm `extended-taxonomy.md` matches matrix findings
- [ ] **Matrix:** point final file = `main-matrix-reconciled.csv` (+ human sample note)
- [ ] **Rubric:** add 1 paragraph “how a developer uses this” (optional short `rubric/user-guide.md`)
- [ ] **Validation report:** update `validation/validation-report.md` with:  
  - human coding status  
  - case study done  
  - Delphi: skipped / scheduled / done (per guide)

### Member B

- [ ] Update `validation/coverage-ratio.md` if register unchanged (or note “unchanged”)
- [ ] Update `validation/project-status.md` checkboxes to current reality
- [ ] Update `RESEARCH_OVERVIEW.md` § pending → mark finished items

### Member C

- [ ] HDMP-16-04: leave as org-policy (default) unless guide wants rewrite  
- [ ] FHIR row: if easy, stamp exact profile note; else leave “partial” as already noted

**Exit:** All five deliverable files exist and status page says what’s final vs draft.

---

## Phase 4 — Final report / thesis (Days 5–8)

### Member B (owns paper polish) + Lead reviews

- [ ] Rewrite `paper/draft-manuscript.md` in **team voice** (remove “agent draft” tone)
- [ ] Keep counts exact: 170 cells, 156 N / 13 P / 1 F, Gap 1 = 20/20 N
- [ ] Keep scope line: pattern ≠ legal compliance
- [ ] κ: call it **exploratory** unless full human–human κ is computed
- [ ] Add Future work: “MCP / tooling possible later; out of scope for this project”
- [ ] Fix `paper/references.md` against `sources.md`
- [ ] Verify Bašić = **v4, 21 studies** everywhere

### Member C

- [ ] Proofread once for clarity (no jargon without explanation)
- [ ] Check all file links in manuscript appendix still work
- [ ] Prepare college submission format if required (PDF export, cover page, etc.)

### Lead (A)

- [ ] Final read of whole manuscript
- [ ] Decision log entry: “Project completion package frozen for submission”
- [ ] Sync public artefact repo if needed (no PDFs)

**Exit:** One submission-ready report + artefact folder.

---

## Phase 5 — Optional (only if guide requires)

### Delphi (Members B + C recruit, Lead runs analysis)

- [ ] Confirm guide said Delphi is mandatory
- [ ] Follow `validation/delphi/protocol.md`
- [ ] Round 1 → revise if needed → Round 2
- [ ] Add results into validation report

### Full 170 human dual coding (A + C)

- [ ] Only if guide rejects sample-only IRR
- [ ] Recompute κ; update validation report

### MCP (NONE of you during major project)

- [ ] Explicitly **do not build** now  
- [ ] One paragraph under Future work only

---

## Weekly standup questions (10 min)

1. What did A finish?
2. What did B finish?
3. What did C finish?
4. Blocked on guide?
5. What is the next single checkbox?

---

## Definition of Done (tick all)

- [ ] Guide OK with reconciliation (or written instruction to change cells)
- [ ] Human coding sample (or full) completed and logged
- [ ] Case study report exists with rubric scores
- [ ] Validation report updated
- [ ] Five deliverable files clearly identified
- [ ] Final manuscript in team voice, counts correct
- [ ] Sources/references consistent
- [ ] No claim of legal compliance; no WASA-keyed rows; no MCP as deliverable
- [ ] Team can demo: register → matrix → rubric → case-study scores in 10 minutes

---

## Who does what (cheat sheet)

| Task | A (Lead) | B | C |
|---|---|---|---|
| Guide meeting / reconciliation | Owner | Support | Support |
| Matrix human coding | Owner | — | Second coder |
| Case study scoring | Owner | Second rater | Evidence pack |
| Validation report update | Owner | Status/overview edits | — |
| Manuscript rewrite | Reviewer | **Owner** | Proofread |
| Citations / sources | Review | **Owner** | — |
| Delphi (if required) | Analysis | Recruit/forms | Recruit |
| MCP | Future only | Future only | Future only |

---

## Start tomorrow morning (first 5 checkboxes)

1. [ ] Fill names in roles table
2. [ ] All three read overview together
3. [ ] Message / meet guide on reconciliation + Delphi + case evidence
4. [ ] C starts evidence pack list
5. [ ] A + C schedule coding session for Gap 1 + sample columns

**Follow this file:** `validation/COMPLETION_ROADMAP.md`
