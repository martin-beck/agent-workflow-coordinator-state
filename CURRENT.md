# Agent Workflow Coordinator current coordination state

This file is generated. Read `README.md`, then use `tools/handoffctl snapshot`.
Never edit this file directly.

## In Progress

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0089](tasks/AR-0089.md): Restore Coordinator-state vendor integrity | Repair the Coordinator state repository whose tracked vendored runtime and tests were changed directly after the recorded vendor snapshot, leaving coordinator.vendor.json inconsistent with authoritative bytes. | Move the Coordinator-state-only TUI session additions into reviewed upstream Coordinator contracts, then restore the state repository with an official complete vendor synchronization and exact digest verification. | coordinator-ar0089-session-handoff |

## Open

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0009](tasks/AR-0009.md): Release integration and first upgrade | Exact origin/main f82467bfca14080a207361156fe43ff710f54b96 release-readiness audit: 58 release identity/workflow/runbook/contract/generator/command tests passed with 81 subtests. Unsigned lightweight tag policy and hostile source/artifact/determinism checks remain explicit; no new dependency-safe release seam found. | Keep AR-0009 open for a genuinely uncovered release-integration/readiness boundary; do not add signing gates or signing prerequisites. | - |
| P0 | [AR-0012](tasks/AR-0012.md): Durable upgrade barrier and SQLite write fencing | Exact origin/main f82467bfca14080a207361156fe43ff710f54b96 validation passes 1436 tests; v10 refinement contract already binds the SQLite route inventory and crash/recovery evidence. No distinct dependency-safe barrier/refinement seam found without enabling mutation or dispatch. | Keep the exact route inventory and crash/recovery evidence bound to the v10 contract; do not claim Python refinement or enable upgrade apply/rollback. | - |
| P0 | [AR-0013](tasks/AR-0013.md): Selector-aware authenticated versioned runtime | Exact origin/main f82467bfca14080a207361156fe43ff710f54b96 selector/runtime hostile matrix passed 192 tests across runtime bootstrap, selector authority/recovery, admission, engine, and identity. Injected publication failures remain fail-closed; no new dependency-safe non-overlapping seam found while mutation/dispatch stay disabled. | Keep AR-0013 open for a genuinely uncovered selector/versioned-runtime correctness boundary after future merges; preserve fail-closed mutation and dispatch. | - |
| P0 | [AR-0031](tasks/AR-0031.md): Executable upgrade mutation and rollback boundary | Backup and authority-neutral stage verification are merged and formally mapped; runtime replacement, selector publication, commit, apply, and rollback remain fail-closed. | Design the next smallest pre-commit selector/readiness evidence seam; do not enable selector publication, runtime replacement, commit, apply, or rollback until independent barrier, process-death, and formal contracts pass. | - |
| P0 | [AR-0060](tasks/AR-0060.md): First release integration and upgrade campaign | First release campaign is not yet authorized: generated prerequisites/runbooks and unsigned-tag checks exist, but selector publication, runtime replacement, authority commit/apply, and rollback mutation remain rejection-only. Fresh-clone campaign must wait for the new separately gated AR-0061, AR-0062, and AR-0063 sequence. | Keep AR-0060 in progress while AR-0061 proves selector/runtime publication, AR-0062 proves authority commit/apply, and AR-0063 proves rollback and the complete fresh-clone campaign. | - |
| P0 | [AR-0063](tasks/AR-0063.md): Rollback and first release integration campaign | Complete rollback and the first supported upgrade campaign without exposing a partial or non-functional coordinator. | Implement and independently verify the first durable rollback boundary: bind verified backup, restore, runtime, barrier, and fencing identities under the held barrier; cover process death, ambiguous fsync, reopen, and competing-owner rejection while keeping public rollback and release publication disabled. | - |
| P0 | [AR-0069](tasks/AR-0069.md): Roles release and downstream pinning | Release agent-workflow-roles v1.0.0 with SPDX graph, bounded distribution archives, and a downstream lock manifest following the coordinator vendor pattern. | Define the authoritative agent-workflow-roles package/repository and release target, then prepare its manifest, SPDX graph, bounded archives, and downstream lock. | - |

## Planned

| Priority | Task | Summary | Next action | Owner |
| --- | --- | --- | --- | --- |
| P0 | [AR-0088](tasks/AR-0088.md): Supported active-task worktree binding | Allow an active legacy task with empty branch/worktree metadata to bind one isolated product worktree through a validated Coordinator mutation instead of manual task-file edits or unfenced git -C execution. | Implement a supported exact-revision worktree-binding transition for claimed legacy tasks, obtain independent review, merge the signed reviewed tree, and publish a complete downstream vendor handoff. | - |
