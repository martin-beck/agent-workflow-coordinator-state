# AR-0102: Issue-series lifecycle updates and finalizer closure

Extend done/reopen/supersede/rollback/recovery transitions with one
correlation-bound public-safe issue projection. Enforce finalizer-only closure
after transitive evidence and hosted-identity checks. Build the closure text
from durable records rather than free-form assertions. Test completion,
replay, crash between state/comment/close, stale revision, manual conflict,
missing evidence, concurrency and all finalizer gates; preserve Git/SQLite
parity and model checks, then require independent review and CI.
