# SoulSyncMobile Error & Bug Ledger

> **Purpose:** preserve every materially identified defect, mismatch, forensic weakness, or process failure so the same class of mistake is not repeated.
>
> **Rule:** an error is not merely something that made a test fail. This ledger also records places where our **methodology could have produced a false conclusion**.
>
> **Prevention principle:** **FAILURE → MINIMAL FIX → DIFF AUDIT → INVARIANT AUDIT → EXECUTION.**

## Error taxonomy

| ID | Finding | Cause | Impact / lesson | Prevention |
|---|---|---|---|---|
| E-001 | G-BOOT harness initially rejected its own modified workflow path | workflow changed but absent from allowlist | Boundary internally inconsistent | Verify allowlist against exact intended diff |
| E-002 | G-BOOT harness had strict-TypeScript argument typing problem | Optional fallback returned `string | undefined` | Isolated compile before broader execution |
| E-003 | Runtime witness could be mistaken for proof merely because command ran | Invocation and observation were conflated | Would create false runtime evidence | Require preserved raw artifact per stage |
| E-004 | CI could be mistaken for mobile runtime evidence | CI does not execute Android lifecycle | Green CI cannot prove runtime | Prohibit CI-as-runtime substitution |
| E-005 | G-BOOT lacked actual Android/emulator evidence | No device/emulator artifact | Gate remains open | Require full G-BOOT runtime sequence |
| E-006 | MALFORMED fixture narrower than general malformed-URL handling | Fixture covers one malformed form | Passing fixture is not universal coverage | Add structurally distinct malformed URL tests |
| E-007 | Zero-width normalization and label validation cover different sets | Normalization strips four code points; observed label check only U+200B | Semantic divergence risk | One canonical invisible-character policy |
| E-008 | Incident storage uses `JSON.parse(raw) as T` | Compile-time assertion without runtime schema | Invalid persisted data can pass typing | Runtime decoder at storage boundary |
| E-009 | Incident and harmony writes are sequential | No transaction boundary | Partial persistence possible | Atomic/recoverable persistence semantics |
| E-010 | Storage failure semantics underspecified | Analysis fail-closed but storage state less explicit | Decision may lack durable record semantics | Separate decision and persistence states |
| E-011 | History preserved but current branch state not explicitly modeled | No dedicated current-state layer | Historical/current confusion risk | Separate immutable history from current state |
| E-012 | Semantic 33 and heuristic threat recognition both normalize inputs | Two intentional recognition paths | Silent divergence risk | Canonical contract or differential tests |
| E-013 | Branch lineage can be confused | Multiple forensic refs | Wrong ref can produce irrelevant evidence | Record branch/ref and exact SHA |
| E-014 | Witness metadata permits UNSPECIFIED identity/evidence fields | Harness arguments optional | Reproduction can be ambiguous | Require minimum gate-closing evidence tuple |
| E-015 | observedAt is write-time rather than event-time | Timestamp generated at record write | Temporal ambiguity | Preserve event and record time where needed |
| E-016 | G-BOOT NDJSON append-only but not tamper-evident | No chained digest/external anchor | Later modification may be hard to detect | Add integrity anchoring when security-critical |
| E-017 | Runtime identity tuple incomplete | Missing complete build/device/runtime identity | Reproduction ambiguity | Define minimum runtime identity tuple |
| E-018 | No production binary/store artifact witnessed | Source/CI only | Release claims remain bounded | Hash production artifact before release claims |
| E-019 | App identity metadata minimal | app.json lacks full production identity | Package/build anchor incomplete | Define production identity before release validation |
| E-020 | Experimental Node type-stripping path fragile long-term | Experimental runtime behavior | Tooling may change | Keep isolated; migrate when blocking |
| E-021 | Missing package module declaration produces warnings | Module mode unspecified | Warning noise | Track environmental warnings separately |
| E-022 | uuid/dependency audit noise observed | Dependency/toolchain state | Distraction risk | Track as hygiene unless security impact shown |
| E-023 | CI Node runtime differs from application Node target | CI environment transition warnings | Environments must not be conflated | Record separately |
| E-024 | Forensic methodology risked outrunning product validation | Evidence machinery preceded mobile runtime proof | Meta-work saturation | Prioritize actual runtime witness |
| E-025 | Commercial-readiness claims exceed evidence | Positioning hypotheses preceded market validation | Architecture does not prove demand | Keep market claims hypothetical |
| E-026 | External reviews can be mistaken for repository facts | Third-party assessments are interpretations | Could cause unverified changes | Reproduce against exact repository state |
| E-027 | Error identifiers can become ambiguous without registry | Duplicate/colliding IDs across components | Traceability weakened | Globally unique, component-scoped registry |
| E-028 | Same evidence category can be counted twice | Overlapping witnesses/checks | Inflated evidence strength | Define evidence identity |
| E-029 | Green inferred from partial coverage | Static/fixture tests do not cover lifecycle | Gate pressure without evidence | Name every required observation |
| E-030 | Fixes can expand application diff | Harness work may alter application behavior | Harness contaminates baseline | Exact baseline + fail closed on unexpected changes |
| E-031 | Ledger transcription introduced a 41-character baseline SHA | Manual transcription duplicated a hexadecimal character | Documentation drifted from authoritative state | TIF-SHA-40; machine validation |

## Root-cause classes

### RC-01 — Boundary conflation
Mixing tool invocation, code correctness, CI success, and real-world runtime observation.

### RC-02 — Contract drift
Related rules encoded differently across system surfaces.

### RC-03 — Type-vs-runtime confusion
Compile-time types treated as runtime guarantees.

### RC-04 — Evidence identity weakness
Witness lacks enough exact identity to reproduce it.

### RC-05 — Process overreach
External assessments or methodology improvements outrun repository evidence.

### RC-06 — Transcription / typographic integrity
A human or tool alters an identifier, reference, path, or semantic class during transcription or prose editing.

**Countermeasure:** canonical identifiers are validated by machine equality/format checks rather than visual inspection.

## Permanent anti-repeat rules

1. Exact SHA before interpretation.
2. No runtime claim without runtime evidence.
3. No green claim from a proxy test.
4. Minimal fix only.
5. Diff audit immediately after every fix.
6. Invariant audit before execution.
7. Independent raw evidence is preserved before gate transition.
8. External reviews are observations, not authority.
9. Historical and current state are never conflated.
10. Every new error gets a unique ID and prevention rule.
11. Do not count one underlying observation as multiple independent witnesses.
12. Do not broaden scope merely because a warning or non-gate defect exists.
13. Canonical identifiers are validated by machine check, not by reading.

## Ledger maintenance rule

**Observe → reproduce → identify root cause → minimal fix if authorized → diff audit → invariant audit → execute → record outcome → add prevention rule.**

Fixed defects are never deleted; their fixing commit and execution witness are appended to preserve audit history.
