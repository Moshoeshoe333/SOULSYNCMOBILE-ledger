# AG-GRK-03 — Grok Architecture / Provenance Ledger

**Role:** Independent architecture and provenance reviewer  
**AuthorityLevel:** NONE  
**Reconciliation authority:** HUMAN-01  
**Ledger status:** Candidate observations recorded; human acceptance remains required.

## 2026-10-02 — Build provenance reconciliation

### Verified current evidence

- PR #12 head is c7e05be1abd12f15bf93233276c4979376c8575e.
- The first EAS workflow did not build that head directly.
- GitHub's actual checkout was merge SHA 7164963d315a6fedbb7cfdb03d0cdda6caf2809f.
- The remote EAS build ID created by that execution is 126b7047-16a5-43b0-ad42-452ef2e0f0b8.
- GitHub waiter/job 110420957901 and run 36877608931 ended cancelled after the configured approximately 60-minute wait.
- The logs show EAS credential acceptance, Android keystore creation, project upload, build submission, and then waiting.
- The logs do not establish the terminal state of the remote EAS build.
- GitHub artifact count is zero.
- APK, artifact hash, installation, and runtime evidence remain unknown.
- The workflow name “Checkout exact PR merge ref” was directionally accurate in practice, but the workflow used bare checkout and only recorded the resulting SHA. Future provenance must explicitly bind the intended source ref to the actual checkout SHA.

### Required Grok instruction

1. Maintain the distinction between PR head SHA, GitHub merge SHA, and EAS build source SHA.
2. Do not infer build success/failure from GitHub waiter cancellation.
3. First recover/inspect the remote EAS build record for 126b7047-16a5-43b0-ad42-452ef2e0f0b8; do not trigger a replacement build before this is resolved.
4. If a workflow correction becomes necessary, propose the smallest provenance-only change that explicitly records the source policy and actual checkout SHA.
5. Do not modify application code, storage contracts, threat heuristics, or G-BOOT semantics.
6. Preserve the lineage as: PR head c7e05be → PR merge 7164963d → EAS build 126b7047...
7. Any artifact claim must bind build ID, source/checkout SHA, artifact identifier, and artifact hash before being promoted.
8. HUMAN-01 remains the only acceptance authority.

## Gate instruction

**Current gate remains OPEN.** The next Point is remote EAS build-result recovery, followed only if necessary by a minimal provenance correction.

BUILD SUBMISSION ≠ BUILD COMPLETION ≠ APK ≠ INSTALLATION ≠ G-BOOT


## Addendum — 2026-10-02 remote-build inspection attempt

A bounded inspection workflow was created on forensic/wu-eas-remote-status-001 and PR #14, targeting existing EAS build 126b7047-16a5-43b0-ad42-452ef2e0f0b8. It pins checkout to the PR head for the inspection and would run eas build:view using EXPO_TOKEN. No new EAS build was submitted. No workflow execution was observed through the available GitHub execution interface, so the remote EAS terminal result remains UNKNOWN.

**Instruction:** do not convert tool-access limitation into a build-state claim. The next valid evidence is an authenticated EAS build:view result for the exact build ID.
