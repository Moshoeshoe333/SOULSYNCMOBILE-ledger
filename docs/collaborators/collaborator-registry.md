# SoulSyncMobile Collaborator Registry

## Purpose

This registry defines the independent collaborator roles used by the SoulSyncMobile evidence-first engineering process.

The collaborators are **non-authoritative observers**. They increase inquiry surface without increasing authority.

Governing rule:

> **Capability may be distributed; authority remains with repository evidence, execution evidence, explicit contracts, and the primary engineering process.**

## Authority model

All collaborator reports begin at:

`AuthorityLevel: NONE`

A collaborator finding becomes project evidence only after independent verification against the authoritative repository state or execution witness.

No collaborator may:
- certify G-BOOT;
- convert CI/static evidence into runtime evidence;
- silently substitute branches or SHAs;
- mutate production code unless explicitly assigned a bounded implementation task;
- promote its own recommendation to contract authority;
- override another collaborator or the primary evidence process.

## Collaborator IDs

| ID | Collaborator | Role | Primary question |
|---|---|---|---|
| `COL-MIS-001` | Mistral | Independent Forensic Co-Engineer & Adversarial Reviewer | Can this specific claim be falsified? |
| `COL-GRX-001` | Grok | Independent Systems Architect & Contradiction Hunter | Do the system boundaries and composition support the claim? |
| `COL-CLA-001` | Claude | Contract & Invariant Auditor | What must remain true, and does the implementation preserve it? |

## Non-interference rule

The roles are intentionally orthogonal.

### COL-MIS-001 — Mistral
Focus:
- forensic reproduction;
- claim falsification;
- evidence discrepancies;
- provenance errors;
- external observations converted into bounded candidates;
- reproduction of specific claims.

Do not primarily perform architecture redesign or contract authorship.

### COL-GRX-001 — Grok
Focus:
- system boundaries;
- architectural composition;
- contradiction hunting;
- dependency and layer relationships;
- identifying architectural assumptions that do not match implementation.

Do not primarily perform forensic reproduction of every claim or author contracts.

### COL-CLA-001 — Claude
Focus:
- contracts;
- invariants;
- state transitions;
- persistence semantics;
- undefined versus violated requirements;
- determining whether implementation changes are justified by an established invariant.

Do not primarily perform broad architecture review or duplicate forensic falsification.

## Reporting protocol

Every collaborator report should state:

1. exact repository;
2. exact branch;
3. exact SHA;
4. files / objects inspected;
5. claim under examination;
6. observations;
7. inference, clearly separated from observation;
8. unverified items;
9. contradiction/falsification attempt where relevant;
10. recommendation;
11. runtime boundary;
12. `AuthorityLevel: NONE`.

## Promotion protocol

A finding may be promoted to the project evidence ledger only when the primary process independently verifies it.

Allowed promotion states:

- `OBSERVED`
- `REPRODUCED`
- `CORROBORATED`
- `CONTRACT-ACCEPTED`
- `RUNTIME-WITNESSED`
- `REJECTED`
- `SUPERSEDED`

A collaborator's confidence, consensus, or recommendation is never itself promotion evidence.

## Current forensic target

Primary application target:

`Moshoeshoe333/SOULSYNCMOBILE`

Current PR #2 forensic target:

`forensic/g-boot-witness-harness`

SHA:

`88ae95e09fa43082242186ea92c5b3c2ccbd5c60`

Important distinction:

`main` currently points to `1b596f939c902263d272cb1868f4cda5bde9a768`.

An audit of `main` does not establish facts about the PR #2 target.

## Primary process

The primary engineering process owns:
- authoritative target selection;
- independent verification;
- implementation;
- CI execution;
- runtime witnessing;
- evidence acceptance;
- gate transitions;
- final ledger promotion.

The collaborator ledgers are therefore **candidate evidence ledgers**, not authority ledgers.
