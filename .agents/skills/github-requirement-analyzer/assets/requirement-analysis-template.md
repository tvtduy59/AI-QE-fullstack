# Requirement Analysis Package

Replace guidance with findings; retain absent sections with explicit not-stated/not-assessed explanations.

## 1. Summary and provenance

- Target canonical identity/URL, target release/environment if known
- Input package identities, versions/timestamps, locators, source freshness, analysis time
- Analysis coverage and handoff readiness, separately, with material reasons
- Objective, changed behavior, explicitly unchanged behavior, baseline gaps
- Short proposed scope and highest-impact questions

## 2. Evidence register

| Source ID (qualified by input package) | URL/locator and precise location | Version/time | Evidence type and inspected extent | Limitations |
| --- | --- | --- | --- | --- |

Reuse upstream IDs; add AS- IDs for new evidence. Attribute direct user decisions as session sources. Never cite unread references as inspected evidence.

## 3. Requirement inventory

| AR-ID / original AC-ID | Behavior and conditions | Expected outcome | Basis | Decision status | Applicability | Clarity | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |

Include actors, permissions, data constraints, units, boundaries, exceptions, and coupled side effects as supported. Use supplementary role/state/input tables only if they add clarity. Preserve exact wording where meaning could otherwise change.

## 4. Change and dependency analysis

| Behavior/component | Before evidence | After evidence | New/changed/unchanged/removed/unknown | Related RR-ID or dependency evidence | Applicability/uncertainty |
| --- | --- | --- | --- | --- | --- |

## 5. Verification obligations and proposed scope

| VO-ID | What to verify | AR/RK IDs and evidence | Requirement/derived/risk basis | Scope disposition and reason | Observable result or missing oracle | Feasibility/blocker | Handoff readiness |
| --- | --- | --- | --- | --- | --- | --- | --- |

Keep unresolved branches conditional. State existing coverage is not assessed unless supplied test evidence was inspected. Do not add test steps, data sets, techniques, or execution owners.

## 6. Risk register

| RK-ID | Behavior and failure mechanism | Consequence | Evidence/inference and premises | Impact / likelihood | Analyst triage and rationale | Linked VO/AQ IDs |
| --- | --- | --- | --- | --- | --- | --- |

## 7. Conflicts, assumptions, and questions

| AQ-ID | Conflict or missing information with sources | Assumption/proposal, if any | Affected AR/VO IDs | Decision needed and why | Blocking scope | Owner role if known |
| --- | --- | --- | --- | --- | --- | --- |

## 8. Disposition and traceability audit

| Original AC / relevant relationship / unresolved candidate | Mapped analysis IDs | Disposition | Reason or inherited limitation |
| --- | --- | --- | --- |

Account for every target AC and relevant relation, including duplicates, historical evidence, rejected applicability, and unresolved context. List explicit exclusions with evidence; unknown information is not excluded by default.

## 9. Downstream handoff

List clear obligations, conditional obligations and decisions, project/QE knowledge still needed, existing-test retrieval anchors, and collection/resolution gaps. State that test strategy, existing coverage, test cases, and execution ownership are downstream work. Summarize a minimal set of blocking questions only after providing the useful analysis.
