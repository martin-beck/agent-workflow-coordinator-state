---
{
  "branch": "fix/vendor-formal-runtime-closure",
  "checkpoint_commit": "",
  "claim_expires": "2026-09-15T17:02:50+00:00",
  "depends_on": [
    "AR-0002",
    "AR-0003"
  ],
  "id": "AR-0015",
  "next_action": "Create and independently review a minimal v0.3.8 metadata bump from exact merge 7b487aa; merge it, run exact post-merge Verify, publish signed immutable v0.3.8 targeting that merge, and verify the GitHub release.",
  "owner": "codex-awc-ar0015-v037-20260915",
  "plan": "../plans/AR-0015.md",
  "priority": "P1",
  "schema_version": 1,
  "status": "in_progress",
  "summary": "PR #307 merged at 7b487aa50f20d70cba8b860a66d006c2389fd58f; post-merge Verify 34996220200 green (512 tests, 95%, all formal tiers no-error, artifact 10407827035). Existing signed immutable tag v0.3.7 targets unrelated 550c014c and has no GitHub release, so publication provenance is invalid for this merge. Remediate with a new signed v0.3.8 release; do not move v0.3.7.",
  "task_revision": 13,
  "title": "Complete formal runtime vendor closure",
  "updated_at": "2026-09-15T16:45:25+00:00",
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

- 2026-09-15T16:32:41+00:00: Promote dependency-ready AR-0015 to implement the already prepared
  formal-runtime vendor closure PR #85, subject to exact-main rebase and full Verify.

- 2026-09-15T16:32:50+00:00: Claimed by codex-awc-ar0015-v037-20260915.

- 2026-09-15T16:33:00+00:00: Recorded command exit 1; command argv SHA-256
  2069104216d5af1d160732b2df3ce74de6bb0efdb85402feaa7f6a9fa1c460d9.

- 2026-09-15T16:33:14+00:00: Recorded command exit 0; command argv SHA-256
  ec358e32b41781be1a2709d2b9babeb2e4ad978d8b81ea61192dd6a4350d8746.

- 2026-09-15T16:33:28+00:00: Recorded command exit 0; command argv SHA-256
  1f290c2f11ff98c472cb05e7d52fa23d02ce7ec82a320af912f083e4eaf399d7.

- 2026-09-15T16:34:03+00:00: Recorded command exit 0; command argv SHA-256
  0d1695299686febd5fcd7788accec442284be32cb54451d99166ce04040036c8.

- 2026-09-15T16:34:26+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T16:37:59+00:00: Recorded command exit 0; command argv SHA-256
  ae8a5574caf1d0404a98066b625accc23b07c81b90efb711c5f0077a1e627723.

- 2026-09-15T16:41:22+00:00: 2026-09-15T16:41:00+00:00: Independent review found v0.3.7 signed tag
  targets 550c014c440cc9bc45727fea71d90a9025c554c3, not verified merge 7b487aa, and no GitHub
  release exists. Tag collision is immutable; no force-move performed.

- 2026-09-15T16:41:22+00:00: Recorded command exit 0; command argv SHA-256
  60acd298aeb8bc7f62fc205abe55cc3d956909334a30a32cd3461cbfdf0f2792.

- 2026-09-15T16:41:29+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T16:45:25+00:00: Recorded command exit 0; command argv SHA-256
  255a6819db9bde8dc1ce27cb19619a95ba269cc2e46d50764ca682d7b71bbf96.
