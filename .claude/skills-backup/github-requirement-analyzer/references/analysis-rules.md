# Evidence and analysis rules

## Normalize without changing meaning

Extract independently verifiable behaviors while preserving conditions, negation, actors, units, limits, exceptions, and coupled outcomes. Keep related outcomes grouped under their original acceptance criterion if splitting would lose an invariant. Preserve original requirement IDs and assign local `AR-` IDs only for analysis bookkeeping. Map every extracted item to its original wording and exact location. Consolidate duplicates only when subject, conditions, version, and expected outcome agree; retain all supporting citations.

Capture actor/permission, trigger, input and constraints, pre-state, expected output/state/side effects, failure behavior, scope/version, and observable evidence where stated. Use `not stated` for missing fields; do not fill them with common product conventions. Distinguish explicit unchanged behavior from behavior merely unmentioned. Record code and observed behavior as implementation evidence, not normative authority.

## Keep evidence dimensions separate

| Dimension | Values / interpretation |
| --- | --- |
| Statement basis | explicit source statement; derived implication; assumption/proposal |
| Decision status | stated; explicitly accepted; proposed; disputed; superseded; unknown |
| Applicability | target version; conditional; historical; unknown, with evidence |
| Clarity | clear; ambiguous; conflicting; incomplete |
| Verification feasibility | observable as stated; oracle missing; access/data/environment unknown; infeasible with known constraints |

`Stated` means a source says it; it does not certify approval. A sourced requirement can be ambiguous. A confident relationship can have unknown applicability. A usable test oracle does not prove access to the environment. Do not collapse these dimensions into a single confidence or readiness score.

Accept derived implications only as labeled analysis, cite premises, and state why the implication follows. Never promote a plausible safety property, implementation convention, or analyst preference into an acceptance criterion. Keep assumptions optional and visible; questions are preferable when different answers change scope or expected outcomes.

## Resolve conflicts only with authority evidence

Compare actor, object, operation, preconditions, environment, release, units, and timing first. Different scopes may explain different values. Preserve both statements if scope is unknown or the same. Use explicit acceptance/supersession or a supplied project authority policy to resolve them. Recency, author job title, closure, merged code, or majority opinion alone is insufficient. If a policy is unavailable, say so instead of inventing precedence.

Treat resolver acceptance as relevance for context, not approval of a requirement. Treat unresolved candidates as open context, not new obligations. Historical defects identify possible risk mechanisms but do not alone establish current expected behavior.

## Analyze behavior and testability

Use compact tables for actors/permissions, inputs/limits, and state transitions only when the evidence warrants them. Mark absent transitions or roles as unknown rather than generating a complete imagined state machine. Inspect exception paths, persistence, concurrency, idempotency, external dependencies, security, accessibility, and performance selectively when a sourced behavior suggests exposure. Record inferred exposure as risk, not a requirement. Do not invent numeric thresholds, error codes, exact UI copy, supported browsers, or hidden APIs.

For each requirement identify the stated observable result and where verification might be possible; separate this conceptual oracle from verified tool/environment availability. Identify ambiguous boundaries, missing outcomes, incompatible criteria, or unavailable prerequisites. Avoid writing test steps, detailed data sets, test levels, techniques, automation classifications, or pass/fail results.

## Changes and updates

Separate new, changed, explicitly unchanged, removed, and unknown behavior. Claim before/after only when both have evidence; otherwise mark the baseline unknown. Preserve IDs for unchanged meanings on a supplied prior analysis, add IDs for new meanings, and mark superseded items without recycling IDs. Record source changes and the affected analysis items; do not silently carry forward stale decisions.
