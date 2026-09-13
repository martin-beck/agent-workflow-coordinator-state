# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0001](tasks/AR-0001.md): Integrate AWQ v0.32.0 into the coordinator | Adopt AWQ v0.32.0 while retaining coordinator-native quality and formal gates. | Obtain independent exact-head review and green required CI for PR #20 at product commit 5ce3b97; merge only after review. | codex-awc-ar0001-pub-20260913 |

## Planned

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0002](tasks/AR-0002.md): Correctness-first coordinator upgrade protocol | Define a correctness-first coordinator release upgrade with verified backup and rollback. | Freeze the correctness invariants, state machine, compatibility boundary, and child-AR contracts. | - |
| P0 | [AR-0003](tasks/AR-0003.md): Release-upgrade contract and generator | Generate and validate complete, bounded upgrade instructions for every release. | Specify the release contract schema, generator, compatibility matrix, and hostile validation fixtures. | - |
| P0 | [AR-0004](tasks/AR-0004.md): Quiescence and upgrade preflight | Prevent upgrades from starting unless the coordination system can remain safe and functional. | Specify quiescence, prerequisite, admission, and reopen invariants with negative-path tests. | - |
| P0 | [AR-0005](tasks/AR-0005.md): Git-backend backup and restore | Back up and restore complete Git-backed coordination state without losing task history. | Define verified Git backup artifacts, restore ordering, and fault-injection coverage. | - |
| P0 | [AR-0006](tasks/AR-0006.md): SQLite backup, migration, and restore | Preserve SQLite authority and recoverability through coordinator upgrades and migrations. | Specify SQLite backup, migration, selector, integrity, and restore invariants with crash tests. | - |
| P0 | [AR-0007](tasks/AR-0007.md): Upgrade engine and rollback | Execute upgrades atomically and restore the known-good runtime on every failure path. | Implement the phase machine and explicit rollback commands only after contract and backend children are accepted. | - |
| P0 | [AR-0008](tasks/AR-0008.md): Formal upgrade and recovery model | Formally verify upgrade safety, crash recovery, rollback, and functional reopen conditions. | Model upgrade and rollback invariants and bind them to exhaustive bounded implementation tests. | - |
| P0 | [AR-0009](tasks/AR-0009.md): Release integration and first upgrade | Publish and exercise generated upgrade paths for every release without sacrificing recoverability. | Add release CI generation, publication evidence, and the first independently reviewed upgrade campaign. | - |
| P1 | [AR-0010](tasks/AR-0010.md): Operational upgrade runbooks and generated release steps | Make every release's prerequisites, steps, evidence, and rollback path explicit and safe to operate. | Generate release-specific operator and agent upgrade/rollback runbooks and privacy-test them. | - |
