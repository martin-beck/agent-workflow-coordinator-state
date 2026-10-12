# AR-0108: Issue-series GitHub publication and receipt adapter

Add an optional Coordinator-owned GitHub adapter with public-safe rendering,
correlation-bound receipts, dry-run, and deterministic mock transport. Live
posting may use configured authentication, but local lifecycle progress requires
neither credentials, network access, nor GitHub state. Validate requested live
attempts before external effects; retain conflicts, failures, and unavailable
hosted state as typed deferred projections. Test success, replay, wrong
identity, closed or moved issue, permission failure, timeout, conflict, privacy
filtering, and offline operation under Git/SQLite parity, then require locally
reproducible functional verification. External review and CI remain optional.
