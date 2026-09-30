# Methodology Delta

## Governing rule

External engineering systems are sources of patterns, not architectures to copy.

For SoulSyncMobile:

```
discovery → deterministic reproduction → policy/contract check → fixture → CI witness → runtime evidence → accepted evidence
```

**Discovery can be autonomous; authority cannot be autonomous.**

## MD-SWARM-001 — Bounded autonomous corpus mining

**Status:** Adopted as methodology only; no production implementation.

Use bounded autonomous/parallel analysis to expand and interrogate evidence corpora while keeping:

1. discovery,
2. validation, and
3. product execution

as separate epistemic layers.

Proposed upstream pipeline:

```
public scam corpus
→ agent preprocessing
→ normalization/deduplication
→ candidate threat patterns
→ Semantic 33 observation
→ policy mapping
→ fixture proposal
→ human/deterministic review
→ THREAT_FIXTURES
```

Agents must not directly modify the production threat engine, grant authority, or become a cloud dependency of the offline mobile product.

## MD-GBOOT-001 — Evidence-producing runtime boundary

The G-BOOT harness may structure and bind observations to repository/device/evidence metadata, but an invocation must never manufacture the runtime observation it purports to witness.

CI validates the harness and prerequisite chain; it does not substitute for mobile runtime evidence.

## MD-001 — Minimal-change execution discipline

For discovered failures:

```
FAILURE
→ MINIMAL FIX
→ DIFF AUDIT
→ INVARIANT AUDIT
→ EXECUTION
```

No broad refactor is justified merely because a narrow boundary was found.

## OpenSRE-derived engineering patterns

The useful extraction is limited to:

- deterministic execution boundaries,
- explicit evidence/transcript handling,
- reproducibility,
- observable state transitions,
- bounded automation,
- separation of investigation from authority.

OpenSRE architecture, cloud orchestration, agent swarms, or runtime dependencies are not being imported into SoulSyncMobile.

## Current application boundary

Application repository: `Moshoeshoe333/SOULSYNCMOBILE`

Evaluation surface remains the forensic G-BOOT witness lineage. Runtime evidence remains separate from CI evidence.
