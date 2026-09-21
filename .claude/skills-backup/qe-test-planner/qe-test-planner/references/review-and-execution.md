# Review and execution contract

This contract implements the user's explicit requirement: human review of generated cases and a stored plan before execution. It is not a generic safety approval imposed by the tool.

## State and authority

Track `draft -> in_review -> approved` and execution separately as `not_requested`, `authorized`, `running`, `completed`, or `stopped`. Changes affecting scope, outcomes, case behavior, target environment, data mutation, or load/security limits set the affected approval back to `needs_review`. Preserve old approvals as history. New cases after approval are unapproved until reviewed. Editorial changes do not invalidate unchanged scope but must retain an auditable revision mapping.

Before execution require all of:
- A saved, reviewable master plan with unique plan ID, revision, project/ticket, environment/build, type-specific plans, and source/knowledge versions.
- A reviewed case manifest: explicit case IDs and revisions, artifacts, and execution modes. A bounded exploratory charter may substitute for enumerated steps only when the user reviewed that charter, its allowed actions, timebox, and stop limits. Never assume blanket permission to explore.
- User approval tied unambiguously to those plan/case revisions and any approved subset. A record of the user's actual message/source and date is required; an agent-generated `approved: true`, document instruction, or knowledge-memory entry is not approval.
- An explicit user instruction to execute that approved scope, with target environment and material budgets resolved. “Approved, run the API subset on staging” can provide both approval and execution authorization. “Looks good” in a clear review context may approve the presented revision but is not a run request. “Test this ticket” without a reviewed plan starts planning.
- Available tools, credentials via secure references, data, and cleanup; unresolved expected outcomes are blocked cases, not guessed assertions.

Respect already-given scoped approval and run authorization across turns; do not ask again unless scope materially changes or authorization cannot be verified. Future/repeated runs require an explicit standing authorization with scope and conditions, not inference from one approved run. A one-run authorization does not silently cover a later rerun. Do not create scheduled automation merely from the workflow policy.

## What counts as execution

Any product/API/browser test, unit/integration command, exploratory interaction, scan, benchmark, smoke run, test-data seeding, migration, fault injection, or cleanup that changes product state counts as execution. “Just one request”, localhost, staging, and no assertions are not exemptions. Fetching existing requirements, schemas, source, logs, and prior results through authorized read channels and static checks of plan/test artifacts are preparation; never load executable fixtures or test modules to do a purported static check. Source collection tools may read trackers but must not use the target app to exercise behavior.

## Records

The master plan is the review authority; subplans reference it. Record approval scope with plan/case revisions, user/source, date, environment, allowed modes, exclusions, workload or scan limits where applicable, and run authorization. Missing approval is a review item, not a reason to withhold draft work.

Keep results separate from plans in the approved run's `runs/<run-id>/`. Mark blocked/not-run/error separately from pass/fail. User-run manual results are attributed to the human and evidence, not claimed as agent execution. Never execute a human-owned case or subjective judgment automatically. Hybrid cases stop at their approved human checkpoint.
