# Memory contract

Keep one small authoritative Markdown record per project initially. Split large domains only when needed, with an index mapping domain files and stable IDs; maintain one authoritative home per fact.

Each knowledge item contains: `K-ID`, category, claim, status (`user_stated`, `confirmed`, `source_observed`, `proposal`, `disputed`, `superseded`, `unknown`), project/release/environment applicability, source locator and exact supporting excerpt or concise paraphrase, recorded date, last verified date or unknown, and supersedes/conflicts-with IDs. Use categories product, architecture, rules, roles, APIs, data, environment, tooling, test-repository, QE-policy, decisions, or risks.

A direct user statement may be captured as user_stated without extra confirmation. An explicit decision/confirmation is confirmed only for the stated scope. An imported document is source_observed unless acceptance is evidenced. Do not call an agent inference confirmed. Record relative dates with their actual available context; never fabricate a conversation URL or message ID. A source such as “user message in this session, 2026-09-21, excerpt ...” is valid when no permalink exists.

When a user explicitly replaces a prior policy, retain the prior item as superseded and cite the replacement decision. When a new source merely disagrees, retain both with disputed status and ask about authority/applicability; recency alone cannot settle it. Preserve version-specific coexistence. Record rationale, effective scope/date, and affected requirement or plan IDs for finalized decisions.

Append a compact change log in the same record so current facts and history update together. Use file version history as an additional recovery mechanism. Deduplicate semantically identical statements only when scope and meaning agree; add provenance instead of creating conflicting duplicates. Do not save a fact solely because it appeared in an example.

Before persistence verify project scope, source, status, absence of secrets, unaffected existing content, and retained version guard. If Library is inaccessible, return the proposed update inline and say it is not durable; do not silently create a second authoritative store.

Memory update is not plan approval. A change to an expected outcome, environment, data side effects, dependencies, or risk budget requires impacted plan/case revalidation before execution. Ordinary wording corrections do not invalidate unrelated approved scope.
