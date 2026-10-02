# Metatron Geometric & Graph Specification
## METATRON-GEO-001 / METATRON-GRAPH-001

**Status:** DRAFT (tied to MD-METATRON-001)  
**Authority:** NONE  
**Date:** 2026-10-02  

This document freezes the geometric construction and graph semantics for the experimental Metatron Graph model.  
All claims are bounded by the invariants in MD-METATRON-001.

---

## A. Geometric Construction (METATRON-GEO-001)

### A.1 Input

Exactly 13 canonical centres with fixed coordinates in the Euclidean plane (unit distance \( d = 1 \)):

```
v0  = ( 0 ,  0 )
v1  = ( 1 ,  0 )
v2  = ( 1/2 ,  √3/2 )
v3  = (−1/2 ,  √3/2 )
v4  = (−1 ,  0 )
v5  = (−1/2 , −√3/2 )
v6  = ( 1/2 , −√3/2 )
v7  = ( 2 ,  0 )
v8  = ( 1 ,  √3 )
v9  = (−1 ,  √3 )
v10 = (−2 ,  0 )
v11 = (−1 , −√3 )
v12 = ( 1 , −√3 )
```

These coordinates are exact (symbolic) and form the conventional Metatron / Fruit-of-Life centre set.

### A.2 Edge Construction

Form the complete graph \( K_{13} \):

- Vertices: \( V = \{v_0, \dots, v_{12}\} \)
- Edges: every unordered pair \( \{v_i, v_j\} \) for \( 0 \le i < j \le 12 \)
- Number of edges: \( \binom{13}{2} = 78 \)

### A.3 Intersection Rule

An intersection point is recorded if and only if:

1. Two edges \( e_a = \{a,b\} \) and \( e_b = \{c,d\} \) have disjoint endpoint sets.
2. The corresponding line segments properly intersect in their relative interiors.
3. The intersection point is not coincident (within exact symbolic equality) with any of the original 13 centres.

### A.4 Collinearity / Multiplicity Rule

- If three or more edges are concurrent at the same point, that point is recorded once only.
- Exact symbolic comparison (after simplification) is used to detect coincidence.
- Numerical floating-point tolerance is forbidden for identity decisions.

### A.5 Subdivision Rule

For each of the original 78 edges:

1. Collect all intersection points that lie on the closed segment (including the two endpoints).
2. Parameterize each point by the affine parameter \( t \in [0,1] \) along the segment.
3. Sort the points by increasing \( t \).
4. Emit consecutive sub-edges between successive points.
5. Discard zero-length sub-edges.

### A.6 Vertex Identity Rule

- Original centres retain their IDs 0–12.
- Each unique intersection point receives a new, stable integer ID starting at 13.
- Identity is determined solely by exact coordinate equality after simplification.
- No two distinct geometric points may share an ID; no single geometric point may receive multiple IDs.

### A.7 Expected Output (to be witnessed)

After applying the rules above, the construction must produce a reproducible planar graph.  
The exact counts of intersection vertices and subdivided edges are **not pre-asserted** in this specification.  
They become empirical claims only after a deterministic implementation has been executed and witnessed under WU-METATRON-001 / M1.

---

## B. Graph Semantics (METATRON-GRAPH-001)

### B.1 Node Types

```ts
type NodeKind =
  | "evidence"
  | "entity"
  | "incident"
  | "indicator"
  | "policy"
  | "derived-state";
```

### B.2 Node Schema (minimum)

```ts
type ThreatGraphNode = {
  id: string;                        // stable, deterministic
  kind: NodeKind;

  // Mandatory provenance
  sourceEvidenceIds: string[];

  // Optional non-authoritative metadata
  confidence?: number;               // 0–1, never used as severity
  authority: "NONE" | "SYSTEM";
  derivedFrom?: string[];            // other graph node IDs

  // Geometry (only when node participates in the geometric layer)
  geometry?: {
    role: "centre" | "intersection";
    x: number;                       // or exact symbolic representation
    y: number;
  };
};
```

### B.3 Edge Schema (minimum)

```ts
type ThreatGraphEdge = {
  id: string;
  source: string;                    // node id
  target: string;                    // node id dig

  // Provenance
  sourceEvidenceIds: string[];

  // Optional analysis metadata (never authoritative)
  weight?: number;
  capacity?: number;                 // for ExposureFlow experiments only
  kind?: "relationship" | "propagation" | "geometric";
};
```

### B.4 Authority Model

- Every node and edge carries an explicit `authority` field.
- Default and only currently permitted value for experimental work: `"NONE"`.
- `"SYSTEM"` may be introduced later only under a separate methodology delta and witnessed promotion.

### B.5 Provenance Invariant

A node or edge is invalid if `sourceEvidenceIds` is empty or cannot be resolved to existing Evidence Ledger entries.

---

## C. Analysis Primitives (Neutral Naming)

| Primitive          | Meaning                                      | Forbidden Interpretation          |
|--------------------|----------------------------------------------|-----------------------------------|
| ExposureFlow       | Maximum flow under given capacities          | “Risk” or “probability of compromise” |
| MinCut             | Minimum capacity cut separating source/sink  | “Critical vulnerability set”      |
| Structural concentration | Any centrality or density measure       | “Importance” or “priority”        |
| HarmonyIndex       | Graph-balance visualization metric           | Threat severity                   |
| DissonanceIndex    | Graph-imbalance visualization metric         | Threat severity                   |

All analysis outputs are observational findings only.  
They may appear in explanations but may never alter a DecisionRecord.

---

## D. Reproducibility Requirement

Given identical:

- input evidence set / fixture
- normalization rules
- this geometric specification
- this graph semantics specification

the following pipeline must be deterministic:

```
input
  ↓
normalization
  ↓
graph construction (geometry + semantics)
  ↓
graph analysis
```

Any non-determinism is a defect.

---

## E. Visualization Boundary (Codex Layer)

The geometric embedding and any derived visual attributes (HarmonyIndex, flow animations, Metatron-style drawings) belong exclusively to the Codex / presentation layer.

They are projections of the Security Graph, never sources of truth.

---

## F. Change Control

Any modification to coordinates, intersection rules, subdivision rules, node/edge schemas, or authority model requires:

1. A new methodology delta or an explicit amendment to MD-METATRON-001.
2. Re-execution of all affected experimental gates (M0 onward).
3. Fresh reproducibility witnesses.

---

**End of metatron-spec.md**
