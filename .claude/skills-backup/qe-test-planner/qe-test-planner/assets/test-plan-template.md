# Test plan: <project> / <ticket-or-change>

Plan ID: <ID>; revision: <revision>; status: draft
Source versions: <collector/resolver/analyzer>; knowledge revision: <revision>
Target build/environment: <known or unresolved>
Plan approval: none; case approval: none; execution authorization: none

## Goal, scope, and risks

Describe target outcomes, supported and conditional scope, exclusions with rationale, risks, and unresolved decisions.

## Coverage and strategy

| Obligation/requirement | Risk | Existing evidence/case | Reuse/update/new/defer | Level/type | Technique and reason | Canonical subplan/case | Execution mode and feasibility |
| --- | --- | --- | --- | --- | --- | --- | --- |

Record pyramid tradeoffs, omitted layers, and regression selection. A similar test is not verified coverage until its assertions and conditions are inspected.

## Environment, data, dependencies, and cleanup

Record targets, build, fixtures, roles/accounts as references, data lifecycle, mocks versus real dependencies, observability, and cleanup actions. Do not include secrets.

## Entry, exit, and stop criteria

Define testable readiness and completion criteria and unresolved thresholds; never make invented SLAs mandatory. Define stop conditions and limits for load, destructive actions, and external services.

## Reviewable artifacts

| Type | Subplan path/revision | Case manifest/revision and IDs | Human checkpoint | Open issue |
| --- | --- | --- | --- | --- |

## Review and execution record

| Event | Exact plan/case revision or subset | User/source/date | Environment/budgets | Status |
| --- | --- | --- | --- | --- |

Keep approval and permission to run separate. Leave them unset until user evidence exists.

## Results

Not run. Link run records only after authorized execution; never mark predicted results as observed.
