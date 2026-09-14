---
{
  "branch": "fix/verified-superseded-dependencies",
  "checkpoint_commit": "2916855f8b0b3f23c2bfe1762c6af4afffb4331e",
  "claim_expires": "",
  "depends_on": ["AR-0002"],
  "id": "AR-0014",
  "next_action": "Independently review PR #79 at the immutable checkpoint, wait for exact-head CI, merge only after all required checks pass, then publish a signed immutable coordinator release before downstream vendor synchronization.",
  "owner": "",
  "plan": "../plans/AR-0014.md",
  "priority": "P0",
  "schema_version": 1,
  "status": "open",
  "summary": "Make explicitly verified superseded tasks satisfy dependencies only through a completed successor.",
  "task_revision": 1,
  "title": "Verified supersession dependency readiness",
  "updated_at": "2026-09-14T20:46:38+02:00",
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
