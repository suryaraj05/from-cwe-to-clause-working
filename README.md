# Repository map (markdown-first research artifact)

All paths relative to `project/`. **PDFs live under `docs/` for evidence; every deliverable and working product is Markdown (or CSV tables that are human-editable).** No application code.

```
project/
  README.md                          ← this file
  PROJECT_BRIEF.md                   ← standing instructions + scope
  sources.md                         ← master source manifest (version + retrieval date)

  docs/                              ← primary sources (gitignored PDFs OK)
    papers/                          ← base + method + empirical PDFs
    regulatory/                      ← DPDP / ABDM / NRCeS PDFs
    standards/                       ← OWASP / CWE / FHIR landing snapshots
    README.md                        ← how to cite local files; WASA note

  register/                          ← Deliverable 1 (working + frozen)
    SCHEMA.md                        ← column definitions (normative)
    obligation-register.md           ← living register (tables)
    coding-protocol.md               ← how we decompose a clause (GuideMe-adapted)
    CHANGELOG.md                     ← row-level change history

  taxonomy/                          ← Deliverable 2
    extended-taxonomy.md             ← ten Bašić categories + obligation dimensions
    nickerson-ending-conditions.md   ← checklist against Nickerson criteria
    dimension-definitions.md         ← consent architecture, purpose binding, …

  mapping/                           ← Deliverable 3
    cross-mapping-matrix.md          ← rows × columns + cell justifications
    not-visible-cells.md             ← headline “not visible” catalogue

  rubric/                            ← Deliverable 4
    assessment-rubric.md             ← questions, 3-level anchors, required evidence
    scoring-protocol.md              ← how raters apply the rubric

  validation/                        ← Deliverable 5
    validation-plan.md
    coverage-ratio.md
    inter-rater.md                   ← kappa + disagreement analysis (links to logs)
    delphi/                          ← round protocols + results (documents only)
    case-study.md                    ← hospital audit report application (documentary)

  paper/                             ← manuscript in paper shape from day one
    00-abstract.md
    01-introduction.md
    02-background-related-work.md
    03-method.md
    04-artifact.md
    05-results.md
    06-threats-to-validity.md
    07-conclusion.md
    references.md

  logs/
    decision-log.md
    citation-ledger.md
    disagreement-record.md
    wasa-absence-finding.md
```

## Method → file correspondence (citation integrity)

| Method we cite | Visible output of ours |
|---|---|
| GuideMe (Ayala-Rivera & Pasquale) | `register/coding-protocol.md` + `register/obligation-register.md` |
| Nickerson et al. | `taxonomy/extended-taxonomy.md` + `taxonomy/nickerson-ending-conditions.md` |
| Hevner et al. | Whole artifact set + `validation/` evaluation design |
| Bašić & Giaretta | Input rows of taxonomy + mapping matrix |
| Vibe-coded insecurity preprint | Related-work boundary + AI-specific patterns in discussion |

If a citation has no corresponding file, drop the citation.

## What is deliberately absent
- No `src/`, notebooks, scripts, or tooling.
- No WASA-keyed register until a public primary specification exists.
