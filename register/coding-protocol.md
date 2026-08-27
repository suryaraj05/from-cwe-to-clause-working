# Coding protocol (GuideMe-adapted) — draft

GuideMe (Ayala-Rivera & Pasquale, RE 2018) converts regulatory text into a catalogue of privacy controls in six steps. We adapt that pipeline to **DPDP + ABDM** and to criteria that are **observable as compliant patterns** in healthcare patient-data modules (documentary assessment only).

## Steps (to be refined against the GuideMe PDF before freeze)

1. **Select source unit** — one section/rule/clause from a document in `sources.md`.
2. **Quote** — copy verbatim into `quoted_obligation`; record `pdf_locus`.
3. **Identify actor and normative force** — who must do what (`shall` / `may` / `shall_not`).
4. **Decompose** — split compound sentences into atomic observables (one row each).
5. **Derive criterion + assessment question + evidence** — pattern-level, not organizational process.
6. **Tag dimensions + commencement** — taxonomy dimensions; Rules/Act tranche from primary commencement text.
7. **Dual code** — second coder independently; disagreements go to `logs/disagreement-record.md` with both originals kept.

## Hard stops

- No clause ID from memory.
- No WASA-keyed rows.
- No inventing numeric SLAs where the statute says “reasonable time.”
- If the next step seems to need running code or generating code samples: **stop** and raise it in the decision log instead.
