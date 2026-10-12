# AR-0109: Issue-series lifecycle updates and finalizer closure

Extend done/reopen/supersede/rollback/recovery transitions with one
correlation-bound public-safe issue projection. Enforce finalizer-only closure
after transitive evidence and hosted-identity checks. Test completion, replay,
crash between state/comment/close, stale revision, manual conflict, missing
evidence, concurrency and all finalizer gates; preserve Git/SQLite parity and
model checks, then require locally reproducible functional verification.
External review and CI are optional.
