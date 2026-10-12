# AR-0109: Issue-series lifecycle updates and finalizer closure

Extend done/reopen/supersede/rollback/recovery transitions with optional
correlation-bound public-safe issue projections. Enforce locally evidenced
finalizer eligibility; perform hosted-identity checks only when an optional
external closure is requested. Test completion, replay, crash between local
state and projection, stale revision, manual conflict, missing evidence,
concurrency, offline operation, and deferred reconciliation; preserve
Git/SQLite parity and model checks, then require locally reproducible
functional verification. External review and CI are optional.
