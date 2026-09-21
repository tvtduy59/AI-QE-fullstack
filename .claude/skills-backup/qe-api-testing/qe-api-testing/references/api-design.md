# API design checklist

Use only applicable categories:
- Inputs: required/optional/nullable/omitted distinctions, types, formats, encoding, empty/duplicate values, lengths, numeric precision, boundaries, and content types from the actual contract.
- Identity and permission: anonymous versus authenticated, expired/revoked credentials where supported, roles, object ownership, tenant boundaries, and field-level constraints. Authentication success does not establish authorization.
- Response: status, schema, types, headers, error payload, business values, and explicitly promised side effects. Schema evolution/backward compatibility needs supported consumer versions, not an invented compatibility promise.
- Collections: documented filters/sorts, cursor/page consistency, empty/final pages, duplicate/missing records, and permissions on totals. Concurrent data changes may alter pagination assumptions; state the consistency contract.
- Mutations: accepted versus rejected effects, transaction boundaries, repeated requests, retry/idempotency-key semantics, key scope/expiry, concurrent updates, and cleanup. Idempotency is a sourced contract or risk hypothesis, not an assumed feature of every endpoint.
- Failure: validation, authentication, authorization, dependency unavailability, timeout, quota, and malformed response behavior where relevant. Clarify unknown error codes; do not normalize them from implementation alone.
- Evidence: request metadata with secret redaction, response assertions, independent domain state where authorized, correlation ID, and cleanup outcome. External production services remain out of scope unless specifically approved.

Tool-specific syntax must be verified against the actual installed framework/specification version before implementation. This skill does not prescribe a tool version or infer system capabilities.
