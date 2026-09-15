# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0017](tasks/AR-0017.md): TLC resource-bound reliability | PR #319 signed head 5a9ba29 includes e3ad0ed capacity/preflight, 499e3e1 timeout alignment, and README correction; checks are pending. | Run and independently review PR #319 full gates; require terminal formal attestation/DCO, then merge and verify post-merge main. | codex-awc-ar0017-tlc-capacity-20260915 |
| P1 | [AR-0016](tasks/AR-0016-release-validation-dispatch.md): Release validation dispatch gate | PR #315 Verify 35003972069 failed at 20:02:41Z with explicit Java OOM during liveness after ~58 minutes: 46,492,959 generated, 38,466,180 distinct, 10,738,716 queued; no invariant violation. Exact head 067ba1c remains unmergeable. PR #318 is now testing the larger resource profile. | Await PR #318 Verify 35015342502 resource-profile result; retain PR #315 unmerged and use OOM evidence to guide remediation. | codex-awc-ar0016-release-gate-20260915 |

## Open

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | PR #316 merged as 7bf4501; post-merge Verify 35005629097 reached 28,432,589 distinct states but failed at the 20-minute RuntimeMaxSec boundary during liveness checking (exit 1), with TLC low-memory warning and no model error. Correctness remains unclosed pending a longer valid exact-head run. | Use the repaired longer formal timeout path or an explicitly approved rerun; then require terminal exact-head evidence before closure. | - |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | PR #317 repaired exact head 267efd9; Verify 35006681700 found no model error but failed at the 20-minute RuntimeMaxSec boundary during low-memory liveness checking after 30,663,299 distinct states. Formal pass remains unproven. | Create or select a reviewed formal-runtime remediation that permits this exact model to complete (longer containment and adequate heap), then rerun exact-head Verify before merge. | - |

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
