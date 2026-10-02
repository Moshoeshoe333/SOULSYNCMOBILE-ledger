# SoulSyncMobile Collaborator Ledger Registry

## Governing authority

- HUMAN-01 is the acceptance and gate-promotion authority.
- Secondary collaborators have AuthorityLevel NONE.
- A collaborator observation becomes authoritative only after independent repository/execution verification and HUMAN-01 reconciliation.

## Designated ledgers

| ID | Collaborator | Designated ledger | Primary responsibility |
|---|---|---|---|
| AG-MIS-02 | Mistral | docs/collaborators/AG-MIS-02-mistral.md | forensic state and contract review |
| AG-GRK-03 | Grok | docs/collaborators/AG-GRK-03-grok.md | architecture/provenance review |
| AG-CLD-04 | Claude | docs/collaborators/AG-CLD-04-claude.md | methodology/contracts/external-source hygiene |
| AG-PRI-01 | Primary / HUMAN-01 | docs/collaborators/AG-PRI-01-primary-human.md | milestone reconciliation and acceptance |

## Cross-collaborator instructions

1. Do not promote an external review, post, model output, or agent assertion to repository truth without independent verification.
2. Preserve exact repository SHA, branch/ref, workflow/run ID, job ID, build ID, artifact ID, and hash whenever applicable.
3. Distinguish expected state from observed state.
4. Distinguish CI/static evidence from remote build evidence and physical runtime evidence.
5. Do not modify application code merely to resolve an analytical disagreement.
6. The active execution Point is WU-EAS-APK-002: recover the terminal state of EAS build 126b7047-16a5-43b0-ad42-452ef2e0f0b8 before any replacement build.
7. G-BOOT remains OPEN.
8. Candidate observations remain AuthorityLevel NONE until HUMAN-01 reconciliation.

## Current lineage

PR head c7e05be1abd12f15bf93233276c4979376c8575e
→ PR merge SHA 7164963d315a6fedbb7cfdb03d0cdda6caf2809f
→ EAS build 126b7047-16a5-43b0-ad42-452ef2e0f0b8
→ remote build result UNKNOWN
→ APK UNKNOWN
→ installation UNKNOWN
→ G-BOOT OPEN

> Strength of a claim must never exceed strength of evidence.
