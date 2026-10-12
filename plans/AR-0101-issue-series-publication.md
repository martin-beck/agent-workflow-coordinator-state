# AR-0101: Issue-series GitHub publication and receipt adapter

Add a narrowly scoped authenticated GitHub adapter invoked only through
Coordinator. It renders public-safe series metadata, records correlation-bound
receipts, supports dry-run and deterministic mock transport, and validates
repository/issue/revision before publication. Retried calls must discover and
verify the matching prior comment rather than duplicate it; conflicting markers
or malformed responses require typed recovery. Test success, replay, wrong
identity, closed/moved issue, permission failure, timeout, conflict and privacy
filtering under Git/SQLite parity, then obtain independent review and CI.
