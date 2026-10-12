# AR-0100: Issue-to-AR series contract and reviewed decomposition

Implement a strict versioned issue-series manifest and a reviewed `handoffctl`
planning/create path. It must support dry-run, require scope/acceptance/
ownership/dependency rationale for every generated AR, and atomically create
the complete dependency graph plus one finalizer AR. Reject duplicate, stale,
malformed, private-text, cross-project, cyclic, orphaned, partial-write and
concurrent-create cases. Preserve Git/SQLite parity and extend bounded formal
models for identity, completion ordering and atomic creation. Require focused
schema, migration, property/fault, generated-view, independent-review and
hosted evidence.
