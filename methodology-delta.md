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

## MD-ENTROPY-001 — Constraint-bounded repository order

**Status:** Adopted as methodology only; conceptual transfer, not a physical/software equivalence claim.

External conceptual input: Carlo Rovelli's discussion of entropy and coarse-graining. The useful engineering lesson is not that software obeys thermodynamic entropy, but that **the observed order of a system depends on its boundaries, constraints, and chosen level of description**.

Applied carefully to SoulSyncMobile:

1. **Boundaries before accumulation.** Architectural separation (UI → hooks → threat semantics → storage → runtime witness) reduces uncontrolled coupling better than adding tools or abstractions without a demonstrated need.
2. **Coarse-graining must be explicit.** A repository summary, metric, score, or dashboard is a representation of underlying files, executions, and observations; it must never be mistaken for the underlying evidence.
3. **Constraints create inspectable order.** Exact SHAs, allowlists, typed contracts, closed decision vocabularies, explicit gates, and append-only evidence records make state transitions observable and auditable.
4. **Do not confuse more structure with more order.** Additional tools, dependencies, files, agents, or documentation increase system state unless they close a demonstrated gap.
5. **Subtraction is a valid control.** Removing redundant paths, duplicated semantics, unnecessary dependencies, or unsupported claims can reduce structural complexity without adding functionality.
6. **Entropy is not a defect label.** “Repo entropy” is an engineering metaphor, not a measured thermodynamic quantity. Any future metric must define its observable variables, scope, and reproducibility rather than borrowing physical terminology as proof.

The resulting workflow principle is:

```
constraint → boundary → observable state → evidence → controlled transition
```

This reinforces, but does not replace, the existing rule:

> **Use the smallest tool that closes the largest evidenced gap.**

**Explicit non-adoption:** no thermodynamic model, entropy score, complexity score, automated “order” optimizer, or AI-generated cleanup authority is introduced by this delta. The active product chain remains unchanged.

## MD-GSTACK-001 — Role-separated engineering loop

**Status:** Adopted as methodology only; no gstack agents or slash-command runtime is being imported into SoulSyncMobile.

The useful pattern from Garry Tan's gstack is not the number of personas or commands. It is the separation of engineering work into bounded roles/stages with explicit intent. Applied to SoulSyncMobile, the existing forensic method can be made more explicit:

```
CONTEXT
  ↓
LOOP
  ↓
HARNESS
  ↓
EVAL
  ↓
RUNTIME
```

### Transferred controls

1. **Context boundary.** Establish authoritative repository state, exact SHA, relevant contract, and current evidence before modification.
2. **Loop boundary.** Every defect follows the existing sequence:
   `FAILURE → MINIMAL FIX → DIFF AUDIT → INVARIANT AUDIT → EXECUTION`.
3. **Role separation.** Planning, implementation, review, testing, and runtime witnessing are distinct responsibilities even when performed by the same contributor or agent. No single conversational instruction becomes authority merely because it spans multiple roles.
4. **Harness boundary.** Harnesses test and bind evidence; they must not manufacture the observation they claim to witness.
5. **Evaluation boundary.** Fixtures and deterministic checks evaluate behavior against explicit expectations; they do not establish mobile-runtime behavior.
6. **Runtime boundary.** G-BOOT remains the direct evidence boundary for installation, boot, input, analysis, visible decision, local record, restart, and offline behavior.
7. **Process over proliferation.** Additional agents, personas, slash commands, or automation are justified only when they close a demonstrated gap. Agent count is not an engineering metric.

### Closed authority chain

The methodology therefore retains:

```
context
→ bounded work
→ actual interface
→ independent evaluation
→ runtime witness
→ accepted evidence
```

and explicitly rejects:

```
prompt/persona
→ authority
```

**Explicit non-adoption:** no gstack persona catalog, prompt swarm, cloud agent dependency, autonomous production-code writer, or replacement of the deterministic threat/policy path is introduced by this delta.

### Immediate consequence

MD-GSTACK-001 does **not** interrupt the active execution chain. Its practical effect is organizational: future work should state its role, boundary, expected artifact, and witness before execution. The next product Point remains Android application identity → authenticated EAS build → APK → physical/runtime evidence.


## MD-SECOND-BRAIN-001 — Evidence-preserving knowledge compounding

**Status:** Adopted as methodology only; no Obsidian/Claude Code dependency is introduced into SoulSyncMobile.

External input: Bober_smart's 29 Sep 2026 post describing a personal knowledge system built around a raw intake area, organized wiki, and a coordinating instruction file, attributed in the post to an Andrey Karpathy “personal second brain” workflow.

The transferable pattern is **not** “let an LLM become the source of truth.” It is to separate intake, organization, and coordination while preserving provenance.

### Proposed second-brain structure

```
RAW
  ↓
NORMALIZE / INDEX
  ↓
WIKI / METHOD
  ↓
CROSS-REFERENCES
  ↓
ACTIVE LEDGER
  ↓
TASK / POINT
```

For SoulSync methodology work:

- **RAW** preserves external articles, reviews, transcripts, screenshots, claims, and supplied observations without silently rewriting them.
- **NORMALIZE / INDEX** extracts entities, claims, repository refs, dates, SHAs, concepts, and candidate relationships.
- **WIKI / METHOD** stores durable engineering patterns such as MD-GSTACK, MD-ENTROPY, MD-TOOLCHAIN, MD-GENREC, and OpenSRE-derived controls.
- **CROSS-REFERENCES** connect methodology entries to repository gates, errors, commits, fixtures, and runtime boundaries.
- **ACTIVE LEDGER** records what is currently evidenced, open, corrected, or deferred.
- **TASK / POINT** contains only the next bounded action justified by the evidence state.

### Authority boundary

A second brain is a **context system**, not an authority system.

```
external source → observation
LLM synthesis   → interpretation/candidate relationship
repository/CI   → engineering evidence
runtime witness → runtime evidence
contract/gate   → authority for its defined decision
```

Therefore:

- accumulated context does not increase evidentiary authority;
- repeated mention does not turn a claim into a fact;
- backlinks do not prove causality;
- generated summaries must remain traceable to source material;
- stale knowledge must remain distinguishable from current repository state.

### Anti-bloat controls

The system must not become a second repository of duplicated product truth.

1. Store methodology and evidence indexes, not copies of application source.
2. Link exact repository SHAs instead of mirroring code.
3. Preserve source dates and provenance.
4. Separate historical from current state.
5. Archive superseded interpretations rather than silently overwriting them.
6. Promote a candidate pattern to adopted methodology only after explicit review.
7. Do not allow the knowledge system to modify production code autonomously.

### Operational loop

```
capture
→ preserve raw source
→ extract claims
→ map relationships
→ verify against authoritative state
→ promote bounded methodology
→ record provenance
→ select next Point
```

This extends the governing rule:

> **Discovery can be autonomous; authority cannot be autonomous.**

It also reinforces:

> **Use the smallest tool that closes the largest evidenced gap.**

**Explicit non-adoption:** no Obsidian runtime, Claude Code dependency, vector database, semantic search service, autonomous knowledge graph, or cloud knowledge dependency is required for SoulSyncMobile by this delta. The current product execution chain remains unchanged.
