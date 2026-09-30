# Semantic 33 Typo Integrity Framework (TIF)

> **Status:** Methodology Delta / Step 0 specification
>
> **Scope:** documentation and verification integrity; Semantic 33 observations remain authority `NONE`.
>
> **Core rule:** a typo that changes an identifier, referent, contract, or truth claim is an integrity event, not merely a spelling defect.

## Purpose

TIF systematically classifies, catches, and reconciles structural, referential, and contextual string defects before they contaminate truth ledgers, repository references, or software boundaries.

TIF extends the existing Semantic 33 evidence-first methodology without creating a second threat engine.

## Three integrity tiers

| Tier | Layer | Invariant focus | Detection target |
|---|---|---|---|
| T1 | Structural | format, length, encoding | malformed SHA strings, zero-width characters, casing/format drift |
| T2 | Referential | binding truth, repository existence | nonexistent commits, dead paths, wrong tree references |
| T3 | Epistemic | claim/context alignment | ledger claims inconsistent with exact HEAD, runtime evidence, or gate state |

These tiers classify observations; they do not independently establish authority.

## Engineering integrity checks

| Check | Purpose |
|---|---|
| TIF-SHA-40 | SHA strings exactly 40 lowercase hexadecimal characters |
| TIF-ALLOWLIST | Changed harness paths reconciled against authorized paths |
| TIF-LEDGER-SHA | Referenced SHAs resolve to known Git objects/history |
| TIF-VOCAB | Semantic 33 classes remain canonical |
| TIF-NO-PROXY | Documentation cannot equate CI success with mobile runtime proof |

Checks should fail closed when a formal integrity invariant is violated.

## Error-ledger integration

### RC-06 — Transcription / typographic integrity

Cause: a human or tool alters an identifier, reference, path, or semantic class during transcription or prose editing.

Countermeasure: canonical identifiers are validated by machine equality/format checks rather than visual inspection.

### Permanent rule 13

> **Canonical identifiers (SHA, class names, allowlist paths, and other formal references) are validated by machine check, not by reading.**

## Verification pipeline

```
Markdown / source input
        ↓
Tier 1 — structural guard
        ↓
Tier 2 — Git/referent reconciler
        ↓
Tier 3 — epistemic alignment
        ↓
commit / verification
```

A successful lower tier does not imply success at a higher tier.

## Future implementation sequence

- Step 0 — specification only: DONE
- Step 1 — Semantic boundary correction: future
- Step 2 — additive signal shape: future
- Step 3 — protected-token observation: future
- Step 4 — engineering verifier: future
- Step 5 — differential integration: future

## Non-goals

- no full-English spellcheck
- no machine-learning typo detector
- no automatic correction
- no typo-derived ALLOW/WARN/DENY
- no new mobile UI
- no replacement of G-BOOT
- no CI command masquerading as Android runtime evidence

## Gate discipline

TIF is subordinate to the current evidence boundary.

The active product chain remains:

```
install → boot → input → analyze → visible decision
       → local record → restart → offline
```

TIF implementation must not interrupt that runtime evidence path unless a separately authorized minimal fix is required.

## Current status

**Step 0 only.**

No TIF implementation is claimed by this specification. No G-BOOT gate transition follows from this document.
