---
name: qe-project-memory
description: Maintain durable project-specific QE knowledge when the user shares a fact, confirms a decision, corrects an assumption, or closes a discussion. Retrieve project rules for QA analysis and planning. Use versioned project knowledge files, preserve evidence and history, and defer to remind-me for read-only recall or cross-checking.
---

# QE Project Memory

Use persistent files as explicit project memory. Updates happen while processing user interactions; do not promise background monitoring or universal recall without invoking the skill. Keep methodology in separate skills and product facts in project records.

## Routing and storage

1. First classify intent. For `remind-me`, “remind me”, or knowledge-focused “tell me/check for me/what do we know/is this still correct”, use `$remind-me` and do no writes. The read-only mode wins over automatic capture, including confirmations during that review, until the user explicitly requests saving or switching to update mode. “Check this API by running tests” is execution intent, not knowledge recall.
2. Resolve project identity from the user, current target repository, or a verified project registry. Do not merge facts from separate products. The initial workspace `ai-test-autonomous` describes this QE workflow, not an assumed product repository. Ask one question only if a fact cannot safely be assigned to a project; otherwise do useful scoped work.
3. Use the Library skill to search/read `/qe-knowledge/projects/<project>/project-knowledge.md`. An explicit user-selected repository-backed knowledge store overrides this default. Never use scratch files or model conversational memory as the sole durable source. Do not search unrelated projects for facts. If persistence fails, say the update was not saved.
4. Read [memory contract](references/memory-contract.md). Load the current file/version before editing; preserve its identity, unrelated facts, IDs, and history. Use version-guarded replacement. On conflict, reload current content and reconcile; never remove the guard or overwrite concurrent changes blindly.
5. Capture applicable new facts and decisions automatically under the user's standing instruction. Distinguish direct user facts, confirmed decisions, sourced observations, proposals, unknowns, and conflicts. Do not require the user to repeat permission for ordinary knowledge updates. A finalized discussion requires an explicit agreed outcome, not agent summary or user silence. Preserve unresolved choices as proposals.
6. Save the updated record; briefly report what was added/changed and any unresolved conflict. Flag affected plans as needing revalidation without automatically rewriting their cases or running them. Record affected plan IDs when known; do not claim all plans were scanned.

## Bootstrap and retrieval

Use [project record template](assets/project-knowledge-template.md) when the project has no record and the task authorizes recording. Load only relevant facts for each downstream task and cite knowledge IDs, source locators, version, and last verification. Check volatile facts against current authoritative evidence when materially relevant. Unknown age is not fresh. A stale fact is still historical evidence, not automatically false. Project memory is context, never evidence of execution approval.

Never import historical user memories as newly confirmed product facts. Omit secrets and unnecessary personal information. Store a secret's configured reference only, not its value. Do not rewrite skill code for every project update.
