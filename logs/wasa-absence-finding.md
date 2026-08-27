# Finding: No public official WASA specification

**Status:** Reported finding (object of study), not a register instrument.  
**Date opened:** 2026-08-27  
**Decision:** WASA reclassified from primary source → object of study. No register row may be keyed to WASA.

## Claim
The security assessment regime that gates (or is said to gate) production access to India’s national health data infrastructure under the WASA label has **no publicly available official NHA/ABDM specification** that we can cite clause-by-clause, as of the retrieval date in `sources.md` (X01).

## What we do instead (re-sourcing)
| Imagined WASA-derived theme | Public instrument to use instead | `sources.md` |
|---|---|---|
| Security-assessment scope / OWASP-shaped web weaknesses | OWASP Top 10 (edition pinned when cited) | S01 |
| Security-by-design / access-logging (health data policy) | ABDM Health Data Management Policy | R06 |
| Independent auditor / empanelment requirement | CERT-In empanelment listings (retrieve before any register row) | *(pending source ID)* |

## Paper placement
Dedicated short subsection on **regulatory transparency** (results or standalone findings), **not** only in threats to validity.

## Reversal condition
If an official NHA milestone or certification guideline is published and retrieved, reopen this decision, add the document to `sources.md`, and log the reversal in `logs/decision-log.md`.
