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


---

# Governance refinement — HUMAN-01 / AG-PRI-01 / AG-MIS-02 / AG-GRK-03 / AG-CLD-04

## Final role matrix

| ID | Role | Non-overlapping responsibility | Primary deliverable |
|---|---|---|---|
| **HUMAN-01** | Point / Human Authority | Direction, acceptance, final truth | Accepted/rejected decisions |
| **AG-PRI-01** | Primary Reasoning & Execution | Implementation, exact-state verification, CI, evidence execution | Verified changes, CI/runtime evidence, gate transitions |
| **AG-MIS-02** | Forensic Falsifier | Attack a bounded claim | Falsification report |
| **AG-GRK-03** | Systems Architect | Examine composition and boundaries | Architecture/contradiction report |
| **AG-CLD-04** | Contract Auditor | Examine invariants and contract sufficiency | Contract/invariant report |

## Isolation rule

A collaborator may **identify** a problem inside another role's domain, but may not **own the resolution**.

Examples:

- Mistral may discover a persistence failure while falsifying a claim, but Claude owns the invariant analysis.
- Grok may notice a persistence composition issue, but Claude determines whether a required invariant exists.
- Claude may identify an architecture requirement implied by a contract, but AG-PRI-01 determines the minimal implementation.
- AG-PRI-01 may discover an issue during execution, but does not automatically convert execution output into an accepted contract.
- HUMAN-01 decides whether a proposed contract, implementation, or milestone is accepted.

## Verification rule

`agent report ≠ project evidence`

Promotion requires:

`candidate → exact-state reproduction → evidence classification → HUMAN-01 acceptance`

Runtime claims additionally require direct runtime evidence.

## Ledger separation

Each collaborator maintains:
- **finding ledger:** observations and candidate conclusions;
- **milestone ledger:** completed role-specific milestones;
- **promotion status:** whether the primary process has independently verified the entry.

The primary milestone/gate ledger is the only place where project-level gate transitions are recorded.

## Current decision

The multi-agent structure is now considered **methodology infrastructure**, not application architecture.

No collaborator is authorized to add itself, its framework, its model, or its workflow as a runtime dependency of SoulSyncMobile.
