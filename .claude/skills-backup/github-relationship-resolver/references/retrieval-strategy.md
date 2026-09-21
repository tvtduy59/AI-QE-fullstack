# Retrieval strategy

## Capability check

Use an existing authorized GitHub connector, MCP, CLI, API, or supplied export. Inspect advertised capabilities and supported query syntax; do not assume GitHub search provides vector search or that an external index is current. Record index/export time, included repositories, searchable fields, and gaps where known. Never upload private content to a new indexing service without authorization. With no live search, assess supplied material and mark discovery coverage accordingly.

## Explicit graph

Start with native parent/child, blocking/blocked-by, duplicate, and linked PR relationships, then textual references. Preserve exact edge type and direction. A mention remains a mention. Native metadata may be unavailable: report unsupported, not absent. Resolve issue versus PR identity before adding a node. Expand only relevant branches; list intentionally skipped branches with a reason. Stop cycles via canonical identities. Record paths such as target -> parent -> sibling, but do not call a sibling a dependency solely from that path.

## Search plan

Build small independent queries from source anchors. Begin with precise original requirement IDs, distinctive rule phrases, endpoint names, or domain entities; broaden to behavior synonyms and component terms. Search bugs for the same operation and failure modes, then issues sharing the relevant workflow or business rule. Include closed issues: closure does not establish obsolescence. Do not require a component label, because labels can be missing or inconsistent. Balance precision with at least one broader behavior query; avoid only searching recent tickets.

Use semantic retrieval when an authorized index supports it. Otherwise use supported keyword queries and read candidates to assess conceptual similarity. Report `keyword retrieval + semantic assessment`, not semantic/vector search. If discussing exact API syntax not exposed by a tool, verify it against current primary documentation before use.

For every query record: query text, method, repositories, state/date/label filters, fields searched if known, result count, inspected pages, time, and limits. Paginate within the declared budget. If an API caps results, refine queries where useful and record remaining truncation. Count unique issues separately from result hits; prioritize direct dependencies, exact requirement matches, and shared behavior before weaker title matches.

Search results are candidate locators. Read bodies and decisive comments, not just snippets. Record what discussion was inspected and whether pagination completed. Relevant newer discussion can qualify an older body. When a deciding comment is inaccessible, do not infer its contents.

## Stopping and provenance

Stop at configured budgets, when planned queries and relevant traversal are exhausted, or when access fails. Record unassessed candidates and next queries, not just the accepted list. Do not silently expand repository/depth scope. Recheck changed sources where supported and material; reconcile once and flag residual inconsistency. Record that snapshots across multiple issues are not atomic.
