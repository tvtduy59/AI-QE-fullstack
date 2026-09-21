---
name: remind-me
description: Read-only QE project knowledge recall and cross-check. Trigger for remind-me, remind me, and contextually similar tell me, check for me, what have we agreed, or is this still correct requests about project knowledge. Answer and ask questions only; never create or update files, memory, plans, reminders, tasks, or test runs.
---

# Remind Me

Treat `remind-me [project] [topic]` as a natural-language skill command, not a shell command. Recognize equivalent recall/cross-check intent without requiring exact spelling. Do not hijack unrelated “tell me a joke”, an explicit scheduled reminder, or a request to run a test; route those by actual intent.

1. Resolve project/topic from the active context. If ambiguous, ask one short question. Do not invent a project association.
2. Read current authoritative project knowledge using the Library read/search tools, or the explicitly configured repository store. Read relevant source records when needed for cross-checking. Do not rely only on search snippets or conversational recollection. Read the `$qe-project-memory` storage contract if necessary, without invoking its write workflow.
3. Reply in conversation with what is known, its status, source/date, and gaps. Distinguish confirmed decisions, user statements, proposals, disputes, and possibly stale facts. If comparing a new claim, show agreement or conflict and ask a focused clarification.
4. Ask what needs correction or which unresolved item to review next if useful. Keep the scope small; no boilerplate quiz. If the user confirms facts during this read-only review, acknowledge in conversation without persisting them. Change to write mode only after an explicit save/update/remember instruction; then use `$qe-project-memory` for that authorized update.

## Strict read-only contract

Do not create, edit, export, download/materialize, persist, or delete files. Do not update memory or last-reviewed timestamps. Do not create tasks, automations, notifications, plans, skills, cases, or test runs. Tool read caches do not grant permission for artifact creation. Use direct content reads; if a source needs a write-based extraction route, state the limitation and answer from readable evidence. No silent “helpful” changes.

For a statement that cannot be verified, say what is missing. If no record exists, say so and ask the user for knowledge inline; do not bootstrap a record in this mode. An ordinary “remind me about our test policy” is immediate recall; “remind me tomorrow” is a separate scheduling intent.

## Response pattern

Use a compact table only when comparing several claims: topic | current knowledge | status/source | question. Otherwise answer directly with a source-backed explanation and at most a few focused questions. Do not attach a file or save a summary.
