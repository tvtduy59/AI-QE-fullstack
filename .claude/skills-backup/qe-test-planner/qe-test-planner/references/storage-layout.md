# Plan storage and review layout

Default to persistent Library paths. For a user-selected git-backed project store, use the same relative tree in that repository and its normal persistence workflow instead; never duplicate repository-backed plans in Library. Root `/test-plans` is a logical persistent folder, not the machine filesystem root. Use safe project/ticket slugs; do not accept `..` or arbitrary path traversal.

`/test-plans/<project>/<ticket-or-change>/plan.md` is the master plan. Store applicable subplans and case manifests at:

| Folder | Responsibility |
| --- | --- |
| `manual/` | Human functional/UX/exploratory work |
| `unit/` | Isolated logic/component checks |
| `api/` | Endpoint behavior and protocol contracts |
| `integration/` | Cross-component and provider/consumer interactions |
| `ui-e2e/` | Browser or full user-journey automation |
| `performance/` | Load, latency, capacity, and endurance |
| `security/` | Authorized security checks |
| `accessibility/` | Accessibility checks and human evaluation |
| `regression/` | Selection manifest referencing canonical cases |
| `runs/<run-id>/` | Results/evidence from an authorized run |

Use `plan.md`, `cases.md` (or the configured test repository format), and optional scripts under each applicable type directory. Do not create empty ticket-specific subplans for irrelevant types. A root workspace can precreate category folders as an organizational scaffold, but actual ticket plans use the layout above.

Manual is an execution mode while API/integration are layers and performance/security are test purposes. They overlap. Assign each case a canonical folder, separate `execution_mode` (human/automated/hybrid/blocked), `test_level`, `test_type`, and tags. A human-run API check stays in `api/` with mode human and is linked from the manual summary, not duplicated. A performance test using an API belongs in `performance/` and records its API surface. The master coverage matrix references each canonical case once.

Create/update through the Library skill and preserve known file identities and version guards. Before execution require the reviewed plan and case versions to be retrievable. If saving fails, present draft work and say execution remains blocked by the missing durable plan. Do not report a directory or artifact as created until the write succeeds.
