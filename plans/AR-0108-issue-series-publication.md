# AR-0108: Issue-series GitHub publication and receipt adapter

Add a Coordinator-owned authenticated GitHub adapter with public-safe rendering,
correlation-bound receipts, dry-run and deterministic mock transport. Validate
repository, issue and manifest revision before publication. Retries discover
and verify a matching comment rather than duplicate it; conflicting markers or
malformed responses require typed recovery. Test success, replay, wrong
identity, closed/moved issue, permission failure, timeout, conflict and privacy
filtering under Git/SQLite parity, then require locally reproducible functional
verification. External review and CI are optional.
