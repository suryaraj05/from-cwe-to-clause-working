# Completion roadmap — 3 members (checklist)

**Goal:** Finish the major project (documents-only artefact + report).  
**As of:** 2026-11-14 (Phase 3–4 in progress / locked artefacts)

**Roles (fill names):**

| Role | Name | Job |
|---|---|---|
| **Lead (Member A)** | Surya | Main path — can do almost everything |
| **Side quest 1 (Member B)** | _________________ | Paper polish + sources/citations |
| **Side quest 2 (Member C)** | Rahul | Case-study evidence + second coding support |

**Pins (do not change without logging):**  
rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`  
**Matrix pin:** `main-matrix-reconciled.csv` post human sample → **158 N / 12 P / 0 F**

**End package you must have:**

1. Obligation register — **locked MVP**
2. Extended taxonomy — **locked draft**
3. Cross-mapping matrix (human-validated sample) — **locked**
4. Assessment rubric (tried on Bahmni HIP) — **locked** + `rubric/user-guide.md`
5. Validation report (updated) — **v0.3**
6. Final report/thesis (`paper/draft-manuscript.md`) — **v0.2 Results updated**

---

## Phase 0 — Align (Day 1, all three together) — ~1 hour

- [x] Read `RESEARCH_OVERVIEW.md` together (15 min)
- [x] Agree: end product = **5 artefacts + report**, not software / not MCP now
- [x] Fill names in the roles table above
- [x] Ask guide (if not done):  
  - [ ] Approve reconciliation (`mapping/reconciliation-record.md`)  
  - [ ] Is Delphi **required** or optional?  
  - [x] Evidence pack: public Bahmni HIP (MIT) — used
- [x] Create a shared folder note: “Guide said: _______________”

**Exit:** Everyone can say the one-sentence end product. **Done.**

---

## Phase 1 — Human trust on the matrix (Days 1–3) — CRITICAL — **DONE**

### Lead (A) + Member C — **DONE 2026-11-14**

- [x] Blind sample coding: 10 CATs × `R-006-02`, `HDMP-27-05a`, `A-008-05`, `R-006-01`, `A-006-04`
- [x] Worksheets: `human-coder-A.md` (Surya), `human-coder-B.md` (Rahul)
- [x] Compare + adjudicate 4 disagreements → `human-sample-results.md`
- [x] Gap 1 unanimous N; matrix patched (158N / 12P / 0F)
- [ ] Mentor sign-off on human patches (esp. CAT-07 × R-006-01 F→Pp)

### Member B (side quest)

- [x] Prepare “what we show guide” tab list (overview, matrix.md, gap1, human-sample-results)
- [ ] Write 5 bullet “progress since Review 1” for the final report intro *(optional polish)*

**Exit:** Sample dual-human coding done + Gap 1 undisputed. **Met.**

---

## Phase 2 — Case study (Days 2–5) — CRITICAL — **DONE**

### Member C (owns evidence pack) — **DONE 2026-11-14**

- [x] Evidence pack: **Bahmni India Distro HIP** (`openmrs-module-hip` + `hip-service`, MIT, public)
- [x] Indexed 10 files in `validation/case-study-evidence-index.md`
- [x] Public MIT — no redaction blocker

### Lead (A) + Member B — **DONE 2026-11-14**

- [x] Scorer A (Surya) + Scorer B (Rahul) completed
- [x] Compare adjudicated (88.9% raw agree)
- [x] Report written: `validation/case-study-report.md`
- [x] Validation report bumped to v0.3

**Exit:** Case study complete. **Met.**

---

## Phase 3 — Lock deliverables 1–5 (Days 4–6) — **DONE 2026-11-14**

### Lead (A)

- [x] **Register:** skimmed; wording unchanged; pin remains `register-v0.3-mvp-2026-08-27`
- [x] **Taxonomy:** `extended-taxonomy.md` aligned with human matrix (CAT-07 × R-006-01 = Pp)
- [x] **Matrix:** final file = `main-matrix-reconciled.csv` (+ `human-sample-results.md`)
- [x] **Rubric:** `rubric/user-guide.md` added
- [x] **Validation report:** human coding + case study recorded; Delphi = optional / if guide requires

### Member B

- [x] `validation/coverage-ratio.md` updated for 158/12/0
- [x] `validation/project-status.md` current
- [x] `RESEARCH_OVERVIEW.md` pending → finished items marked

### Member C

- [x] HDMP-16-04: leave as org-policy (default)
- [x] FHIR row: leave partial stamp as already noted (no meaning change)

**Exit:** All five deliverable files exist and status page says what’s final vs draft. **Met.**

---

## Phase 4 — Final report / thesis (Days 5–8) — **IN PROGRESS**

### Member B (owns paper polish) + Lead reviews

- [x] Rewrite Results in `paper/draft-manuscript.md` + `paper/05-results.md` (team voice / current evidence)
- [x] Counts exact: **170 cells, 158 N / 12 P / 0 F**, Gap 1 = 20/20 N
- [x] Scope line: pattern ≠ legal compliance
- [x] κ: **exploratory** agent; human sample 92% primary trust signal
- [x] Future work: MCP / tooling later; out of scope
- [ ] Fix `paper/references.md` against `sources.md` *(remaining polish)*
- [x] Verify Bašić = **v4, 21 studies** in Results/abstract/conclusion

### Member C

- [ ] Proofread once for clarity
- [ ] Check all file links in manuscript appendix
- [ ] Prepare college submission format if required

### Lead (A)

- [x] Results + status consistency pass
- [x] Decision log: Phase 3–4 lock entry
- [ ] Sync public artefact repo after this pass

**Exit:** One submission-ready report + artefact folder — **pending mentor + final formatting**.

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

- [x] Explicitly **do not build** now  
- [x] One paragraph under Future work only

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
- [x] Human coding sample completed and logged
- [x] Case study report exists with rubric scores
- [x] Validation report updated
- [x] Five deliverable files clearly identified
- [ ] Final manuscript in team voice, counts correct *(Results done; full voice polish optional)*
- [ ] Sources/references consistent
- [x] No claim of legal compliance; no WASA-keyed rows; no MCP as deliverable
- [x] Team can demo: register → matrix → rubric → case-study scores in 10 minutes

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

**Follow this file:** `validation/COMPLETION_ROADMAP.md`
