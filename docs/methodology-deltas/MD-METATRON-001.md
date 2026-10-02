# MD-METATRON-001
## Metatron Graph / Multi-Scale Threat Model

**Status:** PROPOSED  

**Production authority:** NONE  

**Security authority:** NONE  

**Date proposed:** 2026-10-02  

**Related work units:** WU-METATRON-001  

---

### Purpose

Explore graph-based representation, propagation analysis, multi-scale decomposition, and optional symbolic visualization of Guardian evidence.

This methodology delta introduces a **bounded experimental lane** only.  
It does not modify, extend, or depend upon any existing production gate (G0–G8), SCG, Semantic 33, threat engine, or DecisionRecord authority.

---

### Primary Invariants

```
GRAPH ≠ TRUTH
FLOW ≠ THREAT SCORE
GEOMETRY ≠ AUTHORITY
VISUALIZATION ≠ DECISION
SYMBOLISM ≠ FACT
CENTRALITY ≠ IMPORTANCE
```

Any graph finding is observational only.  
It may never silently become, influence, or override a canonical security decision.

---

### Scope Boundaries

**In scope (experimental only):**
- Deterministic construction of a complete graph \( K_{13} \) from 13 canonical centres
- Explicit geometric intersection and edge-subdivision rules
- Provenance-carrying graph nodes and edges
- Neutral analysis primitives (e.g. ExposureFlow, structural concentration)
- Hierarchical (multi-scale) representation experiments
- Optional Codex / visualization projection layer

**Explicitly out of scope:**
- Any modification to existing threat scoring
- Any influence on DecisionRecord or policy evaluation
- Any automatic promotion into production
- Any claim that geometric properties confer security properties
- Numerological forcing of Guardian dimensions to match geometric constants

---

### Architectural Separation

```
                SOULSYNC GUARDIAN
                       │
              ┌────────┐
              │                 │
        Security Graph       Codex Graph
     (forensic / machine)  (presentation only)
              │                 │
              └────────┬────────┘
                       │
                Evidence Ledger
              (canonical authority)
```

- The Security Graph may represent relationships among evidence.
- The Codex Graph may render geometry or symbolic overlays.
- Both remain subordinate to the Evidence Ledger and DecisionRecord.

---

### Node Semantics (Forensic)

```ts
type ThreatGraphNode = {
  id: string;
  kind:
    | "evidence"
    | "entity"
    | "incident"
    | "indicator"
    | "policy"
    | "derived-state";

  sourceEvidenceIds: string[];   // mandatory

  confidence?: number;           // optional, non-authoritative
  authority: "NONE" | "SYSTEM";
  derivedFrom?: string[];
};
```

Every node must answer:  
**“Why does this node exist?”**  
If it cannot, it does not belong in the model.

---

### Geometric Foundation

The conventional Metatron construction supplies a useful analytical topology:

- 13 centres  
- Complete graph \( K_{13} \) → 78 pairwise edges  

This topology is available for experimentation.  
It does **not** define the number or meaning of Guardian dimensions.

Guardian dimensions remain independently defined by evidence and domain requirements.  
A 13-node projection may be tested for usefulness; it is never required.

Exact geometric construction rules (coordinates, intersection, collinearity, subdivision, vertex identity) are defined in:

→ `docs/graph/metatron-spec.md`

---

### Experimental Lane (M0–M9)

| Gate | Name                  | Purpose                                      |
|------|-----------------------|----------------------------------------------|
| M0   | Definition            | Geometry + terminology frozen                |
| M1   | Graph Construction    | Deterministic \( K_{13} \) generation        |
| M2   | Provenance            | Every node/edge fully traceable              |
| M3   | Fixture Projection    | Canonical threat fixtures → graph            |
| M4   | Graph Analysis        | Flow / cut / centrality experiments          |
| M5   | Equivalence           | Graph cannot alter canonical decisions       |
| M6   | Multi-scale           | Hierarchical representation tested           |
| M7   | Visualization         | Codex projection only                        |
| M8   | Performance           | Memory / CPU / storage measured              |
| M9   | Promotion Review      | Independent evidence required (non-automatic)|

**M9 never implies automatic production promotion.**

---

### Relationship to Existing Guardian Chain

Current production chain remains unchanged:

```
typecheck → Semantic33 → threat → SCG shadow/reconciliation → G-BOOT
```

Metatron sits entirely outside:

```
                 CURRENT GUARDIAN
                       │
                 evidence stable
                       │
                       ▼
              METATRON EXPERIMENT
                       │
          ┌────────────┬────────────┐
          ▼            ▼            ▼
       geometry      graph       analysis
          │            │            │
          └────────────┬────────────┘
                       ▼
                  observation
                       │
                       ▼
                 human review
```

---

### Promotion Criteria (Minimum)

No production integration may be considered until all of the following are witnessed:

1. Deterministic geometric construction  
2. Fixture-level graph reproducibility  
3. Full provenance on every node and edge  
4. Demonstrated equivalence (graph findings cannot change canonical decisions)  
5. Resource measurement under realistic ledger sizes  
6. Explicit human review and methodology acceptance

---

### First Work Unit

**WU-METATRON-001 — Geometric & Graph Specification**

Deliverables:
- This document (`MD-METATRON-001.md`)
- `docs/graph/metatron-spec.md`

No implementation code, TypeScript interfaces, UI, or analysis algorithms are authorized under this work unit.

---

**End of MD-METATRON-001**
