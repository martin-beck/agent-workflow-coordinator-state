---
{
  "branch": "fix/release-validation-dispatch",
  "checkpoint_commit": "",
  "claim_expires": "",
  "depends_on": ["AR-0003", "AR-0015"],
  "id": "AR-0016",
  "next_action": "Require a full release validation tier for vendor/runtime changes even when pull-request scope would skip Verify.",
  "owner": "",
  "plan": "../plans/AR-0016.md",
  "priority": "P1",
  "schema_version": 1,
  "status": "planned",
  "task_revision": 1,
  "summary": "Prevent release preparation from bypassing full coordinator validation through path-based CI skipping.",
  "title": "Release validation dispatch gate",
  "updated_at": "2026-09-14T21:30:00+02:00",
  "worktree_key": "agent-workflow-coordinator-release-validation-dispatch"
}
---

Changes that affect release metadata, vendor closure, formal inputs, or
runtime packaging must execute the complete release validation tier. Path-based
pull-request optimization may remain for ordinary changes, but it must not be
the only evidence for a release candidate. The gate must preserve reproducible
CI, pinned tools, DCO/signature checks, formal evidence, and clear failure
classification without changing downstream repositories.

Acceptance: a regression test or workflow proof demonstrates that release
preparation invokes full tests, coverage, formal verification, and attestations;
ordinary non-release PRs retain their bounded fast path; documentation explains
the distinction and no release/tag is published by this AR.
