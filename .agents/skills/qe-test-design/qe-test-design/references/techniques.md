# Design techniques and coverage

Select a technique because of the behavior/risk, not because every ticket must use it. Maintain the derived model with source evidence so the reviewer can see what the cases cover.

| Trigger | Method | Required design evidence | Limits |
| --- | --- | --- | --- |
| Input classes | Equivalence partitioning | Valid/invalid partitions, representatives, assumptions | One representative cannot prove all values; isolate invalid dimensions where needed |
| Ordered limits | Boundary value analysis | Exact boundary, inclusivity, type/precision, adjacent representable values | Do not assume monetary precision or invent epsilon; unresolved precision is a question |
| Interacting conditions | Decision table | Conditions, possible rules, outcomes, impossible combinations with reasons | Remove impossible rules only with constraints, not convenience |
| Stateful workflow | State transitions | States/events/guards/actions, valid and invalid transitions, selected transition/path coverage | Do not invent undocumented states or claim all paths from all transitions |
| Configurations | 1-wise/pairwise/higher-strength combinations | Factors, values, constraints, chosen strength, generated set and measured interaction coverage | 1-wise covers each value, not value pairs; pairwise is not exhaustive and cannot replace known risk scenarios |
| Failure experience | Error guessing/checklist | Concrete prior defect or failure hypothesis | Hypotheses are not confirmed requirements |
| Uncertain UX/workflow | Exploratory charter | Mission, risk, timebox, boundaries, evidence, human checkpoint | Requires reviewed charter before interacting with the product |
| Known pure rule | Property/metamorphic design | Source-backed invariant/relation, domain constraints, falsification oracle | Do not derive the oracle from the same implementation under test |
| Isolated implementation | Statement/branch-oriented unit design | Observable contract, selected code paths, dependencies controlled | Coverage percentages describe execution, not correctness; no claim of coverage before running |

Stable testing concepts: [ISTQB CTFL syllabus](https://istqb.org/?download_id=3345&sdm_process_download=1). Combinatorial strength background: [NIST ACTS project](https://csrc.nist.gov/projects/automated-combinatorial-testing-for-software). Reviewed 2026-09-21. The operational table is an original application guide; do not treat it as verbatim standard text or a product requirement.

## Case quality

Require a verifiable outcome for every meaningful action, source-backed data constraints, realistic preconditions, isolated fixtures, and restoration. Keep high-level cases readable; multiple expectations are valid for one coherent behavior. Preserve postconditions including follow-up actions, but make actions explicit so they are reviewed for execution effects. Split unrelated scenarios or alternative outcomes that make failures ambiguous. Avoid both arbitrary case count targets and Cartesian explosions; explain retained risk and coverage gaps.

Negative cases need approved expected behavior. If the error contract is unknown, draft the condition with outcome unresolved and block execution of that assertion rather than inventing HTTP codes or messages. Include concurrency/precision/time risks only when applicable. Separate intended behavior from current implementation.
