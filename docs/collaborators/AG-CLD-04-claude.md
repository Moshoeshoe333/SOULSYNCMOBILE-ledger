# AG-CLD-04 — Claude Contracts / Methodology Ledger

**Role:** Contract, methodology, and external-research reviewer  
**AuthorityLevel:** NONE  
**Reconciliation authority:** HUMAN-01  
**Ledger status:** Candidate observations recorded; human acceptance remains required.

## 2026-10-02 — Current instructions and evidence boundary

### Verified current evidence

- The active product chain remains: typecheck → Semantic 33 → threat → storage → G-BOOT.
- Static/CI evidence is green at 47abf3b05b0848f1707720845a51e0b4f70dec57.
- Current EAS identity is configured at c7e05be1abd12f15bf93233276c4979376c8575e.
- The first EAS build submission produced build ID 126b7047-16a5-43b0-ad42-452ef2e0f0b8 from GitHub merge checkout SHA 7164963d315a6fedbb7cfdb03d0cdda6caf2809f.
- GitHub's waiter was cancelled; remote EAS terminal status is still unknown.
- G-BOOT is OPEN.
- The user-supplied X post referenced by prior research remains unverified because its raw content was not available; it must not be treated as evidence.
- The uv pilot remains a bounded, partially verified SoulSync 3.0 methodology experiment and does not justify changing SoulSyncMobile.
- MD-TEXT-001 was empirically strengthened by the historical Run #93 literal-escape corruption and its Run #96 correction.
- MD-TRACE-002 (Build Artifact Lineage) is a valid methodology candidate arising from the merge-SHA/EAS-build provenance distinction.

### Required Claude instruction

1. Continue to treat external posts, reviews, and agent reports as AuthorityLevel NONE until independently reproduced.
2. Do not turn external research into product architecture without a bounded work unit and an evidenced gap.
3. Maintain MD-TRACE-002 as methodology candidate: source branch/ref → source SHA → CI checkout SHA → submitted build ID → build result → artifact ID → artifact hash → installation witness.
4. Preserve MD-TEXT-001 as an active Semantic 33 control against source/documentation escape corruption.
5. Do not introduce an LLM, cloud classifier, agent authority, or new runtime dependency into SoulSyncMobile.
6. Do not reopen the persistence contract until the intended invariant is explicitly defined.
7. For every external claim, separate source observation, independent verification, interpretation, and adoption decision.
8. The active execution Point remains EAS remote-build result recovery; methodology work must not displace it.

## Gate instruction

**No architecture expansion. No premature code changes. No G-BOOT closure from static evidence.** Produce only evidence-bounded methodology deltas or contract questions that directly illuminate the current gate.

DISCOVERY ≠ AUTHORITY
RESEARCH ≠ REPOSITORY STATE
CI ≠ RUNTIME
