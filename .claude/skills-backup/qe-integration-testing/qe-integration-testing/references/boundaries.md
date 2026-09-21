# Boundary analysis

Inspect each relevant boundary for:
- Mapping and persistence: field transformations, precision, encoding, identifier propagation, invariants, and independent read evidence.
- Transactions: atomic outcomes within actual transaction boundaries; partial commit or compensation across services; cleanup that does not conceal the outcome.
- Asynchrony: pending/success/failure states, observable completion, documented latency bounds or unknown SLA, message order, duplicates, retry/backoff, poison messages, dead-letter policy, and replay rules. Never assume exactly-once processing.
- Concurrency: multiple writers, race windows, locks/version checks, stale reads, duplicate submissions, and idempotency scope; deterministic synchronization where feasible.
- Dependency faults: timeout, refusal, malformed data, unavailable credentials, partial outage, and recovery. Specify the selected failure mechanism and approved rollback before injection.
- Compatibility: supported producer/consumer/database schema combinations and migration stages; do not infer compatibility from deployment order alone.
- Observability: correlation across components, authoritative state, bounded polling, logs and redaction. “No error observed” is not a positive success oracle.

Document the exact known delivery/consistency contract. If it is absent, draft alternatives and a question. A unit test with a mocked dependency cannot validate that dependency's real behavior; a consumer contract check cannot by itself prove the full business workflow.
