# SoulSyncMobile Forensic Ledger

Independent evidence and methodology repository for `Moshoeshoe333/SOULSYNCMOBILE`.

## Purpose

This repository preserves the forensic memory of SoulSyncMobile without modifying the application repository's runtime tree.

The governing method is:

```
repository state → execution evidence → interpretation → gate transition
```

**Claim strength ≤ evidence strength.**

## Repository boundary

- `SOULSYNCMOBILE`: application source, tests, CI, G-BOOT witness harness, and runtime evidence.
- `SOULSYNCMOBILE-ledger`: milestones, errors, TIF, methodology deltas, and cross-repository evidence references.

A ledger update must not be treated as an application change.

## Authoritative relationship

Ledger records reference the application repository by exact commit SHA, workflow/run identity, branch/ref, and artifact identity where available.

Current known application evaluation surface:

- Repository: `Moshoeshoe333/SOULSYNCMOBILE`
- Latest CI-witnessed PR head: `bf57a67c23dd51e57ae660795f401c8dd7151010`
- Audited application baseline: `88afab23a043c08535c424247eb50bbabe27863f`
- Latest witnessed CI: Run #70, run ID `36706884385`, job `109859111647`

G-BOOT remains open until actual mobile runtime evidence exists.

## Anti-saturation rule

When runtime evidence is missing, documentation expansion is non-blocking and must not displace the next physical evidence boundary.

**Runtime evidence has priority over ledger expansion.**
