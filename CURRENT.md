# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P1 | [AR-0016](tasks/AR-0016-release-validation-dispatch.md): Release validation dispatch gate | Prevent release preparation from bypassing full coordinator validation through path-based CI skipping. | Require a full release validation tier for vendor/runtime changes even when pull-request scope would skip Verify. | codex-awc-ar0016-release-gate-20260915 |

## Open

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | PR #306 merged as 4526b22b182d0b674d765b4ea2b82a8401524122; post-merge Verify 34991547376 green: 512 tests, 95% coverage, all event-appropriate TLC tiers no-error; artifact 10405499029. Continue trusted-session/backend-equivalence work with mutation, dispatch, execute, apply, and rollback unreachable; implementation_refinement remains not-proven. | Start the next AR-0007 correctness slice from exact main 4526b22b182d0b674d765b4ea2b82a8401524122; require independent exact-head review, signed public gates, and post-merge Verify. | - |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | AR-0008 evidence-map slice merged as PR #311 at b67c54a34ddb0789f561df0b4786ee34b8c2b2a9. Exact post-merge Verify 34999092550 passed: 512 tests, 95% coverage, all formal tiers no-error, artifact 10408728117. Added one explicit mapping from six typed rollback rejection tests to formal obligations; correspondence and implementation_refinement remain not-proven and mutation/authorization unreachable. | Continue AR-0008 only for a genuinely missing executable formal obligation. Require exact-head independent review, DCO, public gates, and post-merge Verify; do not promote AR-0012 or claim concrete refinement. | - |

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
| P0 | [AR-0014](tasks/AR-0014-verified-supersession-dependencies.md): Verified supersession dependency readiness | Make explicitly verified superseded tasks satisfy dependencies only through a completed successor. | Coordinator v0.3.6 is published and signed at a1bc4459f884ce447e8ee2884df12ea3ff4b710b. Future supersession tests/features must be added through this canonical coordinator-state handoffctl path; downstream vendor synchronization is intentionally removed. | - |
| P1 | [AR-0015](tasks/AR-0015-vendor-formal-runtime-closure.md): Complete formal runtime vendor closure | PR #309 merged at 6332f032b7445b8a02f60fdf99113d0d835de29e; post-merge Verify 34997001352 failed only formal evidence hash consistency: tools/handoffctl.py changed for v0.3.8 but formal/evidence.json retains prior digest. 512 tests executed; AWQ/scope passed. Existing v0.3.7 immutable tag remains untouched; no release published. | Repair formal/evidence.json using the canonical evidence generator from exact merge 6332f032; obtain independent review and green exact-head Verify, then publish signed immutable v0.3.8 targeting the repaired merge. | - |
