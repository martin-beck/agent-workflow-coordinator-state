---
{
  "branch": "fix/verified-superseded-dependencies",
  "checkpoint_commit": "0a99db37fc9fbf9dbad815c38ccb7bb369d29901",
  "claim_expires": "2026-09-14T21:01:34+00:00",
  "depends_on": [
    "AR-0002"
  ],
  "id": "AR-0014",
  "next_action": "PR #83 prepares coordinator-only v0.3.6 release notes; await exact-head CI/review, merge, then publish a signed immutable v0.3.6 tag and perform downstream vendor synchronization through a new ASB-state AR.",
  "owner": "codex-ar0014-release-20260914",
  "plan": "../plans/AR-0014.md",
  "priority": "P0",
  "schema_version": 1,
  "status": "in_progress",
  "summary": "Make explicitly verified superseded tasks satisfy dependencies only through a completed successor.",
  "task_revision": 4,
  "title": "Verified supersession dependency readiness",
  "updated_at": "2026-09-14T19:03:53+00:00",
  "worktree_key": "agent-workflow-coordinator-verified-supersession-dependencies"
}
---

This P0 AR owns GitHub issue #78 and the coordinator-side contract needed by
downstream projects whose dependency graph contains a task replaced by a
recovery successor. The current runtime treats only `done` as dependency
completion, leaving a graph permanently unclaimable when the original task is
correctly marked `superseded`.

The repair must be explicit and fail closed. A task with status `superseded`
may satisfy a dependency only when it records exactly one valid successor in
the same project graph, that successor is not itself superseded, and the
successor is `done` with valid immutable evidence. Missing, ambiguous,
unfinished, cyclic, cross-project, malformed, or stale successor references
remain unsatisfied. Existing tasks without successor metadata retain current
behavior and remain blocked.

The implementation must preserve project binding, lease ownership, revision
CAS, lock ordering, backend parity, generated status views, and offline
operation. It must define migration and validation rules for existing Git and
SQLite state, reject unknown successor fields where the schema is strict, and
never infer a successor from free-form `next_action` text.

Acceptance requires the upstream PR #79 implementation to have exact-head
CI, independent review, signed DCO, and an immutable signed release. The
downstream AR-1182 vendor synchronization and all downstream state repairs
must wait for that release; this AR must not patch downstream vendor files.

Authoritative sources:

- Issue: https://github.com/martin-beck/agent-workflow-coordinator/issues/78
- Implementation PR: https://github.com/martin-beck/agent-workflow-coordinator/pull/79

- 2026-09-14T20:57:31+02:00: PR #79 merged through the protected path as
  `0a99db37fc9fbf9dbad815c38ccb7bb369d29901`; focused Git/SQLite tests and
  independent review passed. A later unrelated main push is not part of this
  AR's feature scope. Release publication remains pending.

- 2026-09-14T19:01:34+00:00: Claimed by codex-ar0014-release-20260914.

- 2026-09-14T19:03:53+00:00: Created coordinator-only release preparation PR #83 at signed commit
  71f2aec. No ASB or asb-tui files included. Downstream audit found current v0.3.5 vendor digest
  mismatch from downstream patch 4915e9c9a; vendor sync must wait for signed v0.3.6.
