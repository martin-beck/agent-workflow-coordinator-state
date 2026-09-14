---
{
  "branch": "fix/vendor-formal-runtime-closure",
  "checkpoint_commit": "",
  "claim_expires": "",
  "depends_on": ["AR-0002", "AR-0003"],
  "id": "AR-0015",
  "next_action": "Add the complete formal-runner/evidence closure to the vendor allowlist and prove downstream sync consumes it.",
  "owner": "",
  "plan": "../plans/AR-0015.md",
  "priority": "P1",
  "schema_version": 1,
  "status": "planned",
  "summary": "Ensure every formal verifier runtime input and regression test is present in vendor snapshots.",
  "task_revision": 1,
  "title": "Complete formal runtime vendor closure",
  "updated_at": "2026-09-14T21:30:00+02:00",
  "worktree_key": "agent-workflow-coordinator-vendor-formal-runtime-closure"
}
---

The coordinator vendor allowlist must include every file required by
`formal/handoffctl/verify.sh`, including `tools/tlc_runner.py`, the attestation
helper, formal evidence/configuration inputs, and their focused tests. The
allowlist must remain deterministic and preserve atomic sync, manifest hashes,
signatures, and downstream profile/binding isolation.

Acceptance: source/header/license checks, vendor manifest regression tests,
clean exact-tag sync and offline verification, full coordinator tests with at
least 95% branch coverage, formal tier verification, and an independently
reviewed signed DCO commit. Do not edit downstream vendor files by hand.
