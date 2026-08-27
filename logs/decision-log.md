# Decision log

| Date | Decision | Rationale | Sources |
|---|---|---|---|
| 2026-08-27 | Create folder tree + download primary sources before drafting register | Clause numbers must come from local gazette PDFs | `sources.md` |
| 2026-08-27 | Use Bašić & Giaretta **arXiv v4** (17 Mar 2026) | Title and study counts changed across versions | P01 |
| 2026-08-27 | Do not create WASA-keyed register rows | No public official WASA specification found | X01 |
| 2026-08-27 | Add `commencement_status` to register from day one | DPDP Rules/Act commence in stages (publication / +1y / +18m) | R03, R05 |
| 2026-08-27 | Adopt markdown-first tree in `README.md`; register schema in `register/SCHEMA.md` | Mentor: documents only; GuideMe/Nickerson/Hevner each need a visible file | PROJECT_BRIEF |
| 2026-08-27 | Example register rows use Act s.6(1), Rules r.3(b), Act s.6(4)/(6) with `clause_id_verified=false` | Quotes from retrieved text; local PDF page check still required; Example 3 must be split before dual coding | R01, R03 |
| 2026-08-27 | Treat “~20 studies” in brief as to-verify against arXiv v4 PDF | Version drift risk; citation integrity | P01 |
| 2026-08-27 | Primary sources list in brief mentioned WASA — overridden | Public WASA spec absent; keep as finding not register source | X01 |
| 2026-08-27 | **WASA reclassified:** object of study, not primary source; no WASA-keyed rows; re-source to OWASP / ABDM HDMP / CERT-In; dedicated transparency subsection; reopen if official NHA text appears | Team assent (point 1) | X01, S01, R06 |
| 2026-08-27 | **Study count:** cite only arXiv:2412.15004**v4**; number enters drafts only after read off local PDF; record count in sources.md when read | Team assent (point 2); version pin load-bearing | P01 |
| 2026-08-27 | **Commencement modelling:** separate Act (843(E)) vs Rules (r.1) columns; `effective_from` only after both read; unverified cells show `unverified — pending G.S.R. 843(E)` (not blank) | Team assent (point 3) | R03, R05; SCHEMA |
| 2026-08-27 | **Matrix emptiness is not a success criterion.** Freeze operational cell-coding rule before any cell coding; dual-code; report kappa; Gap 1 wording follows counts. Prefer partial over not_visible when imprecise. | Team assent (point 4, amended) | `mapping/cell-coding-rule.md` |
| 2026-08-27 | Cell-coding rule written as **PROPOSED FOR FREEZE** — no cells coded until both coders assent and this log marks FROZEN | Point 4 next step | `mapping/cell-coding-rule.md` |
| 2026-08-27 | Cell-coding rule **approved in principle with 7 amendments**; status → `v0.2-amended-unfrozen`; **still not frozen** | Counterfactual RCM; underspecified flag; partial sub-flags; closed legal-concept list; pre-freeze pilot; weighted kappa; register version pin | `mapping/cell-coding-rule.md`, `imported-legal-concepts.md`, `register/VERSION.md` |
| 2026-08-27 | Primary IRR = linearly weighted kappa; report unweighted alongside | Ordinal verdicts | `validation/inter-rater.md` |
| 2026-08-27 | Standing: freeze pins rule version + register version + hash; criterion reword after pin → log re-code need | Amendment 7 | `register/VERSION.md` |
| 2026-08-27 | **Category profiles** extracted from Bašić v4 §4/Table 3; study count **21**; OWASP lines marked provisional (not in Bašić) | Blocks undefined row vocabulary | `taxonomy/category-profiles.md` |
| 2026-08-27 | **G.S.R. 843(E) read** from local PDF; Act commencement lookup filled; Rules r.1 schedule recorded; MVP register commencement populated | Point 2 | `register/commencement-lookup.md`, `obligation-register.md` v0.2 |
| 2026-08-27 | MVP register **15 criteria** spanning consent/notice, security, breach, retention, localization, ABDM cl.16.4 | Pilot corpus | `register-v0.2-mvp` |
| 2026-08-27 | Method section drafted; WASA transparency finding written as paper subsection | Parallel work | `paper/03-method.md`, `paper/findings-wasa-transparency.md` |
| 2026-08-27 | CERT-In empanelment added as S04 | WASA re-sourcing | `sources.md` |
| 2026-08-27 | **Logging Gap 1 evidenced** in Bašić v4 (no CWE-778/779/223/532/1295; no topical “logging”); CWE-117 only | PDF-verified | `paper/findings-logging-gap1.md` |
| 2026-08-27 | Add dimension `access_logging_demonstrability`; tag R-006-02; closed-list capability note; CAT-10 trap; pilot P10/P11; ABDM FHIR+15.4+27.5a → register v0.3 | Pre-pilot review | register, taxonomy, mapping, pilot |
| 2026-08-27 | Kappa measures agreement not correctness — shared wrong intuitions (logs=files; CWE-117=logging) | ToV | `paper/06-threats-to-validity.md` |
| 2026-08-27 | Split repos: private working (with PDFs); public artifact without third-party PDFs | Copyright / citation hygiene | GitHub |
| 2026-08-27 | Page-stamped Act/Rules/HDMP loci (`register/page-stamps.md`) | Pre-pilot | local PDFs |
| 2026-08-27 | Pilot stress-test 13 cells (`pilot-worksheet.md`); P05 expectation miss; P12 underspec confirmed | Instrument test | mapping |
| 2026-08-27 | Folded real defect: removed “logging” as example shared observable in partial test | Contradicted capability note | `cell-coding-rule` |
| 2026-08-27 | **FROZE** cell-coding-rule **v0.3-frozen**; pin register-v0.3-mvp + cat-profiles-v0.1; pilot handling **A**; SHA-256 `904b24b50e35fdbbe9b58b72b2f23e82b1ba6be742b8ec547ea3277b4e757eb8`; main dual-coding still required for kappa | User authorized next items | `mapping/cell-coding-rule.md` |
| 2026-08-27 | **Main dual coding complete** (170 cells); pilot handling A (12 excluded); linearly weighted κ = **0.949** (*n*=158); 1 non-pilot disagreement (CAT-06×A-006-04); reconciliation pending; logging columns N/N undisputed | User authorized main pass | `mapping/main-matrix.md`, `main-matrix-dual.csv`, `main-matrix-kappa.json` |
| 2026-08-27 | **Reconciliation complete** (5 cells); consensus 156N / 13Pp / 1F; Gap-1 logging 20/20 N; human second-coder + mentor review still required | User: agent work vs human work split | `main-matrix-reconciled.csv`, `reconciliation-record.md`, `validation/human-next-steps.md` |
| 2026-08-27 | **Agent completion pass (team unavailable):** rubric, extended taxonomy, Nickerson checklist, validation plan/report, coverage ratio, Delphi/case protocols, paper drafts 00–07 + references | User: complete what AI can | `validation/project-status.md`, `rubric/`, `taxonomy/extended-taxonomy.md`, `paper/` |
| 2026-08-27 | **Integrated manuscript** `paper/draft-manuscript.md` v0.1 — single read-through draft for thesis; section splits retained | User: best agent deliverable | `paper/draft-manuscript.md`, `paper/README.md` |
