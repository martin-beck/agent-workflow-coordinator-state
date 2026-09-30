# AR-0025 plan: state-worktree observation contract

1. Read the coordinator development, architecture, quality and public-contract
   documentation plus the ASB AR-1544 failure evidence. Reconcile exact main,
   current PRs and hosted checks before claiming.
2. Reproduce `project_scan` with separate product and state repositories,
   shared paths, detached worktrees, dirty paths and missing metadata. Keep
   observations bounded and sanitized.
3. Implement the smallest coordinator-source repair that scans both bound
   checkouts, deduplicates paths, and preserves existing GitHub/run evidence
   behavior. Add negative tests for failed or malformed observations.
4. Run focused tests, full coordinator gates, formal/privacy/type checks and
   independent review. Publish only a clean signed+DCO exact-head PR.
5. Wait for exact-head required CI, merge only when green, publish an immutable
   release and verify it from a fresh clone.
6. Hand the exact release commit/tag to ASB AR-1544; do not accept a local
   vendor edit or mixed snapshot as downstream evidence.
