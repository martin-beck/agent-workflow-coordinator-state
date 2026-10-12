# AR-0107: Issue-to-AR series contract and reviewed decomposition

Implement a strict issue-series manifest and locally validated `handoffctl` planning and
creation path. Support dry-run, require scope/acceptance/ownership and
dependency rationale for each generated AR, atomically create the graph and
finalizer, and retain Git/SQLite parity. Add schema, migration, property,
fault, concurrent-create, generated-view and bounded-model tests. Reject
duplicate, stale, malformed, private-text, cross-project, cyclic, orphaned and
partial-write cases. Require locally reproducible exact-head verification;
external review and hosted CI are optional.
