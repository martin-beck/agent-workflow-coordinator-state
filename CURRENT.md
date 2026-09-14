# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | PR #80 merged into main 5b38583, but post-merge Verify 34882351034 failed the 95% total branch gate: 404 tests passed, total coverage 94%, due uncovered handoffctl superseded dependency-chain branches introduced by PR #79. Corrective PR #81 a8ef7ef adds tests only for non-superseded, malformed, self-referential, and cyclic superseded_by cases. | Independently review corrective PR #81 exact head a8ef7ef; merge only after awq/scope/smoke and exact-head coverage >=95% pass. Preserve production mutation/dispatch constraints. | codex-awc-ar0007-next-20260914 |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | Combined main regression at 5b38583 (PR #80 plus PR #79) ran 404 tests successfully but failed the repository Verify coverage gate: 5,423 statements, 1,908 branches, total branch coverage 94%, below fail-under=95. The failure occurred before formal workflow execution; GitHub checks show awq SUCCESS, scope SUCCESS, verify FAILURE, smoke SKIPPED. TLC admission also failed closed in the test log because systemd-run cgroup containment was unavailable, so no TLC result exists. This regression provides no implementation refinement or formal correspondence evidence. | Track the corrective coverage PR and independently review its exact head. Keep AR-0008 diagnostic-only with implementation_refinement=not-proven and mutation disabled; require coverage >=95 and a successful admitted formal workflow before treating the publication gate as green, and require separate executable caller/trace evidence before any refinement claim. | codex-awc-ar0008-next-20260914 |

## Open

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0014](tasks/AR-0014-verified-supersession-dependencies.md): Verified supersession dependency readiness | Make explicitly verified superseded tasks satisfy dependencies only through a completed successor. | Publish a signed immutable coordinator release containing the merged supersession implementation after release-specific provenance checks; then perform downstream vendor synchronization through AR-1182. Ignore unrelated coordinator coverage work. | - |

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
