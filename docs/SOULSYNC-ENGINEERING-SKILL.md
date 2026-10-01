# SoulSync Engineering Skill — Execution & Evidence Protocol

## Purpose

Provide one canonical, bounded execution protocol for engineering work on SoulSyncMobile.

This file is a methodology control, not an application runtime dependency and not an autonomous authority system.

## Governing rule

```
claim
→ authoritative state
→ bounded evaluator
→ execution
→ raw evidence
→ classification
→ accepted transition
```

**Claim strength must not exceed evidence strength.**

## 1. Establish the target

Before meaningful work:

1. identify repository;
2. identify branch/ref;
3. verify exact SHA;
4. identify applicable contract/spec;
5. identify current gate/milestone;
6. check collaborator ledgers;
7. identify existing evidence and its authority level.

Never silently substitute a branch, SHA, clone, sandbox, or generated state.

## 2. Classify the requested work

Determine whether the task is:

- observation/research;
- contract clarification;
- documentation/methodology;
- bounded implementation;
- verification;
- runtime witnessing;
- gate preparation.

Do not convert research directly into product architecture.

## 3. Map before modifying

Record:

- authoritative files;
- relevant interfaces;
- invariants;
- current tests/fixtures;
- known failure modes;
- expected evidence;
- explicit non-goals.

If the contract is unresolved and implementation choice depends on it, stop at the contract boundary.

## 4. Make the smallest bounded change

For an evidenced defect:

```
FAILURE
→ MINIMAL FIX
→ DIFF AUDIT
→ INVARIANT AUDIT
→ EXECUTION
```

Do not refactor adjacent architecture without an evidenced need.

## 5. Evaluate the actual boundary

Prefer the evaluator that exercises the interface being claimed.

Examples:

- TypeScript claim → typecheck;
- threat-policy claim → Semantic 33 + threat fixtures;
- persistence-shape claim → storage validation/tests;
- mobile visibility claim → G-BOOT visible-decision;
- restart durability claim → G-BOOT restart;
- offline claim → G-BOOT offline.

A proxy test may support a narrower claim but must not be promoted to a broader one.

## 6. Preserve expected vs observed

Always distinguish:

```
EXPECTED = contract/fixture input
OBSERVED = execution output
```

Never populate an observed runtime field from an expected value merely because the expected behavior is known.

## 7. Protect evaluator integrity

The evaluator must not be silently changed to make the subject pass.

Check for:

- modified test/evaluator logic;
- fixture drift;
- wrong repository/ref;
- stale CI;
- uncommitted or untracked state;
- generated native state;
- environment substitution;
- harness self-reporting without direct observation.

If evaluator integrity is uncertain, downgrade the evidence classification.

## 8. Audit after execution

After a change:

1. verify exact resulting SHA;
2. inspect diff;
3. audit invariants;
4. inspect execution result;
5. preserve raw evidence identifiers;
6. classify observation vs inference vs recommendation;
7. update the relevant ledger;
8. determine whether the gate actually moved.

## 9. Promotion states

Use:

```
CANDIDATE
OBSERVED
REPRODUCED
CORROBORATED
CONTRACT-ACCEPTED
RUNTIME-WITNESSED
REJECTED
SUPERSEDED
```

Collaborator agreement is corroboration, not authority.

## 10. Runtime boundary

G-BOOT remains the direct mobile-runtime evidence boundary:

```
install
→ boot
→ input
→ analyze
→ visible-decision
→ local-record
→ restart
→ offline
```

CI may validate prerequisites and harness integrity, but it cannot manufacture or substitute for these observations.

## 11. Research intake

External research follows:

```
source
→ observation
→ transferable pattern
→ methodology candidate
→ exact project-gap check
→ bounded adoption or rejection
```

No external benchmark result becomes a SoulSyncMobile claim without SoulSync-specific evidence.

## 12. Human authority

```
agent proposal
≠
engineering truth
```

Normative choices remain with HUMAN-01 where the project governance requires human acceptance.

## Non-goals

This skill does not authorize:

- autonomous production-code modification;
- cloud dependency in the offline product;
- LLM authority over ALLOW/WARN/DENY;
- runtime evidence fabrication;
- aggregate “quality scores” as substitutes for gate evidence;
- architecture expansion merely because a tool or research paper suggests it.
