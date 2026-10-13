# AR-0034 plan: fail-closed legacy worktree binding repair

1. Reproduce the ASB AR-1826 partial-legacy state against the exact v0.7.5
   behavior and verify no existing command safely clears it.
2. Specify a single explicit repair command that accepts only the task,
   expected revision, retained worktree key, and bounded note; require an open,
   unowned task with empty branch and exact key, then clear only that key.
3. Add positive coverage and hostile coverage for stale revisions, wrong keys,
   non-empty branches, active owners/leases, malformed input, conflicts, and
   replay/idempotency; preserve bind-worktree rejection and authority fences.
4. Update the coordinator guide/CLI contract and any formal transition evidence
   needed for the new state transition without broadening mutation authority.
5. Run focused and full native/AWQ/schema/privacy/formal gates, independent
   exact-head review, signed-DCO PR and exact-head CI; publish an immutable
   release and record durable evidence for ASB AR-1826 requalification.
