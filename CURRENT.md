# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | PR #173 merged 2677170f; Verify 34921930180 succeeded (TLC 121472/90752 main, 110/94 small, artifact 10378332084). PR #174 published at 09b446a. | Independently review PR #174 exact head 09b446a; merge only after awq/scope/smoke and full Verify pass, then record post-merge evidence. | codex-awc-ar0007-next-20260914 |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | Reviewed PR #174 exact signed head 09b446a against 2677170f. Test-only rejects null state_revision=None before common-lock; focused hostile/session/lock suite passes 45 tests and 18 subtests. AWQ/scope/smoke green; Verify skipped. | Continue independent exact-head review of the next caller/session slice. Require project/authority/revision/fence/barrier type and equality validation before common-lock, process-death/replacement/WAL evidence, trusted reread plus second recheck, and admitted TLC before stronger claims. Preserve implementation_refinement=not-proven, mutation disabled, and do not promote AR-0012. | codex-awc-ar0008-next-20260914 |

## Open

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0014](tasks/AR-0014-verified-supersession-dependencies.md): Verified supersession dependency readiness | Make explicitly verified superseded tasks satisfy dependencies only through a completed successor. | Coordinator v0.3.6 is published and signed at a1bc4459f884ce447e8ee2884df12ea3ff4b710b. Future supersession tests/features must be added through this canonical coordinator-state handoffctl path; downstream vendor synchronization is intentionally removed. | - |

## Planned

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0009](tasks/AR-0009.md): Release integration and first upgrade | Publish and exercise generated upgrade paths for every release without sacrificing recoverability. | Add release CI generation, publication evidence, and the first independently reviewed upgrade campaign. | - |
| P0 | [AR-0012](tasks/AR-0012.md): Durable upgrade barrier and SQLite write fencing | Durably fence upgrade admission and every SQLite authority mutation under one project barrier. | Promote only after AR-0007 is complete; then implement the accepted barrier, fencing, and fail-closed SQLite contract with exact-head tests and formal refinement evidence. | - |
| P0 | [AR-0013](tasks/AR-0013.md): Selector-aware authenticated versioned runtime | Bind an authenticated, selector-aware versioned coordinator runtime to safe upgrade and rollback execution. | Design and implement the stable bootstrap, authenticated versioned runtime store, selector publication, and validation-to-exec binding only after AR-0007 and AR-0008 provide accepted executable contracts. | - |
| P1 | [AR-0010](tasks/AR-0010.md): Operational upgrade runbooks and generated release steps | Make every release's prerequisites, steps, evidence, and rollback path explicit and safe to operate. | Generate release-specific operator and agent upgrade/rollback runbooks and privacy-test them. | - |
| P1 | [AR-0015](tasks/AR-0015-vendor-formal-runtime-closure.md): Complete formal runtime vendor closure | Ensure every formal verifier runtime input and regression test is present in vendor snapshots. | Add the complete formal-runner/evidence closure to the vendor allowlist and prove downstream sync consumes it. | - |
| P1 | [AR-0016](tasks/AR-0016-release-validation-dispatch.md): Release validation dispatch gate | Prevent release preparation from bypassing full coordinator validation through path-based CI skipping. | Require a full release validation tier for vendor/runtime changes even when pull-request scope would skip Verify. | - |

## Done

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0001](tasks/AR-0001.md): Integrate AWQ v0.32.0 into the coordinator | Adopt AWQ v0.32.0 while retaining coordinator-native quality and formal gates. | Merged PR #20 at merge commit 713761b; post-merge AWQ PR check passes; no coordinator release was published by this merge. | - |
| P0 | [AR-0002](tasks/AR-0002.md): Correctness-first coordinator upgrade protocol | Define a correctness-first coordinator release upgrade with verified backup and rollback. | Merged PR #21 at bd070596729949a77cfb4fae7c4230055f3f4ece. Post-merge AWQ and focused contract verification pass; no coordinator release published. AR-0011 remains the next open child. | - |
| P0 | [AR-0003](tasks/AR-0003.md): Release-upgrade contract and generator | Generate and validate complete, bounded upgrade instructions for every release. | PR #23 at 736d2e2 is published; await exact-head verify run 34784319165 and independent review before merge. | - |
| P0 | [AR-0004](tasks/AR-0004.md): Quiescence and upgrade preflight | Prevent upgrades from starting unless the coordination system can remain safe and functional. | AR-0004 complete; PR #24 merged and post-merge main verification green. AR-0007 is now dependency-ready for phase-machine implementation. | - |
| P0 | [AR-0005](tasks/AR-0005.md): Git-backend backup and restore | Back up and restore complete Git-backed coordination state without losing task history. | AR-0005 complete; PR #25 merged and post-merge main verification green. AR-0006 PR #26 remains open pending independent review and exact-head checks. | - |
| P0 | [AR-0006](tasks/AR-0006.md): SQLite backup, migration, and restore | Preserve SQLite authority and recoverability through coordinator upgrades and migrations. | AR-0006 complete; PR #26 merged and post-merge main verification green. AR-0004 remains blocked pending its correctness fixes and healthy exact-head rerun. | - |
| P0 | [AR-0011](tasks/AR-0011.md): Bounded TLA+ execution and admission safety | Exact-head PR #22 formal publication gate independently reviewed green. | Await parent merge decision; retain full-exhaustive claims for successful scheduled/manual run and preserve merge-tree attestation provenance. | - |
