# Scope, risk, and downstream handoff

## Proposed verification obligations

Describe what must be verified, not how to execute it. Use local `VO-` IDs and map each obligation to `AR-` requirement IDs or `RK-` risk IDs and source evidence. Keep three bases visible: sourced requirement, derived implication, and risk-driven proposal. A risk-driven proposal is not an approved product requirement.

Classify each item as:
- `supported_scope`: evidence-backed behavior applicable to the target and sufficiently clear to carry into test design. This is analyst-supported scope, not human approval.
- `conditional_scope`: applicability, conflicting requirements, or expected outcome needs a decision. Preserve branches rather than selecting a winner.
- `excluded`: explicitly outside scope or justified irrelevant, with evidence/reason. Missing information is not an exclusion.

Separate these scope decisions from practical verification blockers such as missing test accounts. Include regression concerns only when a concrete shared rule, dependency, or invariant connects them to the change. Never claim existing test coverage without inspecting test evidence; normally state `existing coverage not assessed` for this phase. Avoid expanding scope into every generic QA checklist item.

## Risks

For each risk record the triggering behavior, failure mechanism, possible consequence, evidence versus hypothesis, impact, likelihood if supported (otherwise unknown), and uncertainty. Apply supplied project severity/priority rules when available. Otherwise use qualitative analyst triage high/medium/low/unknown with a rationale, explicitly not a calibrated score or project-approved priority. Separate requirement ambiguity from product failure risk and execution obstacles. Prioritize questions by what decisions they block, not just by count.

## Questions and assumptions

Assign `AQ-` IDs. Include the conflicting statements or missing detail, sources, affected requirements and obligations, why the answer matters, and suggested decision-owner role only when known. Never invent a named owner. Record answers supplied by the user as session decisions, separately from product-source approval. Ask the smallest set of blocking questions after delivering all useful analysis. Do not stop analysis for nonblocking gaps or send messages to owners without authorization.

## Readiness and completeness

Report both dimensions:
- Analysis coverage: `complete_within_supplied_scope`, `partial`, or `blocked`. Mark partial if known retrieval gaps, stale/conflicting snapshots, or unavailable decisive evidence prevent analysis of otherwise in-scope behavior. Mark blocked when no identifiable target behavior is available. A fully documented requirement conflict does not itself mean analysis coverage is incomplete.
- Handoff readiness: `ready_for_test_design`, `ready_with_conditions`, or `blocked_on_decisions`, applied per obligation and summarized with reasons. Clear obligations can proceed independently even when others are blocked. None of these means ready for release or QE approved.

## Validation before handoff

1. Account for every target acceptance criterion and relevant accepted relationship: mapped, duplicate, historical, conditional, excluded, or unresolved, with reason. Do not silently discard unresolved resolver candidates.
2. Give every requirement, risk, scope decision, and proposed verification obligation a trace to inspected evidence or an explicitly labeled inference with premises.
3. Preserve all material conflicts and inherited missing-content limitations. No unresolved value may appear as a confirmed expected result.
4. Reconcile IDs and cross-references; preserve upstream package identity, versions, locators, and ID namespaces.
5. Keep unknown coverage distinct from absent coverage; do not claim any tests were designed or run.

Pass the Requirement Analysis Package and upstream locators to the Existing-Test Retriever and Test Strategist roles. These are downstream roles, not assumed installed skills. The next stages retrieve QE/project conventions, check existing coverage, select levels and techniques, and form a test plan and suite. Do not automatically start those phases.
