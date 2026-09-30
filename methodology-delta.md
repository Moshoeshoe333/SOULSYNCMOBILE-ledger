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

## MD-002 — Engineering seriousness vs product maturity

**Working thesis:** SoulSyncMobile is a serious, evidence-driven experimental engineering effort progressing toward product maturity, rather than a finished public product.

This thesis deliberately separates:

- **engineering seriousness** — supported by observed repository structure, typed contracts, CI witnesses, deterministic fixtures, forensic harnessing, explicit gates, and error tracking;
- **experimental status** — supported by the evolving architecture/methodology and unresolved runtime boundary;
- **product maturity** — not established merely by successful CI or static analysis.

The repository currently supports claims of substantial engineering activity and witnessed CI/Semantic/fixture execution. It does **not** yet support a claim of production readiness because mobile runtime execution and G-BOOT evidence remain open.

The term **solo** should remain qualified as “appears primarily developed by one contributor” unless contributor-history evidence is explicitly audited. Contribution concentration is descriptive; it is not itself a quality judgment.

The appropriate maturity question is therefore:

```
not: “Does the repository look like a finished app?”
but:
“Which product claims have earned direct execution evidence?”
```


## MD-GENREC-001 — Context engineering without authority substitution

**Status:** Adopted as methodology only; no LLM runtime or recommendation architecture is being added to SoulSyncMobile.

External research source: Netflix, *GenRec: An LLM-Backed Recommendation Ranker at Netflix*, arXiv:2608.10257v2 (21 Aug 2026). The paper describes a shift from extensive hand-engineered recommendation features toward verbalized context, context engineering, catalog-aware scoring, reward-weighted post-training, and cost-constrained prefill-only serving. Its empirical claims are specific to Netflix recommendation ranking and are not evidence that the same architecture improves threat detection.

The transferable engineering pattern for SoulSyncMobile is narrower:

1. **Context before feature proliferation.** Before adding another brittle keyword/regex rule, ask whether the relevant evidence can be represented as a bounded, structured context object whose fields are explicitly defined and testable.
2. **Closed-world outputs.** Threat decisions should remain constrained to an explicit decision vocabulary and policy contract. Open-ended generation must never become an authority path.
3. **Signal budgeting.** Prefer high-signal, provenance-bearing observations over accumulating redundant or low-value context. Context reduction is a methodology question, not permission to discard evidence silently.
4. **Separate understanding from authority.** Any future contextual/LLM-assisted analysis may propose observations or fixture candidates, but deterministic policy contracts and witnessed execution remain the authority boundary.
5. **Measure before replacing.** GenRec's results come from controlled offline/online evaluation against a production baseline. SoulSyncMobile must not infer equivalent benefit without its own corpus, fixtures, deterministic comparisons, and runtime evidence.

This yields a bounded design rule:

```
raw input
→ normalized evidence
→ bounded contextual representation
→ Semantic 33 observation
→ deterministic policy evaluation
→ closed decision vocabulary
→ witnessed runtime behavior
```

**Explicit non-adoption:** no LLM classifier, prompt-driven ALLOW/WARN/DENY, catalog-style scoring head, cloud inference, autonomous production-code modification, or replacement of Semantic 33 with generative inference is authorized by this delta.

The immediate application is therefore **context-schema research only**, after the active E-008 and G-BOOT boundaries are resolved. This delta must not interrupt the active execution chain.


## MD-TOOLCHAIN-001 — Evidence-first engineering loop

**Status:** Adopted as methodology only; no external toolchain is being imported into the mobile runtime.

The supplied engineering loop is useful as a refinement of the existing evidence discipline:

```
capture task
→ map authoritative code/state
→ select bounded tool
→ test the actual interface
→ scan the change
→ run the pipeline
→ inspect evidence/trace
→ improve the next attempt
```

The transferable patterns are:

1. **Map before modify.** Repository structure, exact refs, contracts, and current execution witnesses are established before proposing a change.
2. **Structural inspection where it adds signal.** AST-aware search may be used for repository audits when text search is insufficient; it is an analysis aid, not a new threat classifier.
3. **Interface testing over proxy testing.** Tests should exercise the actual boundary being claimed. A static/CI result must not be represented as mobile-runtime evidence.
4. **Change scanning as a separate control.** Secret, dependency, configuration, and infrastructure scanning may be evaluated as independent verification layers. A scan result does not establish application correctness.
5. **Reproducible pipeline execution.** Local/containerized pipeline tooling may be evaluated later to reduce environment drift, but only if its behavior can be reconciled with the authoritative CI pipeline.
6. **Trace/evidence inspection.** Observability should preserve what actually happened without converting telemetry into authority.
7. **Tool minimization.** A tool is adopted only when a demonstrated gap exists that it closes better than the existing deterministic mechanism.

### Bounded candidate applications

| Pattern | Candidate use | Current decision |
|---|---|---|
| Beads / Git Town / GitButler | task and branch-state management | methodology reference only |
| Repomix | reproducible context snapshot before large audits | candidate offline aid |
| Serena / ast-grep | semantic/structural code navigation | candidate audit aid |
| ToolHive / MCP Inspector / Steel / Midscene | external-system/browser integration | defer; not required for current gate |
| Bruno | explicit interface/request collections | defer unless an external interface is introduced |
| Gitleaks | repository secret scanning | candidate independent CI hygiene control |
| Trivy / Checkov / Scorecard | dependency/container/IaC/CI posture | candidate; scope only after a concrete need |
| SWE-bench | repair-evaluation methodology | reference only; not a product test |
| Dagger | reproducible pipeline execution | candidate; do not duplicate CI without evidence of benefit |
| OpenLLMetry / LangWatch | LLM tracing | defer; no LLM runtime is authorized |

### Non-adoption boundary

These tools must not become hidden authority layers, cloud dependencies, autonomous production-code writers, or substitutes for G-BOOT. In particular:

```
tool output = observation
tool output ≠ authority
CI green ≠ mobile runtime proof
external review ≠ repository truth
```

### Immediate consequence

The active product chain remains unchanged:

```
typecheck
→ Semantic 33
→ threat fixtures
→ storage validation
→ G-BOOT
```

No toolchain expansion is justified solely because the tool exists. The next product boundary remains the Android application identity → authenticated EAS build → APK → physical/runtime evidence sequence.

This delta also adopts the principle:

> **Use the smallest tool that closes the largest evidenced gap.**


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

Current forensic evaluation surface: PR #2 / `forensic/g-boot-witness-harness`, head `405fcfa07bb44715d21f196c4d782f8d48791b5d`.

Run #73 (workflow `typecheck`, run ID `36712792873`) executed successfully against that exact head. Its steps include forensic workspace testimony, TypeScript isolation, G-BOOT tail-byte inspection, claim verification, typecheck, Semantic 33, and threat fixtures. It did **not** execute the mobile runtime or close G-BOOT.

E-007 remains execution-witnessed at its exact pre-merge head by Run #72; the correction was then merged into the current PR #2 head.

Runtime evidence remains separate from CI evidence.
