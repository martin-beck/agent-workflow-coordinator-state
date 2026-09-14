# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | PR #76 merged at de2278a from signed 306f55f. The journal harness durably replaces a complete record, dies before the caller continues, reopens and validates operation identity, authority revision, fencing token, barrier digest, and envelope digest, and rejects authority-revision drift fail-closed. Independent review passed 30 focused tests, 402 full tests, 95% coverage, Ruff, mypy, format, and diff. Post-merge Verify 34881587836 succeeded on the exact merge head; mutation/dispatch/upgrade/apply/rollback wiring remains unchanged. | Implement the next control/journal slice at merged head de2278a: bind durable control CAS/release or stale-fence/ambiguous-safe-mode recovery to the journal record, then publish a signed PR after independent review. | codex-awc-ar0007-next-20260914 |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | Exact merged origin/main de2278af56f5f28d24e68a8a859b680ff03f4b66 (PR #76, 306f55f) adds a journal process-death trace: complete UpgradeEngine plan journal is atomically replaced, worker SIGKILLs, reopened journal preserves authority revision/fencing token/barrier and envelope digests, and a drifted authority revision is rejected on load. This maps to narrow durable journal identity/IdentityStable and stale-context rejection, related to RecheckEvidence/StaleCASRejected; it does not bind journal state to durable control-store CAS/barrier, manifest/backup digest, phase commit/release, lock ownership, or rollback ambiguity. Formal hashes unchanged: TLA 2a1a31f, CFG e38502a, evidence 035e6c15; implementation_refinement=not-proven; mutation disabled. | Keep AR-0008 diagnostic-only and mutation disabled. Next slice must link the recovered journal to control-store expected revision/fence CAS and manifest digest, exercise started/verified/releasing/released/ambiguous recovery with SIGKILL, and prove idempotent reconciliation/no duplicate restore before any model extension or correspondence claim. No TLC warranted. | codex-awc-ar0008-next-20260914 |

## Planned

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0009](tasks/AR-0009.md): Release integration and first upgrade | Publish and exercise generated upgrade paths for every release without sacrificing recoverability. | Add release CI generation, publication evidence, and the first independently reviewed upgrade campaign. | - |
| P0 | [AR-0012](tasks/AR-0012.md): Durable upgrade barrier and SQLite write fencing | Durably fence upgrade admission and every SQLite authority mutation under one project barrier. | Promote only after AR-0007 is complete; then implement the accepted barrier, fencing, and fail-closed SQLite contract with exact-head tests and formal refinement evidence. | - |
| P0 | [AR-0013](tasks/AR-0013.md): Selector-aware authenticated versioned runtime | Bind an authenticated, selector-aware versioned coordinator runtime to safe upgrade and rollback execution. | Design and implement the stable bootstrap, authenticated versioned runtime store, selector publication, and validation-to-exec binding only after AR-0007 and AR-0008 provide accepted executable contracts. | - |
| P1 | [AR-0010](tasks/AR-0010.md): Operational upgrade runbooks and generated release steps | Make every release's prerequisites, steps, evidence, and rollback path explicit and safe to operate. | Generate release-specific operator and agent upgrade/rollback runbooks and privacy-test them. | - |

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
